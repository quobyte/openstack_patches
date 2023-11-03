
## use_current_vol-url patch

This patch fixes the Cinder bug [1828993](https://bugs.launchpad.net/cinder/+bug/1828993) with patch [659265](https://review.opendev.org/#/c/659265/), thus ensuring always the currently configured quobyte_volume_url
is used in the Cinder Quobyte driver.

This patch applies to stripped packaged installations as well as full source tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory. For stripped packaged installations please run:

    patch -p2 < /path/to/patchfile

For full source tree installations please run:

    patch -p1 < /path/to/patchfile
