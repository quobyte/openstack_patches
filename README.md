# Quobyte OpenStack Patches

This project provides patches for Quobyte drivers in the different OpenStack projects.

## Where is What

Patches in this project are ordered by OpenStack release. A specific patch  version for the Mitaka release can be found at:

    <patch-dir>/Mitaka


## Usage

These patches can be applied by navigating to the project to be patched root directory and running:

    patch -p1 < /path/to/patchfile

# Contents

- systemd-cgroup_patch: backports of a [https://review.openstack.org/#/c/432344/ Nova bugfix] for a [https://bugs.launchpad.net/nova/+bug/1530860 bug] that caused mounts to be removed when the Nova service was stopped or restarted.