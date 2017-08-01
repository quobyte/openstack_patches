
## xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the Nova driver and mount Quobyte volumes without xattr support, in order to improve iops. This patch comes in two flavors:

* xattr-removal_mitaka-nova_plain-diff.patch: patches xattr out of the vanilla release code
* xattr-removal_mitaka-nova_upon-systemd-run-patch.patch: patches xattr out of code that has previously been patched with the systemd-cgroup patch from this repository

### Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p1 < /path/to/patchfile
