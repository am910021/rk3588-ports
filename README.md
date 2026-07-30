# FreeBSD Ports for RK3588

This repository contains FreeBSD ports maintained for RK3588 systems.

## Ports

### `net/realtek-rge-kmod`

Packages `if_rge.ko` and its manual page for Realtek RTL8125, RTL8126, and
RTL8127 PCI Express Ethernet controllers. The driver is Adrian Chadd's
FreeBSD port of the OpenBSD `rge` driver, with updates validated on the
NanoPC-T6 LTS. It provides the community-style alternative to Realtek's
vendor driver.

### `sysutils/rk3588-installer`

Installs a live FreeBSD RK3588 system from SD card to eMMC, or from eMMC to
SD card, without overwriting the running media. It creates the required GPT
layout, reserves space for Rockchip firmware, creates the EFI system
partition, and installs either a UFS or ZFS root filesystem with optional
swap.

The installer detects SPI boot through `/chosen/rockchip,boot-storage`. When
booting from SPI, it preserves the target firmware area instead of writing a
second U-Boot image. It also installs the board DTB, EFI loader, and U-Boot
menu needed to boot the installed system.

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
