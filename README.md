# `ned-ppa` Build

Run the `bbuild` script to build the binary package. Run the `sbuild` script to build the source package and push it to the PPA.

**Note:** This is parked for now. Source packages pushed to Launchpad cannot access the Internet to build, so cargo cannot download dependencies. I am going leave this as a branch for future reference while I just build binary debs - https://github.com/nevdelap/ned-deb - to release on GitHub instead of trying to put them in my PPA.
