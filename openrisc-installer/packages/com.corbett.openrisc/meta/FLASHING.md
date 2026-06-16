# Deployment Instructions - OpenRISC Linux Kernel
## Corbett OpenRISC Linux Kernel Build

---

## REQUIREMENTS

- QEMU with OpenRISC support OR or1ksim simulator
- OR DE0-Nano FPGA board with OpenRISC core

---

## WARNING

The builder assumes NO responsibility for damaged hardware.
Verify all commands before executing.

---

## RUNNING IN QEMU (Recommended)

Install QEMU:
sudo apt install qemu-system-misc

Boot the kernel:
qemu-system-or1k -kernel vmlinux -nographic -m 256M

---

## RUNNING IN OR1KSIM

Install or1ksim:
sudo apt install or1ksim

Run:
or1ksim vmlinux

---

## DE0-NANO FPGA DEPLOYMENT

For DE0-Nano board deployment you will need:
- Quartus Prime (free lite version)
- OpenRISC core for Cyclone IV FPGA
- JTAG cable for programming

1. Synthesize OpenRISC core into DE0-Nano FPGA
2. Connect JTAG programmer
3. Load vmlinux via JTAG:
   or1k-jtag -f vmlinux

---

## KNOWN ISSUES

- OpenRISC is a 32-bit architecture with limited hardware availability
- Most testing done in simulation via QEMU or or1ksim
- Some kernel features may not be fully functional on real hardware
- Network and storage drivers depend on specific FPGA peripheral config

---

## ADDITIONAL RESOURCES

- OpenRISC project: https://openrisc.io
- QEMU OpenRISC: https://wiki.qemu.org
- Project page: https://sourceforge.net/projects/corbett-kernel-builds

---

*Deployment instructions by Corbett - June 2026*