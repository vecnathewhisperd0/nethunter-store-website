---
layout: page
title: Inclusion How-To

---

This page documents how a new application gets included in the main
NetHunter Store repository. It includes the technical details that a submitter should be aware of.

Application Inclusion Proposal
------------------------------

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
by the minimal issue template; and wait for people in the NetHunter team to review the
application and do all necessary steps for you.

### Proposal by Metadata Merge Request

A more advanced alternative for application inclusion is to
write a NetHunter Store metadata file for the application yourself, and propose
inclusion by filing a git merge request on the NetHunter Store application metadata
repository ([nethunter-storedata GitLab
repository](https://gitlab.com/kalilinux/nethunter/store/nethunter-storedata/)). This will lead to
much quicker inclusion as the already-available metadata file will reduce
the burden on reviewers when inspecting your proposed metadata; the submitter
assumes responsibility of providing a correct metadata file.

When proposing inclusion this way, it is assumed that:

-   You have a good understanding of what the NetHunter Store is for.
-   You already read and understand the [Inclusion
    Policy](../Inclusion_Policy).
-   You already read and understand the [Repository Style
    Guide](../Repository_Style_Guide).
-   You already read and understand
    [the relevant parts of the F-Droid documentation](../Build_Metadata_Reference).
-   You have an account on [GitLab](https://gitlab.com/).
-   You have a local instance of the F-Droid server software, and you know
    what you are doing.


Application Review Process
--------------------------

Once the inclusion proposal is filed, the application will enter a
reviewing process where NetHunter staff look into the applications source
code and determine whether the it fits for inclusion (and when it's
not, determine all necessary steps to make it so).


### Special Consideration of Metadata Merge Request

In case the inclusion is from a GitLab merge request, the review process is
theoretically the same. They are done mostly to confirm that
the proposed metadata is consistent with what is really in the
application source code. Steps about writing and committing metadata
are omitted, as they will use the original metadata file you proprosed.
Feedback will be given on the original merge request thread that the
application was proposed; and once the process is completed, the request
will be merged to the `master` branch of the fdroiddata
GitLab repository.

In an attempt to optimize the process, when you proposed inclusion via
metadata merge request, NetHunter staff rely on several assumptions
([outlined above](#Proposal_by_Metadata_Merge_Request)). As such, the
reviewing process will be much less intensive in several respects, and
consumes much less time. Policy-violating applications that somehow
sneaked in this way will be dealt with after the fact.



External Links
--------------

-   [NetHunter Store application submission queue on
    GitLab](https://gitlab.com/kalilinux/nethunter/store/rfp/issues) (for new submissions)
-   [NetHunter storedata GitLab repository](https://gitlab.com/kalilinux/nethunter/store/nethunter-storedata)
-   [nethunter-storedata revision
    history](https://gitlab.com/kalilinux/nethunter/store/nethunter-storedata/commits/master)
