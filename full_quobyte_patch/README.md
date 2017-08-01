
## Full Quobyte patch

These patches contain all relevant fixes and changes for the given OpenStack releases and projects. By applying this patch no other patches from this repository need to be applied to an installation. The fixed & improved issues are:

- Cinder
    - Fixes bug [1685277](https://bugs.launchpad.net/cinder/+bug/1685277) with patch [458885](https://review.openstack.org/#/c/458885/) in order to enable the usage of the Cinder Generic Volume Cache with the Quobyte driver (_this fix is only applied for the Ocata release_).
    - Fixes bug [1674611](https://bugs.launchpad.net/cinder/+bug/1674611) with patch [447958](https://review.openstack.org/#/c/447958/), thus allowing e.g. cloned backups of Quobyte Cinder volumes.
    - Fixes bug [1675710](https://bugs.launchpad.net/cinder/+bug/1675710) with patch [449553](https://review.openstack.org/#/c/449553/) in order to allow specifying multiple Quobyte registries in the quobyte_volume_url Cinder configuration option.
    - Fixes bug [1687048](https://bugs.launchpad.net/cinder/+bug/1687048) with patch [461471](https://review.openstack.org/#/c/461471/)

- Nova

### Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p0 < /path/to/patchfile
