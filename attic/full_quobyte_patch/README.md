
## Full Quobyte Patches (Continuous Work in Progress)

These patches are continuosly evolving and contain all relevant fixes and changes for the given OpenStack releases and projects. By applying these patches no other patches from this repository need to be applied to an installation. The fixed & improved issues currently patched are
listed for each release.

In case you are using a missing release please contact the Quobyte support and we'll provide the required patches in this repository.

### Installation

#### Usage for the pure driver patches

These patches can be applied by navigating to the respective project package root directory and running:

    patch -p1 < /path/to/patchfile

For __example__, to patch a cinder installation based on a stripped package run:

    cd /usr/lib/python2.7/site-packages/cinder/
    patch -p1 < /path/to/full_quobyte_ocata_cinder.patch

#### Usage for the full source tree driver patches

These patches can be applied by navigating to the respective project source root directory and running for Cinder:

    patch -p0 < /path/to/patchfile

And for Nova and Manila:

    patch -p1 < /path/to/patchfile

#### Usage for the driver files

Alongside the patch files we also provide the fully patched driver files in newer releases. These can simply be copied into the existing driver file locations.

### Changelog

#### 0.6 (2018-09-11)
    - Adds Pike release patches
    - Moves release based patch information into separate Readme.md files per release

#### 0.5 (2018-06-29)
    - Updates Manila patches for fixing a share resizing and a code style issue

#### 0.4 (2018-05-28)
    - Adds Manila patches

#### 0.3 (2018-05-08)
    - Fixed a regression that reintroduced superfluous truncate operations in Nova

#### 0.2 (2018-04-13)
    - Updated systemd based mount handling

#### 0.1 
    - Original release