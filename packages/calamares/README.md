# calamares (OXSystemsOS build)

Custom Calamares build for OXSystemsOS repository.

Differences from the base AUR package:

- Python modules enabled (`WITH_PYTHON=ON`) so modules like `mount`, `fstab`,
  `localecfg`, `networkcfg`, `bootloader` are available.
- Keeps Arch-style install modules (`initcpio`, `initcpiocfg`, `initramfs`).
- Built as package `calamares` for direct use in OXSystemsOS live ISO.
