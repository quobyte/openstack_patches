# Quobyte OpenStack Patches

This project provides patches for Quobyte drivers in the different OpenStack
projects.

## Where is What

Patches in this project are ordered by OpenStack releases. For example a
specific patch  version for the Mitaka release can be found at:

    <patch-dir>/Mitaka


## Usage

These patches can be applied by navigating to the project to be patched root
directory and running the linux patch utility, e.g.:

    patch -p1 < /path/to/patchfile

Please see the different patches readme files for their respective installation
commands.

# Contents


## encry_param_fix

Fixes a Cinder [parameter bug](https://bugs.launchpad.net/cinder/+bug/2042102)
currently in [review](https://review.opendev.org/c/openstack/cinder/+/899706).

## image_to_volume_fix

Fixes a Cinder
[file format handling bug](https://bugs.launchpad.net/cinder/+bug/2069597)
currently in [review](https://review.opendev.org/c/openstack/cinder/+/922082).

## multiattach

Allows activating Cinder multi attach with the Quobyte driver.

# Attic

## Outdated Patches

The following patches are still available but outdated.

### Full Quobyte Patch

These patches provides an all in one patch file per project for easier
installation. These patch files correct a list of issues/features, including
single issue fix patches availabe in this repository.


### overlay_volumes (**beta**)

Backport of the upstream changes for [overlay
volumes](https://review.openstack.org/#/c/507050), the
[volume_from_snapshot_cache](https://review.openstack.org/#/c/502974/9) and
some [general volume creation
optimizations](https://review.openstack.org/#/c/500782/) for Cinder.

### qemu-img_commit_patch
A simple Cinder patch for setups encountering qemu-img commit crashes during
snapshot deletion with v3 Kernels.

### return_for_create_clone

Small patch that enables volume backups via volume cloning with Quobyte
volumes. This change is part of the upstream code for releases Pike and newer.

### systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a
[bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be
removed when the Nova service was stopped or restarted.
This patch is part of the upstream code fore releases Pike and newer.

### user_current_vol-url

Patches the Cinder Quobyte driver to always use the currently configured
quobyte_volume_url.

### xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the
Nova driver and mount Quobyte volumes without xattr support, in order to
improve iops.
This patch is part of the upstream code fore releases Pike and newer.


## Removed Patches

This contains a list of older patches that where removed and are no longer
available.

- truncate-ephemeral_patch: Removed due to possible stability issues
- nova_mitaka_external-mount_patch: Superseeded by the systemd-cgroup_patch (see above)
