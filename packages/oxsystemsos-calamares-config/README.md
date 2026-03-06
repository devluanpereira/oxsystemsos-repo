# oxsystemsos-calamares-config

This package carries all Calamares runtime configuration for OXSystemsOS:

- `/etc/calamares/settings.conf`
- `/etc/calamares/modules/bootloader.conf`
- `/etc/calamares/modules/prepare-target.conf`
- `/etc/calamares/modules/cleanup-target.conf`
- `/etc/calamares/modules/services-systemd.conf`
- `/etc/calamares/modules/unpackfsc.conf`
- `/usr/local/lib/oxsystemsos/prepare-installed-target`
- `/usr/local/lib/oxsystemsos/cleanup-installed-target`
- `/etc/calamares/branding/oxsystemsos/*`

Keeping this package in the pacman repository decouples installer branding/config
from the ISO source tree.
