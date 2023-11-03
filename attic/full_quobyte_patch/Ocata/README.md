## Ocata Release
Fixes the following issues:

- Cinder
    - Fixes bug [1685277](https://bugs.launchpad.net/cinder/+bug/1685277) with patch [458885](https://review.openstack.org/#/c/458885/) in order to enable the usage of the Cinder Generic Volume Cache with the Quobyte driver (_this fix is only applied for the Ocata release_).
    - Fixes bug [1674611](https://bugs.launchpad.net/cinder/+bug/1674611) with patch [447958](https://review.openstack.org/#/c/447958/), thus allowing e.g. cloned backups of Quobyte Cinder volumes.
    - Fixes bug [1675710](https://bugs.launchpad.net/cinder/+bug/1675710) with patch [449553](https://review.openstack.org/#/c/449553/) in order to allow specifying multiple Quobyte registries in the quobyte_volume_url Cinder configuration option.
    - Fixes bug [1687048](https://bugs.launchpad.net/cinder/+bug/1687048) with patch [461471](https://review.openstack.org/#/c/461471/)
    - Removes the requirement to support extended attributes from Cinder mounts with patch [427833](https://review.openstack.org/#/c/427833/) for improved performance

- Manila
    - Fixes bug [1733807](https://bugs.launchpad.net/manila/+bug/1733807) with patch [570741](https://review.openstack.org/#/c/570741) for improved API compatibility.
    - Fixes bug [1771958](https://bugs.launchpad.net/manila/+bug/1771958) with patch [569355](https://review.openstack.org/#/c/569355/) to fix initial quota creation.
    - Fixes bug [1771970](https://bugs.launchpad.net/manila/+bug/1771970) with patch [569355](https://review.openstack.org/#/c/569355/) to correct the quota when resizing a Manila share.
    - Fixes bug [1774604](https://bugs.launchpad.net/manila/+bug/1774604) with patch [571693](https://review.openstack.org/#/c/571693/) to avoid incoherent volume specification in resizing.
    - Fixes bug [1773929](https://bugs.launchpad.net/manila/+bug/1773929) with patch [572291](https://review.openstack.org/#/c/572291/) to fix a coding style issue.

- Nova
    - Fixes bug [1530860](https://bugs.launchpad.net/nova/+bug/1530860) with patch [432344](https://review.openstack.org/#/c/432344/) and bug [1756823](https://bugs.launchpad.net/nova/+bug/1756823) with patch [554195](https://review.openstack.org/#/c/554195/) in order to prevent systemd service restarts from unmounting Nova mounts
    - Fixes bug [1679976](https://bugs.launchpad.net/nova/+bug/1679976) with patch [453537](https://review.openstack.org/#/c/453537/) disallowing a specific and potentially bad exit code during volume mounts
    - Removes the requirement to support extended attributes from Nova mounts with patch [428646](https://review.openstack.org/#/c/428646/) for improved performance

The patches come in two versions, the driver only and the full source patch.
