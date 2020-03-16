
## multiattach patch

With this patch the Cinder Quobyte driver is enabled to use multiattach. Please note that using Cinder multiattach with Quobyte requires additional external locking services to be in use and Quobyte client caching to be off for the used Quobyte volume(s).

This patch applies to stripped packaged installations as well as full source tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory. For stripped packaged installations please run:

    patch -p2 < /path/to/patchfile

For full source tree installations please run:

    patch -p1 < /path/to/patchfile
