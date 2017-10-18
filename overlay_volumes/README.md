
## overlay_volumes patch (**beta**)

This patch adds optional overlay volumes based on the cache for volumes generated from snapshots in the Quobyte Cinder driver, which speeds up the creation of volumes from large snapshots.
The corresponding [upstream change](https://review.openstack.org/#/c/507050/12) is still in review which is why this patch is currently in **beta** state and subject to possible changes. Please note that this patch also includes a range of several [volume creation performance improvements](https://review.openstack.org/#/c/500782/9) and the [volume from snapshot cache](https://review.openstack.org/#/c/502974/11), who this implementation depends upon.

The patch comes in two versions:

1. _overlay_volumes_Cinder-Pike.patch_ - The pure driver patch for patching package based installations that strip tests and other development elements
2. _overlay_volumes_Cinder-Pike_full_source_tree.patch_ - The full source patch including updates of unit tests and release notes files


### Installation

The patch usage is slightly different for both versions (pure driver vs. full source patch). The difference resides in the -p parameter for the patch command and is applied as follows:

#### Usage for the pure driver patch

This patch can be applied by navigating to the Cinder project package root directory and running:

    patch -p1 < /path/to/overlay_volumes_Cinder-Pike.patch


#### Usage for the full source driver patch

This patch can be applied by navigating to the Cinder project source root directory and running:

    patch -p0 < /path/to/overlay_volumes_Cinder-Pike_full_source_tree.patch


### Configuration

The new cache and overlay volumes can be activated by adding the config lines:

    quobyte_volume_from_snapshot_cache = True
    quobyte_overlay_volumes = True

to your cinder.conf Quobyte backend section(s).

By activating only the _quobyte_volume_from_snapshot_cache_ option but not the _quobyte_overlay_volumes option_, an intermediate optimization level can be set. In this case the volume from snapshot cache is used to store merged backing chains which prevents a merge for every new volume. New volumes are created as full copies from the cached volume, thought, and no overlay volumes are used.
