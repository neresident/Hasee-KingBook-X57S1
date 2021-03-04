## Changelog

### 11 January 

* Testing ig-platform-ids, except default, which is used by WEG and stable 8A5C0002

8A520000 - unstable sleep/wake - waking to black screen

8A530002 - unstable sleep, sometimes wake to black screen (need to put back in sleep and wake again)

**8A5C0002** - stable sleep, stable wake 

*8A520001* - currently testing

* Trying to get headphones working with auto-detect if you plug them in laptop, trying to get Line-in working also

* Captured logs of booting process (that black screen glitch), logs while using HiDPi with blinking screen, logs with some patches of WEG, which are not applied, idk why


### 6 February

Updated to Big Sur 11.3 Beta 1

#### Fixes:

* Headphones detection with auto-switch after plug / ungplug; audio is now working after reboot/shutdown from Windows thanks to @agasecond

* Fixed random sleep issues due to Thunderbolt 3 USB (TXHC) and lid state status (fixed in SSDT-LID)

* PWRB is working normally again (because of YogaSMC)

* Updated to OC 0.6.6 and new versions of kexts

#### WIP:

* Line-in

* Touchpad is not working after hot reboot from Windows / But working if you do shutdown from Windows

* To get FAN sensor working (not FAN managament, just the sensor itself)


### 4 March 

Updated to Big Sur 11.2.1 (reverted from beta)

#### Fixes:

* HiDPI glitching and blinking problem finally fixed (details are in readme file)

* Updated kexts/OC

* Finally, thanks to that dumps from original MacBook Air (that's about fixing HiDPI too), i have found the most stable ig-platform

* Touchpad is working after hot reboots from any OSes (details are in readme file)

* Fully fixed sleep issues

#### WIP

* Line-in (still using pre-built version of AppleALC)

* Fan sensor

* Thunderbolt 3 
