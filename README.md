# Quobyte OpenStack Patches

This project provides patches for Quobyte drivers in the different OpenStack projects.

## Where is What

Patches in this project are ordered by OpenStack releases. For example a specific patch  version for the Mitaka release can be found at:

    <patch-dir>/Mitaka


## Usage

These patches can be applied by navigating to the project to be patched root directory and running the linux patch utility, e.g.:

    patch -p1 < /path/to/patchfile

Please see the different patches readme files for their respective installation commands.

# Contents

## Full Quobyte Patch

These patches provides an all in one patch file per project for easier installation. These patch files correct a list of issues/features, including single issue fix patches availabe in this repository.

## return_for_create_clone_patch

Small patch that enables volume backups via volume cloning with Quobyte volumes. This change is part of the upstream code for releases Pike and newer.

## systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a [bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be removed when the Nova service was stopped or restarted.
This patch is part of the upstream code fore releases Pike and newer.

## overlay_volume_patch (**beta**)

Backport of the upstream changes for [overlay volumes](https://review.openstack.org/#/c/507050), the [volume_from_snapshot_cache](https://review.openstack.org/#/c/502974/9) and some [general volume creation optimizations](https://review.openstack.org/#/c/500782/) for Cinder.

## xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the Nova driver and mount Quobyte volumes without xattr support, in order to improve iops.
This patch is part of the upstream code fore releases Pike and newer.

# Attic

This contains a list of older patches that where removed.

- truncate-ephemeral_patch: Removed due to possible stability issues
- nova_mitaka_external-mount_patch: Superseeded by the systemd-cgroup_patch (see above)
