
## xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the Nova driver and mount Quobyte volumes without xattr support, in order to improve iops. This patch comes in two flavors, one for patching the plain vanilla release code and one for patching installations that have previously applied the systemd-cgroup patch from this repository.

Both flavors come in two versions, the vanilla release :

1. _xattr-removal_Nova-RELEASENAME.patch_ - The pure driver patch for patching package based installations that strip tests and other development elements
2. _xattr-removal_RELEASENAME-Mitaka_full_source_tree.patch_ - The full source patch including updates of unit tests and release notes files

And the _upon-systemd-run-patch_ versions:

1. _xattr-removal_Nova-RELEASENAME_upon-systemd-run-patch.patch_ - The pure driver patch for patching package based installations that strip tests and other development elements
2. _xattr-removal_RELEASENAME-Mitaka_upon-systemd-run-patch_full_source_tree.patch_ - The full source patch including updates of unit tests and release notes files


### Installation

The patch usage is slightly different for both versions (pure driver vs. full source patch). The difference resides in the -p parameter for the patch command and is applied as follows:

#### Usage for the pure driver patch

This patch can be applied by navigating to the Nova project package root directory and running:

    patch -p2 < /path/to/patchfile


#### Usage for the full source tree driver patch

This patch can be applied by navigating to the Nova project source root directory and running:

    patch -p1 < /path/to/patchfile


### Configuration

Some older releases may have incomplete Nova rootwrap configurations. This can be checked by looking for the following entries in the Nova rootwrap configuration file _compute.filters_ :

    # nova/virt/libvirt/volume/quobyte.py
    mount.quobyte: CommandFilter, mount.quobyte, root
    umount.quobyte: CommandFilter, umount.quobyte, root

If the entries are not present you can copy & paste from here.

The exact location of the _compute.filters_ file is set in _/etc/nova/rootwrap.conf_ .
