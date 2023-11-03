
## return_for_create_clone patch

This patch fixes the Cinder bug [1674611](https://bugs.launchpad.net/cinder/+bug/1674611) with patch [447958](https://review.openstack.org/#/c/447958/), thus allowing e.g. cloned backups of Quobyte Cinder volumes.
This patch is part of the upstream code fore releases Pike and newer.

This patch applies to stripped packaged installations as well as full source tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory. For stripped packaged installations please run:

    patch -p1 < /path/to/patchfile

For full source tree installations please run:

    patch -p0 < /path/to/patchfile
