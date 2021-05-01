## Haskintosh for Hasee KingBook X57S1

[Ice Lake owners chat](https://gitter.im/ICE-LAKE-HACKINTOSH-DEVELOPMENT/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

 - Bootloader: OpenCore, currently 0.6.8 version
 - macOS: currently using Big Sur 11.3
 
### Some details about laptop

 - Intel Core i7-1065G7
 - Hasee HINS02 (Intel 495 Series Chipset, Intel Ice Point-LP, Intel Ice Lake-U)
 - Memory 16 GB DDR4-2666 (8 GB x 2, upgradable, Crucial)
 - 1TB NVME Crucial
 - Realtek ALC256 (2 front and 2 bottom speakers + headphones + internal mic in webcam + jack mic) 
 - Intel(R) Wi-Fi 6 AX201 160MHz / Working with BCM94360NG currently (requires kext to get full 5Ghz speeds)
 - BOEhydis NV156FHM-N61 [15.6" LCD]
 - HTIX5228 Touchpad / known as fake "SYN3602"/"ALPS0001"
 - 1 x Thunderbolt 3 Port
 - [Geekbench Score] / [OpenCL Score] / [Metal Score]

---

### Functionality

 - [x] CPU Speedstep (XCPM)
 - [x] Graphics (Intel Iris Plus G7)
 - [x] Audio (Speakers + headphones // auto-switch to headphones after plugging them working right now. Also audio is working after shutdown or reboot from Windows. Thanks to [agasecond] for fixing that)
 - [x] Type-C to HDMI (currently no sound)
 - [x] Battery Management
 - [x] USB (with USB map)
 - [x] Wireless Network (Intel/Broadcom)
 - [x] Bluetooth (Intel/Broadcom)
 - [x] Keyboard Brightness (OOTB)
 - [x] Fn Brightness Keys (thanks to [zhen-zen] for YogaSMC)
 - [x] Power Button = PWRB (thanks to [zhen-zen] for YogaSMC)
 - [x] Fully working I2C Touchpad (GPIO Interrupt) (thanks to for GDPI patch and consulting - [ben9923], [for patch in VoodooI2CHID] - [zhen-zen], [ben9923])
 - [x] Sleep/wake from LID (fixed now, thanks for SSDT to [kasti0])
 - [x] Sleep from SLPB (Fn+Esc)
 - [x] Wake Up (PS/2 Keyboard)
 - [x] WebCam (OOTB)

### Not working / Glitching / Bugging / WIP / Partly working

#### Sound: 

- [ ] Combojack problem: Jack mic is not working (Line-in) - still trying to fix that issue with creating own resources for [AppleALC] with [agasecond]

#### Graphics related: 

- [ ] HDMI (Video/Audio) - problem on the Apple's driver side (probably won't be fixed)
- [x] HiDPi issues before sleep-wake cycle - glitching-blinking screen while using launchpad/switching/dragging windows and etc. > Fixed via injecting value (AAPL,GfxYTile) from that [plist](https://github.com/khronokernel/DarwinDumped/blob/master/MacBookAir/MacBookAir9%2C1(2)/Device%20Properties/device-properties.plist) file (from real MacBook Air / MacBook Pro). Thanks to [Applelife topic](https://applelife.ru/threads/dampy-originalnyx-makov.2943712/) AND (especially to member of forum - RV_ABZ), [khronokernel](https://github.com/khronokernel)
- [ ] Login screen glitch [black glitch screen for 5-7 seconds] or any other screen corruption (related to all Ice Lake hackintoshes)

#### Peripherals: 

- [ ] Thunderbolt 3 - only did dump from chip with programmer (i didn't test it myself, but it seems to be working with eGPU, without Hotplug support, result was reported by [kingo132]
- [ ] MicroSD CardReader (USB based Realtek) - not mounting cards in system, not detected at all (working OOTB under Linux/Windows)
- [ ] Wake-up from USB inserting - actually not need that at all, just to mention.

#### Other

- [ ] Some vendor FnKeys not working (Fn+F1 - switch WiFi; Fn+F7 - LCD/Projector switch; Fn+F12 - switch Num Lk). Others working okay, like key brightness, switch of trackpad, volume and etc.
- [x] Touchpad is not working after hot reboot from Windows/Linux - you need to shutdown and boot to macOS to get it working. Touchpad required ACPI patch (GPIO) + codeless kext or ACPI patch to change name of touchpad to SYN3602 (fixed reboot from Windows) [Details about fix]
- [ ] Fan RPM are not working. Trying to get it working now with latest changes in SMCSuperIO.kext

#### Some info

Intel(R) ME code versions:

    BIOS Version                           IN1V105
    
    Vendor ID                              8086
    
    FW Version                             13.0.40.1738 LP Consumer

IUPs Information

    PMC FW Version                         130.1.30.1051
    
    IOM FW Version                         4.15.0.0000
    
    NPHY FW Version                        9.0.1.0006
    
    TBT FW Version                         13.0.0.7501
    
    PCHC FW Version                        13.0.0.1005

### Thanks

* To all of [acidanthera] and [dortania] team members for all of their kexts/guides and etc 
* Collaborateurs: [m0d16l14n1], [Ardentwheel]
* All VoodooI2C developers, especially [ben9923] & [zhen-zen] for fixes and helping to get touchpad working
* [OC-little] for some patches and guides
* [fewtarius] for AppleALC patch for Ice Lake and help
* [agasecond] for fixing headphones switching/sound working after reboot/shutdown from Windows
* [0xFireWolf] for multiple Ice Lake fixes
* [kasti0] for LID fix for his Lenovo, which helped me to make my lid work like it should with a small change (lid state)
* [AppleLife] forum - [link to my topic] (Russian forum)
* PCBeta forum
* Discord "Hackintosh Paradise" 
* Apple

[Geekbench Score]:<https://browser.geekbench.com/v5/cpu/3534153>
[OpenCL Score]:<https://browser.geekbench.com/v5/compute/1430453>
[Metal Score]:<https://browser.geekbench.com/v5/compute/1430464>

[Modify BIOS For Advanced Setting]: <https://github.com/Ardentwheel/OpenCore-Hasee-X57S1/tree/master/Tools/BIOS>
[black glitch screen for 5-7 seconds]: <https://github.com/acidanthera/bugtracker/issues/1329>
[for patch in VoodooI2CHID]: <https://github.com/VoodooI2C/VoodooI2CHID/pull/45>
[here]: <https://github.com/acidanthera/bugtracker/issues/1207>
[link to my topic]: <https://applelife.ru/threads/hasee-kingbook-x57s1.2945175/>
[Details about fix]: <https://github.com/VoodooI2C/VoodooI2C/issues/442>

[AppleLife]: <https://applelife.ru>
[ben9923]: <https://github.com/ben9923>
[m0d16l14n1]: <https://github.com/m0d16l14n1>
[Ardentwheel]: <https://github.com/Ardentwheel>
[zhen-zen]: <https://github.com/zhen-zen>
[OC-little]: <https://github.com/daliansky/OC-little>
[fewtarius]: <https://github.com/fewtarius>
[acidanthera]: <https://github.com/acidanthera>
[dortania]: <https://github.com/dortania>
[0xFireWolf]: <https://github.com/0xFireWolf>
[kasti0]: <https://github.com/kasti0>
[agasecond]: <https://github.com/agasecond>
[AppleALC]: <https://github.com/acidanthera/AppleALC>
[kingo132]: <https://github.com/kingo132>
