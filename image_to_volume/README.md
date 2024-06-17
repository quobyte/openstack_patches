## encry_param_fix

This patch fixes the Cinder bug
[2069597](https://bugs.launchpad.net/cinder/+bug/2069597) with patch
[922082](https://review.opendev.org/c/openstack/cinder/+/922082), adding
handling for different image file formats during copy_image_to_volume
operations in the Quobyte driver.

Please note that this patch is valid for all releases from Antelope to Caracal.

This patch applies to stripped packaged installations as well as full source
tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory.
For stripped packaged installations please run:

    patch -p2 < /path/to/patchfile

For full source tree installations please run:

    patch -p1 < /path/to/patchfile
