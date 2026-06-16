Corbett OpenRISC Linux Kernel Build v6.10.7
============================================
Builder: Corbett
Build Date: June 16, 2026
Project: https://sourceforge.net/projects/corbett-kernel-builds

WHAT IS THIS:
Mainline Linux kernel build targeting the OpenRISC architecture.
Built from Linux mainline kernel source using the or1k-linux
cross-compiler toolchain targeting the or1ksim simulator.

ARCHITECTURE:
- Architecture: OpenRISC (OR1K)
- Fully open source CPU architecture
- 32-bit RISC design
- Developed by the OpenRISC project
- Runs on FPGAs and in simulation via or1ksim/QEMU

KERNEL VERSION: Linux 6.10.7

INCLUDED FILES:
- vmlinux — OpenRISC kernel image

TARGET:
- or1ksim OpenRISC simulator
- QEMU OpenRISC emulation
- DE0-Nano FPGA board (Terasic)
- Any OpenRISC compatible hardware

RUNNING IN QEMU:
Install QEMU with OpenRISC support first then boot with:
qemu-system-or1k -kernel vmlinux -nographic -m 256M

EXPERIMENTAL WARNING:
This is an experimental community build. Not intended for
production use. Use at your own risk.

SUPPORT:
No official support provided.
Project: https://sourceforge.net/projects/corbett-kernel-builds