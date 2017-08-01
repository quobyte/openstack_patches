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

## systemd-cgroup_patch

Backport of a [Nova bugfix](https://review.openstack.org/#/c/432344/) for a [bug](https://bugs.launchpad.net/nova/+bug/1530860) that caused mounts to be removed when the Nova service was stopped or restarted.

## truncate-ephemeral_patch

This patch changes Nova ephemeral image prealloc behaviour by running truncate instead of fallocate. This improves performance with ephemeral images on Quobyte volumes.
This change is compatible with other backends with a possible performance impact.

## xattr-removal_patch

Backports of performance optimizations that remove the usage of xattr from the Nova driver and mount Quobyte volumes without xattr support, in order to improve iops. 