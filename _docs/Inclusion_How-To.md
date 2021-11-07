---
layout: page
title: Inclusion How-To

---

This page documents how a new application gets included in the main
NetHunter Store repository. It includes the technical details that a
submitter should be aware of.

## Application Inclusion Proposal

To propose inclusion of a new application to the main NetHunter Store repository,
one could post the applications relevant information to the Submission
Queue. The more advanced alternative is writing a complete metadata file
yourself, test, and propose inclusion (merge request) directly into
the nethunter-storedata Git repository; speeding up the process. Both ways will be
described below in detail.

Note that you can propose inclusion even you are not a developer or
maintainer of the proposed application itself. See [Inclusion
Policy](../Inclusion_Policy) and [Repository Style
Guide](../Repository_Style_Guide) for the policy aspect of this
section.

### Proposal by Submission Queue

This is the simplest way to get the application included. But due to an
amount of reviewer labor required for each application, this is the
slowest method.

Do this by creating a new ticket at the [NetHunter Store Submission Queue on
GitLab](https://gitlab.com/kalilinux/nethunter/store/rfp/issues), add all details required
by the minimal issue template; and wait for people in NetHunter Store team to review the
application and do all necessary steps for you.

### Proposal by Metadata Merge Request

A more advanced alternative for application inclusion is to
write an NetHunter Store metadata file for the application yourself, and propose
inclusion by filing a git merge request on the NetHunter Store application metadata
repository ([nethunter-storedata GitLab repository](https://gitlab.com/kalilinux/nethunter/store/nethunter-storedata/)).
 This will lead to
much quicker inclusion as the already-available metadata file will reduce
the burden on reviewers when inspecting your proposed metadata; the submitter
assumes responsibility of providing a correct metadata file.

When proposing inclusion this way, it is assumed that:

-   You have a good understanding of what [Free
    Software](https://www.gnu.org/philosophy/free-sw.html) means, and
    what NetHunter Store is for.
-   You already read and understand the [Inclusion
    Policy](../Inclusion_Policy).
-   You already read and understand the [Repository Style
    Guide](../Repository_Style_Guide).
-   You already read and understand
    [the relevant parts of the NetHunter Store documentation](../Build_Metadata_Reference).
-   You know how to use [Git VCS](https://git-scm.com/), and know how
    a merge request (a.k.a. "pull request" in
    GitHub terminology) works in general.
-   You have an account on [GitLab](https://gitlab.com/).
-   You have a local instance of the NetHunter Store server software, and you know
    what you are doing.

Recommended steps to propose inclusion this way are written on the [NetHunter Store
application metadata repository](https://gitlab.com/fdroid/nethunter-storedata/blob/master/CONTRIBUTING.md).

## Application Review Process

Once the inclusion proposal is filed, the application will enter a
reviewing process where NetHunter Store staff look into the applications source
code and determine whether the it fits for inclusion (and when it's
not, determine all necessary steps to make it so).

As NetHunter Store is a software repository which promises users free software,
a review process is for ensuring that all applications
distributed from the NetHunter Store main repository are Free Software.

This is a nonexhaustive list of what a reviewer would do:

-   They will go to your source code repository, and look for copyright
    notices in license files, including README, to check that the
    proposed application is released under [recognized Free
    Software license(s)](https://www.gnu.org/licenses/license-list.html).
-   They will look at your build script to see which build system you
    use, and whether NetHunter Store build server can handle it (Ant and Gradle
    are the most common and easiest ones).
-   They will try to download a copy of your source code.
-   They will look in all source code files to verify that their
    licenses are consistent with corresponding license/README files.
-   They will check if your application uses any pre-compiled libraries or
    binary blobs.
-   They will skim through the source code to see if your application
    uses Non-Free dependencies, shows advertisements, tracks users,
    promotes Non-Free services/applications, or does anything that is
    harmful or otherwise undesirable for users.
-   They will try patching your application to remove usage of
    third-party proprietary software (if there is any).
-   They will try to determine a suitable update process for your
    application (e.g. by looking at how your releases relate to VCS tags
    and/or version information
    in _AndroidManifest.xml_).
-   They will try writing a suitable metadata file for your application,
    and add it to local NetHunter Store build server instance.
    (`fdroid rewritemeta`, `fdroid
    lint` are used to ensure that metadata is well-formed)
-   They will try to build your application in an isolated environment to
    see if the process succeeds and yield a functional APK.
-   If all went smoothly, they will add a new metadata file to their
    local nethunter-storedata git repository and synchronizes the change
    to GitLab.

In the case that the application failed some steps in the review, feedback
will be given in the original submission queue thread where the proposal
was posted.

Once the nethunter-storedata repository is updated on GitLab, it's mostly just a
matter of time before NetHunter Store's official build server will fetch, build,
and publish your application on the main NetHunter Store repository.

You can confirm the inclusion of your application by looking at the [GitLab
nethunter-storedata revision
history](https://gitlab.com/kalilinux/nethunter/store/nethunter-storedata/commits/master).

### Special Consideration of Metadata Merge Request

In case the inclusion is from a GitLab merge request, the review process is
theoretically the same. They are done mostly to confirm that
the proposed metadata is consistent with what is really in the
application source code. Steps about writing and committing metadata
are omitted, as they will use the original metadata file you proprosed.
Feedback will be given on the original merge request thread that the
application was proposed; and once the process is completed, the request
will be merged to the `master` branch of the nethunter-storedata
GitLab repository.

In an attempt to optimize the process, when you proposed inclusion via
metadata merge request, NetHunter Store staff rely on several assumptions
([outlined above](#Proposal_by_Metadata_Merge_Request)). As such, the
reviewing process will be much less intensive in several respects, and
consumes much less time. Policy-violating applications that somehow
sneaked in this way will be dealt with after the fact.

## Build Process

After the application metadata is added to nethunter-storedata GitLab repository,
the next step is for the main NetHunter Store build server to fetch
the applications source code and related components, build the application,
and publish it on the main NetHunter Store repository.

This build process is done **daily**, and applications are processed
in batch. As steps are done behind the scene and are mostly automatic;
all the submitter needs to do is to wait for it to finish.

A record of the build process for each application is provided on the NetHunter Store wiki, as a
subpage `lastbuild` of the applications information
page (e.g. [here is the lastbuild page for the NetHunter Store
Client](https://store.nethunter.com/wiki/page/com.nethunter.store/lastbuild)).
This is useful to aid in diagnosing problems when the build unexpectedly
failed.

### Metadata Refreshing Process

When the scheduled building time arrives, the NetHunter Store build server will
fetch changes from the nethunter-storedata GitLab repository and merge it to a local
repository. Then, update checks will be performed for all
applications. If a new version is found, their metadata files will be
updated and committed to the repository by the author `NetHunter Store
Builder <admin@store.nethunter.com>`.

Once metadata files are updated, the NetHunter Store Server will check them against a
list of released APKs to constuct a list of new applications and/or
versions that need to be built. It will then enter the application
preprocessing process, followed by the build process for each of them.

### Application Preprocessing

### Application Build Process

### APK Signing Process

### Repository Publishing Process

## What to Expect

When your application metadata is approved and accepted into the nethunter-storedata
git repository on GitLab, **it won't immediately appear** in the main
NetHunter Store repository.

Provided that your application does not have any build problems, it would
takes somewhere **around 24 to 48 hours** from nethunter-storedata merge
until the application to appears in the main
repository.
This timing limitation is due to the APK signing part of the build process,
which requires human intervention on keystore access
step.

Nevertheless, your application will not appear in store.nethunter.com's Lastest
Apps list just yet, even though people can now already search and
download it: Once the application appeared in the main NetHunter Store
repository, it would take another day before appearing on [Latest Apps
list](https://store.nethunter.com).

## External Links

