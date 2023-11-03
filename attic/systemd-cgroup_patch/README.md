
## systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a [bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be removed when the Nova service was stopped or restarted.

This patch is part of the upstream code fore releases Pike and newer.

The patch comes in two versions:

1. _systemd-run_Nova-Mitaka.patch_ - The pure driver patch for patching package based installations that strip tests and other development elements
2. _systemd-run_Nova-Mitaka_full_source_tree.patch_ - The full source patch including updates of unit tests and release notes files

__Important__: Installations that applied the previous [Nova Mitaka external mount patch](https://github.com/quobyte/nova_mitaka_external-mount_patch) for this issue have to remove this previous patch before applying the systemd-cgroup_patch!
Removal can easily be done via:

    patch -p1 -R < /path/to/patchfile


### Installation

The patch usage is slightly different for both versions (pure driver vs. full source patch). The difference resides in the -p parameter for the patch command and is applied as follows:

#### Usage for the pure driver patch

This patch can be applied by navigating to the Nova project package root directory and running:

    patch -p1 < /path/to/systemd-run_Nova-Mitaka.patch


#### Usage for the full source tree driver patch

This patch can be applied by navigating to the Nova project source root directory and running:

    patch -p0 < /path/to/systemd-run_Nova-Mitaka_full_source_tree.patch


### Changelog


#### 1.0
	- mounts no longer as root but as Nova service user

#### original release
