# FreeBSD Ports for RK3588

This repository contains FreeBSD ports maintained for RK3588 systems.

## Ports

- `net/realtek-rge-kmod`: Community-style driver for Realtek RTL8125,
  RTL8126, and RTL8127 PCI Express Ethernet controllers.
- `sysutils/rk3588-installer`: Installer for RK3588 systems using U-Boot,
  an EFI system partition, and a UFS or ZFS root filesystem.

The NanoPC-T6 LTS image builder consumes these ports from
`src/ports` and supplies board-specific firmware and DTB payloads to the
installer image.

## Building

Build a port with the normal FreeBSD Ports framework:

```sh
make -C net/realtek-rge-kmod package
make -C sysutils/rk3588-installer package
```

Cross-building `realtek-rge-kmod` requires a matching FreeBSD source and
kernel object tree. The RK3588 image builder configures those paths
automatically.

## License

Each port follows the license declared in its `Makefile`. Bundled upstream
files retain their original copyright and license notices.
