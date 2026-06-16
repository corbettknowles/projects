# Flashing Instructions - Microchip PolarFire SoC MPFS Icicle Kit
## Corbett Hardened RISC-V 64 Linux Kernel Build

---

## REQUIREMENTS

- Microchip PolarFire SoC MPFS Icicle Kit
- MicroSD card (minimum 4GB, Class 10 recommended)
- USB to UART serial adapter (3.3V)
- Terminal emulator (minicom, PuTTY, screen)
- Existing U-Boot installation on the board
- Linux or Windows with WSL2 host machine

---

## WARNING

Flashing incorrect images can render your board unbootable.
Verify all device paths before running any commands.
The builder assumes NO responsibility for bricked hardware.

---

## SERIAL CONSOLE SETUP

Connect to J11 on the Icicle Kit:
- Baud: 115200
- Data bits: 8
- Stop bits: 1
- Parity: None
- Flow control: None

Linux:
sudo minicom -D /dev/ttyUSB0 -b 115200

Windows PuTTY:
- Serial, COM port from Device Manager, Speed 115200

---

## COPYING KERNEL TO SD CARD

Mount your SD card boot partition and copy files:
sudo mount /dev/sdX1 /mnt/boot

sudo cp Image.gz /mnt/boot/

sudo cp mpfs-icicle-kit.dtb /mnt/boot/

sudo cp mpfs-icicle-kit-prod.dtb /mnt/boot/

sudo umount /mnt/boot

sync

---

## U-BOOT CONFIGURATION

At the U-Boot prompt configure boot:
setenv bootargs "root=/dev/mmcblk0p2 rw console=ttyS0,115200"

setenv bootcmd "load mmc 0:1 ${kernel_addr_r} Image.gz; load mmc 0:1 ${fdt_addr_r} mpfs-icicle-kit.dtb; booti ${kernel_addr_r} - ${fdt_addr_r}"

saveenv

boot

---

## PRODUCTION DEVICE TREE

For production use swap to the production DTB:
setenv bootcmd "load mmc 0:1 ${kernel_addr_r} Image.gz; load mmc 0:1 ${fdt_addr_r} mpfs-icicle-kit-prod.dtb; booti ${kernel_addr_r} - ${fdt_addr_r}"

saveenv

---

## HARDENING NOTES

This kernel has security hardening enabled. Some implications:

- KASLR enabled — kernel base address randomized each boot
- Hardened usercopy — stricter kernel/userspace memory boundaries
- Stack protector — may catch stack corruption attempts
- Strict RWX — kernel memory permissions enforced

These features may cause issues with out-of-tree modules or
poorly written drivers. If you experience unexpected panics,
check dmesg for hardening-related messages.

---

## RECOVERY

If board fails to boot:
1. Check serial console for kernel panic messages
2. At U-Boot prompt, try booting previous kernel
3. Reflash SD card with known-good image
4. Check U-Boot environment variables are correct

---

## ADDITIONAL RESOURCES

- PolarFire SoC documentation: https://www.microchip.com/en-us/development-tool/mpfs-icicle-kit
- Linux RISC-V: https://github.com/riscv/riscv-linux
- Project page: https://sourceforge.net/projects/corbett-kernel-builds

---

*Flashing instructions by Corbett - June 2026*
EOF
