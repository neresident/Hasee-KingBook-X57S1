# Haskintosh for Hasee KingBook X57S1

 - OpenCore
 - Intel Core i7-1065G7
 - Hasee HINS02   ( Intel 495 Series Chipset, Intel Ice Point-LP, Intel Ice Lake-U )
 - Memory 16 GB DDR4-2666 (8 GB x 2, upgradable) 
 - Realtek ALC256
 - Intel(R) Wi-Fi 6 AX201 160MHz / Working with BCM94360NG currently (requires kext to get full 5Ghz speeds)
 - BOEhydis NV156FHM-N61 [15.6" LCD]
 - [Geekbench Score] / [OpenCL Score] / [Metal Score]

---

### Functionality
 - [x] CPU Speedstep (XCPM)
 - [x] [4CH Audio] (2 Front + 2 Bottom speakers + Jack)
 - [x] Headphone
 - [ ] HDMI (Video And Audio)
 - [x] Battery Management
 - [x] Usb (with USB map)
 - [ ] Thunderbolt 3
 - [x] Wireless Network (Intel/Broadcom)
 - [x] Bluetooth
 - [x] Keyboard Brightness
 - [x] Fn Brightness Keys (thanks to [zhen-zen] for YogaSMC)
 - [x] Power Button = PWRB (thanks to [zhen-zen] for YogaSMC)
 - [x] I2C Touchpad (GPIO Mode) (thanks to [ben9923], [zhen-zen])
 - [x] Sleep/wake from LID (not stable)
 - [x] Sleep from SLPB (Fn+Esc)
 - [ ] Wake Up (Usb Device)
 - [x] Wake Up (PS/2 Keyboard) (Big Thanks to [m0d16l14n1])
 - [x] WebCam (OOTB)
 - [x] SDHC CardReader (OOTB)


### How To Use
 1. Copy EFI folder to ESP/EFI Partition in bootable USB flash drive.
 2. Install Mac OS X.
 3. Copy EFI folder to ESP/EFI Partition in HDD/SSD disk.
 5. [Modify BIOS For Advanced Setting] (Possible Collapse BIOS, IF YOU NOT DO IT RIGHT)
 6. Disable CFG Lock, Change DVMT to 128MB, And Disable CFG Fix in config.plist
 7. If you have any problems with installation - use [dortania] guides

### Tools
  - [OpenCorePkg]
  - [Hackintool]
  - [Maciasl]
  - [DarwinDumper]
  - [BootDiskUtility]


### Thanks
* To all of [acidanthera] and [dortania] team members for all of their kexts/guides and etc 
* Collaborateur [m0d16l14n1]
* I2C Touchpad Helper [ben9923] & [zhen-zen]
* [OC-little]
* AppleALC patch for Ice Lake and help [fewtarius] 
* [0xFireWolf] for multiple Ice Lake fixes

[Geekbench Score]:<https://browser.geekbench.com/v5/cpu/3534153>
[OpenCL Score]:<https://browser.geekbench.com/v5/compute/1430453>
[Metal Score]:<https://browser.geekbench.com/v5/compute/1430464>

[OpenCorePkg]: <https://github.com/acidanthera/OpenCorePkg>
[Hackintool]: <https://github.com/headkaze/Hackintool>
[Maciasl]: <https://sourceforge.net/projects/maciasl/>
[DarwinDumper]: <https://bitbucket.org/blackosx/darwindumper>
[BootDiskUtility]: <http://cvad-mac.narod.ru/>

[Modify BIOS For Advanced Setting]: <https://github.com/Ardentwheel/OpenCore-Hasee-X57S1/tree/master/Tools/BIOS>
[4CH Audio]: <https://github.com/acidanthera/AppleALC/pull/601>

[ben9923]: <https://github.com/ben9923>
[m0d16l14n1]: <https://github.com/m0d16l14n1>
[zhen-zen]: <https://github.com/zhen-zen>
[OC-little]: <https://github.com/daliansky/OC-little>
[fewtarius]: <https://github.com/fewtarius>
[acidanthera]: <https://github.com/acidanthera>
[dortania]: <https://github.com/dortania>
[0xFireWolf]: <https://github.com/0xFireWolf>