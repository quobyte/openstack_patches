
## return_for_create_clone patch

This patch fixes the Cinder bug [1674611](https://bugs.launchpad.net/cinder/+bug/1674611) with patch [447958](https://review.openstack.org/#/c/447958/), thus allowing e.g. cloned backups of Quobyte Cinder volumes.

### Usage

This patch can be applied by navigating to the Nova project root directory and running:

    patch -p0 < /path/to/patchfile
