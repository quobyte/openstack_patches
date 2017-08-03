
## Full Quobyte patch (Work in progress)


When complete these patches contain all relevant fixes and changes for the given OpenStack releases and projects. By applying this patch no other patches from this repository need to be applied to an installation. The fixed & improved issues currently patched are:

- Cinder
    - Fixes bug [1685277](https://bugs.launchpad.net/cinder/+bug/1685277) with patch [458885](https://review.openstack.org/#/c/458885/) in order to enable the usage of the Cinder Generic Volume Cache with the Quobyte driver (_this fix is only applied for the Ocata release_).
    - Fixes bug [1674611](https://bugs.launchpad.net/cinder/+bug/1674611) with patch [447958](https://review.openstack.org/#/c/447958/), thus allowing e.g. cloned backups of Quobyte Cinder volumes.
    - Fixes bug [1675710](https://bugs.launchpad.net/cinder/+bug/1675710) with patch [449553](https://review.openstack.org/#/c/449553/) in order to allow specifying multiple Quobyte registries in the quobyte_volume_url Cinder configuration option.
    - Fixes bug [1687048](https://bugs.launchpad.net/cinder/+bug/1687048) with patch [461471](https://review.openstack.org/#/c/461471/)
    - Removes the requirement to support extended attributes from Cinder mounts with patch [427833](https://review.openstack.org/#/c/427833/) for improved performance

- Nova
    - Fixes bug [1530860](https://bugs.launchpad.net/nova/+bug/1530860) with patch [432344](https://review.openstack.org/#/c/432344/) in order to prevent systemd service restarts from unmounting Nova mounts
    - Fixes bug [1679976](https://bugs.launchpad.net/nova/+bug/1679976) with patch [453537](https://review.openstack.org/#/c/453537/) disallowing a specific and potentially bad exit code during volume mounts
    - Removes the requirement to support extended attributes from Nova mounts with patch [428646](https://review.openstack.org/#/c/428646/) for improved performance
    - Exchanges Nova fallocate on qcow2 ephemeral images with a truncate command for improved performance with Quobyte


### Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p0 < /path/to/patchfile
