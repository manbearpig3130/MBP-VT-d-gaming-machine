# MBP-VT-d-gaming-machine
Configuration files for my OVMF based VT-d gaming machine

Manbearpig3130's Virtual Gaming Machine:
Hardware:
* CPU: Intel Core i7-6850K
* Motherboard: Gigabyte x99-Ultra Gaming-CF (Revision 1.0, BIOS/UEFI Version: F4)
* Host GPU: AMD R9 390
* Guest GPU' NVIDIA 2080TI
* RAM: 32GB G-Skill Ripjaws DDR4 3333MHz
* Guest Storage: 2TB Intel 660P NVMe SSD

Configuration:
* Host Kernel: version Linux 5.3.12.1-1. Having trouble booting VM with newer kernels at the moment.
* Using libvirt QEMU/KVM with OVMF: link to domain XMLs/scripts/notes: https://github.com/manbearpig3130/MBP-VT-d-gaming-machine
* Host OS: Arch Linux
* Guest OS: Windows 10 Pro
* Intel 660P NVMe SSD passed through as a PCI device. This particular SSD chipset (sm2262) needed a firmware update for passthrough to work, so previously I just mounted it in Linux and had the VM disk as a .raw file. Another advantage of direct PCI passthrough is I now have the option of booting into windows directly with all hardware available. 
* USB Host controller is passed through, giving most USB ports to the VM, leaving my USB 3.1 controller with attached USB hub for the host.
* Motherboard has two NICs, one is passed into VM (Works after installing Killer NIC Driver).
* VM gets dedicated 16GB RAM via static hugepages.
* CPU pinning increased performance considerably.
* Windows boots straight into Steam big picture mode on its primary display. 
* Runs Valve Index flawlessly. 2080TI also includes USB-C port which the index is plugged into.
* Setting up IOthreads properly greatly helped with stuttering during high disk usage (steam downloads)
* Intel 9260 M.2 Wifi + Bluetooth card passed through as well so I can connect Xbox series X/S controller

Overall an awesome machine that runs games pretty much flawlessly. Took a while to get configuration to where it is but haven't had any game issues specific to running in a VM.
