## Lab 07

- Name: Corinna Green
- Email: green.442@wright.edu

## System Discovery

1. CPU info:
    - CPU brand: AMD
    - Number of cores: 6
    - Number of logical cores: 12
2. GPU info:
    - Integrated GPU info: None?
    - Dedicated GPU info: 360/512 MB
    - Link to driver software for GPU: https://www.amd.com/en/support/download/drivers.html
3. Memory info:
    - Physical memory (RAM) size (in GB): 15.3 GB
    - Virtual memory size (in GB): 31.1 GB
4. Storage info (repeat for each disk attached to your system): 
    - Disk 1 type: SDD
    - Disk 1 manufacturer and model: (Standard disk drives) and  SAMSUNG MZVLQ256HBJD-00BH1
    - Total disk 1 size (in GB): 239 GB
5. Primary partition info:
    - Primary partition mount point: C:\
    - Remaining space on primary partition (in GB): 19.2 GB
    - Filesystem on primary partition: NTFS
6. BIOS / UEFI info: 
    - BIOS or UEFI version: UEFI: F.14
    - How to access your BIOS / UEFI: Go to settings and click 'restart' under 'Advanced setup'. Then clikc 'troubleshoot', 'Advanced options', 'UEFI firmware settings', and 'restart'. This restarts the PC into UEFI interface.
7. Kernel / OS info:
    - Bootloader software on your system: Windows Boot Manager
    - Kernel version of your operating system: 10.0.22621.4317
    - Operating System name & version: 'Microsoft Windows 11 Home' and '10.0.22621 Build 22621'

## Part 2 - Virtualize the Machine

1. Virtual Machine Manager:
    - Software & version: VirtualBox Graphical User Interface Version 7.1.4 r165100 (Qt6.5.3)
    - Link to software URL: https://www.virtualbox.org/wiki/Downloads
    - ![screenshot of installed & running software](RELATIVE_PATH_TO_SCREENSHOT_IN_FOLDER)

2. Guest OS information: 
    - Linux distribution selected: Ubuntu
    - URL downloaded from: https://ubuntu.com/download/desktop

3. Guest VM resource allocations:
    - Number of Virtual CPUs: 4
    - RAM: 4096 MB
    - Hard disk space: 45.00 GB

4. Guest OS Installation:
    - Note steps completed to install and then run the guest operating system
    - First download the OS, I chose Ubuntu 24.04.1 LTS. Then when the VB comes up, click on the option that says `new`. You can give it whatever name you want, I named mine `CEG2350`. Find where you want to store the ISO message from `Other`. Click `Skip Unattended Installation`. Assign some hardware for the VM, I gave mine 4 GB of RAM and 4 CPUs. Next, give it some storage, I gave mine 45 GB (minimum requirement is 35 GB). Verify the settings are set up properly and click `Finish`. On the new page, click on the VM you just created, it should be highlight blue. Click `Start`. From here, it should be starting up the VM from the OS. Select install and it may take some time. Then proceed with the setting questions given on your new VM!
    - ![![Screenshot 2024-10-25 160312](https://github.com/user-attachments/assets/c192d5ac-dcb8-463b-be49-efcbd4926a5c)
](RELATIVE_PATH_TO_SCREENSHOT_IN_FOLDER)

## Part 3 - Virtual Playground:

1. How to change your desktop background in your VM:
2. How to install VSCode in your VM:
3. How to connect to your AWS instance from your VM using `ssh`:
