Corbett Hardened RISC-V 64 Linux Kernel Build v6.10.7
======================================================
Builder: Corbett
Build Date: June 15, 2026
Project: https://sourceforge.net/projects/corbett-kernel-builds

WHAT IS THIS:
This is an experimental hardened mainline Linux kernel build targeting
the Microchip PolarFire SoC MPFS Icicle Kit RISC-V 64 development board.
Built directly from the Linux mainline kernel tree with security hardening
options enabled.

TARGET HARDWARE:
- Board: Microchip PolarFire SoC MPFS Icicle Kit
- Architecture: RISC-V 64-bit (RV64GC)
- CPU: SiFive U54 quad-core + E51 monitor core
- RAM: 2GB LPDDR4

KERNEL VERSION: Linux 6.10.7

HARDENING FEATURES ENABLED:
- Stack Protector Strong (CONFIG_STACKPROTECTOR_STRONG)
- Hardened Usercopy (CONFIG_HARDENED_USERCOPY)
- Kernel Address Space Layout Randomization (KASLR)
- Strict Kernel RWX (CONFIG_STRICT_KERNEL_RWX)
- Linux Security Module framework
- Read-only kernel data sections
- CAN bus support (automotive networking)
- Netfilter/iptables security framework

INCLUDED FILES:
- Image.gz — Compressed kernel image
- mpfs-icicle-kit.dtb — Device tree blob (development)
- mpfs-icicle-kit-prod.dtb — Device tree blob (production)

REQUIREMENTS:
- Microchip PolarFire SoC MPFS Icicle Kit
- U-Boot bootloader (v2024.04 or later recommended)
- SD card or eMMC (minimum 1GB)
- Serial console access (J11, 115200 baud)

EXPERIMENTAL WARNING:
This is an experimental hardened kernel build. Not intended for
production use without thorough testing on your specific hardware
and use case. Use at your own risk.

HOW TO DEPLOY:
See FLASHING.md for complete flashing and deployment instructions.

SUPPORT:
No official support provided. Community discussion welcome on the
SourceForge project page.
