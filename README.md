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

Installs a live FreeBSD RK3588 system to a selected MMC target while always
excluding the running system disk. For an MMC target, the user independently
chooses whether to write the bundled U-Boot image; the current SD, eMMC, or
SPI boot source does not make that decision. The installer always reserves
the Rockchip firmware area, creates the EFI system partition, and installs
either a UFS or ZFS root filesystem with optional swap.

The installer only runs when `/chosen/rockchip,boot-storage` reports eMMC
(`1`), SD (`2`), or SPI NOR (`9`). This verifies that the system was started
by the supported RK3588 U-Boot; it does not control the U-Boot write choice.

It also installs the board DTB, EFI loader, and U-Boot menu needed to boot the
installed system and enables `powerd` for RK3588 DVFS.

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

Repository-authored content is licensed under the BSD 2-Clause License; see
`LICENSE`. Each port also follows the license declared in its `Makefile`.
Third-party and upstream files retain their original copyright and license
notices and are not relicensed by this repository.
