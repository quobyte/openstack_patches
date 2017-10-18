
## truncate-ephemeral_patch

This patch changes Nova ephemeral image prealloc behaviour by running truncate instead of fallocate. This improves performance with ephemeral images on Quobyte volumes.
This change may have a possible performance impact on other backends.

The patch comes in two versions:

1. _truncate-ephemeral_<Release name>-Pike.patch_ - The pure driver patch for patching package based installations that strip tests and other development elements
2. _truncate-ephemeral_<Release name>-Pike_full_source_tree.patch_ - The full source patch including updates of unit tests and release notes files


### Installation

The patch usage is slightly different for both versions (pure driver vs. full source patch). The difference resides in the -p parameter for the patch command and is applied as follows:

#### Usage for the pure driver patch

This patch can be applied by navigating to the Cinder project package root directory and running:

    patch -p1 < /path/to/patchfile


#### Usage for the full source tree driver patch

This patch can be applied by navigating to the Cinder project source root directory and running:

    patch -p0 < /path/to/patchfile
