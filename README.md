# Hackintosh-OptiPlex-9020M
**Works on MacOS Big Sur and Catalina.**

This is the Hackintosh EFI Folder for Dell OptiPlex 9020M. The configuration settings support MacOS Catalina 10.15.7 and Big Sur 11.6.3 with resolution up to 1920x1080. HiPDI support can be actived with [One Key HiDPI](https://github.com/xzhih/one-key-hidpi/blob/master/README.md) script. You will have to **generate a new serial and SmUUID** before login to your iCloud account and if you install Big Sur, you also need [Map USB](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html) so that you won't have any problems with the usb ports when installing .

![Screen Shot 2022-01-31 at 20 03 52](https://user-images.githubusercontent.com/92006941/151798456-ec3db64d-177e-46da-ab0f-45345fe818bc.png)

## Specs

* **Name:** [Dell OptiPlex 9020M](https://www.hardware-corner.net/desktop-models/Dell-OptiPlex-9020M/) with 1 port DP and 1 port VGA
* **CPU:** [Intel® Core™ i5-4590T](https://ark.intel.com/content/www/vn/vi/ark/products/78928/intel-core-i5-4590t-processor-6m-cache-up-to-3-00-ghz.html)
* **iGPU:** Intel® HD Graphics 4600
* **RAM:** 8GB DDR3 1600MHz
* **SSD:** NT-256-TI
* **Ethernet:** I217-LM
* **Wi-Fi & Bluetooth:** AC-7260

## Working

* CPU Turbo Boost
* Integrated Graphics with acceleration
* Monitor output at 1920x1080
* Integrated Audio Output/Input
* All USB Ports
* LAN & Wireless Network
* Sleep & Wakeup

## Not  Working

* Airdrop & Airplay
* Handoff
* SideCar
* DRM for stuff like Netflix and Amazon Prime [require a dGPU](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md).

## BIOS Settings
- General → Advanced Boot Options: ***uncheck***
- General → Advance Boot options → Enable Legacy Operation ROMs: ***uncheck***
- System Configuration → SATA Operation: ***AHCI***
- Secure Boot → Secure Boot Enable: ***Disabled***
- Virtualization Support → VT for Direct I/O: ***uncheck***
- Virtualization Support → Virtualization: ***check***


## BIOS Settings via modGRUBShell.efi

First, download [modGRUBShell.efi](https://github.com/datasone/grub-mod-setup_var/releases) then put it in EFI/OC/Tools folder, next Open config.plist and add it to Misc -> Tools. When you are in the boot Menu of Opencore, select modGRUBShell.efi then enter the values below

* Disable CFG Lock: 
  * **setup_var 0xD9F 0x0**
* Set DVMT pre-alloc to 64MB: 
  * **setup_var 0x263 0x2**
* Enable EHCI hand-off:
  * **setup_var 0x2 0x1**
  * **setup_var 0x144 0x1**
  * **setup_var 0x15A 0x2**
  * **setup_var 0x146 0x0**
  * **setup_var 0x147 0x0**

When done, reboot.

![Screen Shot 2022-01-31 at 20 06 19](https://user-images.githubusercontent.com/92006941/151798769-f04208b1-029d-4fc4-86cf-c7d8ac0aee93.png)

[Download the EFI](https://github.com/HowNeft/Optiplex9020M/releases/tag/Release)

**Good Luck** 
