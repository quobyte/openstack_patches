## encry_param_fix

This patch fixes the Cinder bug
[2042102](https://bugs.launchpad.net/cinder/+bug/2042102) with patch
[899706](https://review.opendev.org/#/c/899706/), fixing a regression
introduced in the remotefs driver.

Please note that this patch is valid for all releases from Victoria to Bobcat.

This patch applies to stripped packaged installations as well as full source
tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory.
For stripped packaged installations please run:

    patch -p2 < /path/to/patchfile

For full source tree installations please run:

    patch -p1 < /path/to/patchfile
