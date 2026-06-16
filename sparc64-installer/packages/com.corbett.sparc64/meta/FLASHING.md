# Deployment Instructions - SPARC64 Linux Kernel
## Corbett SPARC64 Linux Kernel Build

---

## REQUIREMENTS

- SPARC64 compatible hardware OR QEMU with SPARC64 support
- OpenBoot PROM (OBP) firmware for real hardware
- Serial console access for real hardware

---

## WARNING

Deploying incorrect kernel images can render systems unbootable.
Verify all commands before executing.
The builder assumes NO responsibility for damaged systems.

---

## RUNNING IN QEMU (Easiest Method)

Install QEMU with SPARC64 support:
sudo apt install qemu-system-sparc

Boot the kernel:
qemu-system-sparc64 -machine sun4u -kernel zImage -nographic -m 512M

---

## DEPLOYING TO REAL SPARC64 HARDWARE

### Serial Console Setup
Connect to the system serial port:
- Baud: 9600 (OBP default) or 115200
- Data bits: 8, Stop bits: 1, Parity: None

### OpenBoot PROM Boot
At the OBP prompt:
ok boot disk kernel/zImage

Or network boot via TFTP:
ok boot net zImage

### Copying Kernel to Disk
Mount your boot partition and copy:
sudo mount /dev/sdaX /mnt/boot

sudo cp zImage /mnt/boot/kernel/

sudo umount /mnt/boot

sync

---

## QEMU MACHINE TYPES

Supported QEMU SPARC64 machine types:
- sun4u — UltraSPARC IIi (recommended)
- sun4v — UltraSPARC T1/T2

---

## KNOWN ISSUES

- SPARC64 is a legacy architecture with limited active development
- Some drivers may not be fully functional
- Hardware support depends on specific SPARC64 system variant
- Real hardware deployment requires matching rootfs

---

## ADDITIONAL RESOURCES

- SPARC Linux: https://www.sparc.org
- QEMU SPARC docs: https://wiki.qemu.org/Documentation/Platforms/SPARC
- Project page: https://sourceforge.net/projects/corbett-kernel-builds

---

*Deployment instructions by Corbett - June 2026*
