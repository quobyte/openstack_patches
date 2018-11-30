
## qemu-img_commit_patch for old v3 kernels

Backports a very simple patch for Cinder setups that use qemu-img version 2.10+ with v3.10 Kernels. In case a setup hits issues with qemu-img crashing in a qemu-img commit call during snapshot deletion this patch provides a simple fix.
The patch has been added upstream with [change #6200926](https://review.openstack.org/#/c/620926/) and will be ported back to the previous three releases. Older releases are provided with this patch via this repository.


### Installation

This patch can be applied by navigating to the Cinder project source root directory and running:

    patch -p1 < /path/to/patchfile
