
## truncate-ephemeral_patch

This patch changes Nova ephemeral image prealloc behaviour by running truncate instead of fallocate. This improves performance with ephemeral images on Quobyte volumes.
This change may have a possible performance impact on other backends.

### Usage

This patch can be applied by navigating to the Nova project root directory and running:

    patch -p0 < /path/to/patchfile
