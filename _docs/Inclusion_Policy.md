---
layout: page
title: Inclusion Policy

---

All applications in the repository must be free software.
We do accept binary apk into the repo as long as they are free.

For open source software that we are asked to build, please note:

-   We cannot build apps using Google's proprietary "play-services".
    Please talk to upstream about an untainted build flavor (either
    using microg or removing non-free dependencies completely).
-   We cannot build apps using proprietary tracking/analytic
    dependencies like Crashlytics and Firebase. Please talk to upstream
    about an untainted build flavor (either using a FLOSS analytics
    software like ACRA or by removing non-free dependencies completely).
-   We cannot build apps using proprietary ad libraries. We have nothing
    against advertisments, but they must be provided by a FLOSS compatible way.
-   We cannot build apps requiring non-free buildtools, including
    Oracle's JDK or some pre-release toolchains.


Additionally:

-   The source code for the application must be maintained in a publicly
    accessible Version Control System which we have support for (git,
    hg, svn, bzr), and the source code needs to be maintained in an up
    to date state.
-   The software should not download additional executable binary
    files (e.g. non-free addons, auto-updates, etc).
-   The software should use its own unique Android package ID. Where the
    application is a fork of another (even one not included in the
    NetHunter repository) it must have a new ID, different from
    the original.
-   Although not ideal, "non-functional" assets (e.g. artwork) *may* be
    acceptable under less permissive licenses than functional code - an
    example would be artwork assets that are licensed only for use with
    that particular game. In any case though, they must be included
    under some kind of license, and not be copyright violations.
-   Trademarks must not be infringed, and any other legal requirements
    must be adhered to.
-   Kali NetHunter does not sign up for any API keys. Even if provided by a
    third party, we include them in both, binary and
    sourcecode releases.
-   Binary dependencies such as JAR files have to be replaced by
    source-built versions or used from a trusted repository
    (see manual).

Ideally:

-   Releases should be clearly tagged (or otherwise marked).

When including donation information, the relevant donation links (e.g. Bitcoin/
PayPal/Flattr/etc) must also be available either:

-   In a README or similar file in the projects source code.
-   On the applications main website.
-   If the software is hosted on GitLab, then it is sufficient that the
    person requesting donation info to be added to the nethunter-storedata repository
    is the same user account which manages the application source code.

This is to prevent arbitrary people from maliciously changing the donation links of
applications in the main NetHunter repository without the consent of upstream developers.

For more information on adding applications to the NetHunter Repository,
see the [Inclusion How-To](../Inclusion_How-To).
