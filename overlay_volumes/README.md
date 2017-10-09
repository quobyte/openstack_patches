
## overlay_volumes patch (**beta**)

This patch adds optional overlay volumes based on the cache for volumes generated from snapshots in the Quobyte Cinder driver, which speeds up the creation of volumes from large snapshots.
The corresponding [upstream change](https://review.openstack.org/#/c/507050/9) is still in review which is why this patch is currently in **beta** state and subject to possible changes. Please note that this patch also includes a range of several [volume creation performance improvements](https://review.openstack.org/#/c/500782/7) and the [volume from snapshot cache](https://review.openstack.org/#/c/502974/9), who this implementation depends upon.


### Usage

This patch can be applied by navigating to the Nova project root directory and running:

    patch -p0 < /path/to/patchfile

The new cache can be activated by adding the config lines:

    quobyte_volume_from_snapshot_cache = True
    quobyte_overlay_volumes = True

to your cinder.conf Quobyte backend section(s).