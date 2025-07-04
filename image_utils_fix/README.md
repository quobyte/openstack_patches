## image_utils_fix

This patch fixes the Cinder bug
[2074377](https://bugs.launchpad.net/cinder/+bug/2074377) for the Quobyte driver
and is based on an upstream bugfix to image_utils. This bugfix has been backported
to releases as old as 2023.2 .

An earlier version of this patch did fixing by patching
the missing parameter into the required image_utils methods. This older versioni
is still available for relases prior to 2023.2 (Bobcat).

This patch applies to stripped packaged installations as well as full source
tree installations. Slightly different patch commands are used (see below).

### Usage

This patch can be applied by navigating to the Cinder project root directory.
For stripped packaged installations please run:

    patch -p2 < /path/to/patchfile

For full source tree installations please run:

    patch -p1 < /path/to/patchfile
