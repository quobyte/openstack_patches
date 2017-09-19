
## volume_from_snapshot_cache patch (**beta**)

This patch adds an optional cache for volumes generated from snapshots in the Quobyte Cinder driver.
This significantly speeds up the generation of multiple volumes from the same snapshot.
The corresponding [upstream change](https://review.openstack.org/#/c/502974/9) is still in review which is why this patch is currently in **beta** state and subject to possible changes. Please note that this patch also includes a range of several [volume creation performance improvements](https://review.openstack.org/#/c/500782/7) which the cache implementation depends upon.

### Usage

This patch can be applied by navigating to the Nova project root directory and running:

    patch -p0 < /path/to/patchfile

The new cache can be activated by adding the config line:

    quobyte_volume_from_snapshot_cache = True

to your cinder.conf Quobyte backend section(s).