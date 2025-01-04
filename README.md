# Hackintosh HP 850 G7 Opencore Sequoia
* Opencore EFI for HP 850 G7 running Sequoia

## Changes
04012025  
- Fix all USB port via port mapping 
- Fix Bluetooth as notes below 

## Working
- Full graphics acceleration on Intel UHD630 iGPU
- GigEthernet LAN connection
- Wireless and bluetooth with any compatible card
- CPU power management
- Battery management
- Keyboard and touchpad
- Keyboard backlight (F5/F6)
- Touchpad including tap-to-click, scrolling, mouse buttons (can be disable with prt scr key)

## Not Working
- Camera
- Microphone
- HDMI

![Screenshot](https://github.com/yahgoo/Hackintosh-HP-850-G7-Opencore-Sequoia/blob/main/img/Sequoia%20running%20on%20HP850G7.png)

# Specifications:
* CPU: Intel i7-10510U (4) @ 1.80GHz
* GPU: Intel HD Graphics UHD 630
* Resolution: 1600x900
* Audio: Intel Audio
* Wi-Fi: BCM94360CS2
* Bluetooth: Broadcom Bluetooth 4.0
* Ethernet: Intel
* Card reader
* Fingerprint: Synaptics Fingerprint Sensors

## Set bios settings as follows:
Advanced tab:  
Boot options:  
- Fast Boot = Disabled
- Network (PXE) Boot = Disabled  
Secure Boot Configuration:
- "Legacy Support Enable and Secure Boot Disable"  
System Options:  
- Virtualization Technology (VTx) = Disabled (recommended, Enable also worked)
- Virtualization Technology for Direct I/O (VTd) = Disabled (recommended, Enable also worked)  
Built-In Device Options:  
- Wake On LAN = Disabled
- Video memory size = 64 MB
- LAN/WLAN Auto Switching = Disabled
- Fingerprint Device = Disabled  
Power Management Options:  
- Extended Idle Power States = Disabled
- Deep sleep = You can keep this enabled
- Wake when Lid is Opened = Enabled
- Wake on USB = Disabled

## Notes  
How to get BCM94360CS2 to work with macOS Sequoia
0. Set SMBIOS in order for Compatibility with Sequoia eg MacBookPro16,4 for HP 850 G7
1. Mount ESP, select EFI folder, copy below kext to OC/kexts folder:
AMFIPass.kext
IOSkywalkFamily.kext
IO80211FamilyLegacy.kext
IO80211FamilyLegacy.kext/Contents/PlugIns/AirPortBrcmNIC.kext
2. Open config.plist, run OC Configurator, click Add tab to add below:
BundlePath: IOSkywalkFamily.kext
BundlePath: IO80211FamilyLegacy.kext
IO80211FamilyLegacy.kext/Contents/PlugIns/AirPortBrcmNIC.kext
MinKernel: 24.0.0
3. Click Block tab to block below:
Arch: Any
Identifier: com.apple.iokit.IOSkywalkFamily
Comment: Allow IOSkywalkFamily Downgrade
MinKernel: 24.0.0
Strategy: Exclude
Enabled: YES
4. Select Misc, click Security tab to disable Secure Boot Model:
Set dropdown list to Disabled
5. Select NVRAM, add boot Args:
Select last entry "7C....F82", add "-v keepsyms=1  -lilubetaall revpatch=sbvmm" to boot-args key
6. Disable SIP for root patching
Set csr-active-config to 03080000
7. Save config.plist
8. Reboot system and reset NVRAM
9. Patch System Volume
Run OCLP and select Post-install Root Patch
Click Start Root Patching
Click Yes to relaunch as root
10. Reboot system and reset NVRAM

## Credits 
perez987 aka miliuco
ikip  
Opencore Dev Team  

