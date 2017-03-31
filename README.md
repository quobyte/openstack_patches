# Quobyte OpenStack Patches

This project provides patches for Quobyte drivers in the different OpenStack projects.

## Where is What

Patches in this project are ordered by OpenStack releases. For example a specific patch  version for the Mitaka release can be found at:

    <patch-dir>/Mitaka


## Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p1 < /path/to/patchfile

# Contents

## systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a [bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be removed when the Nova service was stopped or restarted.

__Important__: Installations that applied the previous [Nova Mitaka external mount patch](https://github.com/quobyte/nova_mitaka_external-mount_patch) for this issue have to remove this previous patch before applying the systemd-cgroup_patch!
Removal can easily be done via:

    patch -p1 -R < /path/to/patchfile

## xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the Nova driver and mount Quobyte volumes without xattr support, in order to improve iops. This patch comes in two flavors:

* xattr-removal_mitaka-nova_plain-diff.patch: patches xattr out of the vanilla release code
* xattr-removal_mitaka-nova_upon-systemd-run-patch.patch: patches xattr out of code that has previously been patched with the systemd-cgroup patch from this repository
