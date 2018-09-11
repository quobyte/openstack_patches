## Pike Release
Fixes the following issues:

- Manila
    - Fixes bug [1774604](https://bugs.launchpad.net/manila/+bug/1774604) with patch [571693](https://review.openstack.org/#/c/571693/) to avoid incoherent volume specification in resizing.
    - Fixes bug [1773929](https://bugs.launchpad.net/manila/+bug/1773929) with patch [572291](https://review.openstack.org/#/c/572291/) to fix a coding style issue.

- Nova
    - Fixes bug [1756823](https://bugs.launchpad.net/nova/+bug/1756823) with a backported variant of patch [554195](https://review.openstack.org/#/c/554195/) in order to prevent systemd service restarts from unmounting Nova mounts
    - NOTE: Please add the following config to */etc/nova/rootwrap.d/compute.filters* when using the patched Nova setup:
        

        ```
        # nova/virt/libvirt/volume/quobyte.py
        systemd-run: CommandFilter, systemd-run, root
        ```


The patches come in three versions, the driver only patch, the full source patch and the full driver file.
