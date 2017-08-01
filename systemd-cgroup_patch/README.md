
## systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a [bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be removed when the Nova service was stopped or restarted.

__Important__: Installations that applied the previous [Nova Mitaka external mount patch](https://github.com/quobyte/nova_mitaka_external-mount_patch) for this issue have to remove this previous patch before applying the systemd-cgroup_patch!
Removal can easily be done via:

    patch -p1 -R < /path/to/patchfile

### Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p1 < /path/to/patchfile
