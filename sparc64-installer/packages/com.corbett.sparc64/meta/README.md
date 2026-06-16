Corbett SPARC64 Linux Kernel Build v6.10.7
==========================================
Builder: Corbett
Build Date: June 17, 2026
Project: https://sourceforge.net/projects/corbett-kernel-builds

WHAT IS THIS:
Mainline Linux kernel build targeting the SPARC64 architecture.
Built from Linux mainline kernel source using a cross-compiler
targeting sparc64-linux-gnu.

ARCHITECTURE:
- Architecture: SPARC64 (64-bit SPARC)
- Originally developed by Sun Microsystems
- Used in Sun/Oracle SPARC enterprise servers
- Still deployed in enterprise environments worldwide

KERNEL VERSION: Linux 6.10.7

INCLUDED FILES:
- image — Uncompressed SPARC64 kernel image
- zImage — Compressed SPARC64 kernel image

TARGET HARDWARE:
- Sun UltraSPARC workstations and servers
- Oracle SPARC servers
- SPARC64 compatible systems
- QEMU SPARC64 virtual machines (sun4u machine type)

RUNNING IN QEMU:
qemu-system-sparc64 -machine sun4u -kernel zImage -nographic

EXPERIMENTAL WARNING:
This is an experimental community build. Not intended for
production use. Use at your own risk.

SUPPORT:
No official support provided.
Project: https://sourceforge.net/projects/corbett-kernel-builds