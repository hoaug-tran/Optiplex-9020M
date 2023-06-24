# **Hackintosh-OptiPlex-9020M**
**Works on MacOS Catalina, Big Sur and Monterey**

This is the Hackintosh EFI Folder for Dell OptiPlex 9020M (**_only Dell OptiPlex 9020M_**). The configuration settings support MacOS Catalina lastest, Big Sur lastest and Monterey lastest with resolution up to 1920x1080. HiPDI support can be actived with [One Key HiDPI](https://github.com/xzhih/one-key-hidpi/blob/master/README.md) script. You will have to [generate a new SMBIOS](https://github.com/corpnewt/GenSMBIOS) before login to your iCloud account and need [Map USB](https://dortania.github.io/OpenCore-Post-Install/usb/intel-mapping/intel.html) so that you won't have any problems with the usb ports when installing.

Also, if you install Catalina you should use SMBIOS iMac14.3. If you install Big Sur, you can use SMBIOS iMac14.4 or 15.1. If you install Monterey, you need to use SMBIOS iMac16.2. I recommend installing Catalina or Big Sur for the smoothest experience.

![Screen Shot 2023-06-24 at 14 16 20](https://github.com/hoaug-tran/Optiplex-9020M/assets/92006941/50b1c562-afe3-4f46-8069-534c9ad59c68)

## **Specs**

* **Name:** [Dell OptiPlex 9020M](https://www.hardware-corner.net/desktop-models/Dell-OptiPlex-9020M/) with 1 port DP and 1 port VGA
* **CPU:** [Intel® Core™ i5-4590T](https://ark.intel.com/content/www/vn/vi/ark/products/78928/intel-core-i5-4590t-processor-6m-cache-up-to-3-00-ghz.html)
* **iGPU:** Intel® HD Graphics 4600
* **RAM:** 8GB DDR3 1600MHz
* **SSD:** NT-256-TI
* **Ethernet:** I217-LM
* **Wi-Fi & Bluetooth:** AC-7260

## **Working**

* CPU Turbo Boost
* Integrated Graphics with acceleration
* Monitor output at 1920x1080
* Integrated Audio Output/Input
* All USB Ports
* LAN & Wireless Network
* Sleep & Wakeup

## **Not  Working**

* Airdrop & Airplay ( *It can be fixed if you replace the Intel card with a native Broadcom Wifi card such as BCM94360NG* )
* Handoff
* SideCar
* DRM for stuff like Netflix and Amazon Prime [require a dGPU](https://github.com/acidanthera/WhateverGreen/blob/master/Manual/FAQ.Chart.md).

## **BIOS Settings**
- General → Advanced Boot Options: ***Disabled***
- General → Advance Boot options → Enable Legacy Operation ROMs: ***Disabled***
- System Configuration → SATA Operation: ***AHCI***
- Secure Boot → Secure Boot Enable: ***Disabled***
- Virtualization Support → VT for Direct I/O: ***Disabled***
- Virtualization Support → Virtualization: ***Enabled***


## **BIOS Settings via modGRUBShell.efi**

First, download [modGRUBShell.efi](https://github.com/datasone/grub-mod-setup_var/releases) then put it in EFI/OC/Tools folder, next Open config.plist and add it to Misc -> Tools. When you are in the boot Menu of Opencore, select modGRUBShell.efi then enter the values below.

 **WARNING!: Be careful with entering these values as it may cause you to fail the bios and have to remove the CMOS battery to reset the bios.**

---
**Disable CFG Lock:** 
  * setup_var 0xD9F 0x0
---
**Set DVMT pre-alloc to 64MB:** 
  * setup_var 0x263 0x2
---
**Enable EHCI hand-off** (Can be replaced with SSDT-EHCx_OFF.aml)**:**
  * setup_var 0x2 0x1
  * setup_var 0x144 0x1
  * setup_var 0x15A 0x2
  * setup_var 0x146 0x0
  * setup_var 0x147 0x0
---

**When done, reboot and enjoy.**

**Good Luck** 

Update time: 2:22 PM - Sat - 24/06/2023
