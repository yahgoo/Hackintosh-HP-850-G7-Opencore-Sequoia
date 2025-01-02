# Hackintosh HP 850 G7 Opencore Sequoia
* Opencore EFI for HP 850 G7 running Sequoia

## Changes
28112022
- Updated to MacOS Ventura 13.1
- Updated to OC 0.8.7 and latest kexts

## Working
- Full graphics acceleration on Intel UHD620 iGPU
- Multi-display with DisplayPort OOB, VGA 
- GigEthernet LAN connection
- Wireless and bluetooth with any compatible card
- CPU power management
- Battery management
- Keyboard and touchpad
- Keyboard backlight (F5/F6)
- Touchpad including tap-to-click, scrolling, mouse buttons (can be disable with prt scr key)

![Screenshot]()

# Specifications:
* CPU: Intel Core i7-6600U
* GPU: Intel HD Graphics HD 520
* Resolution: 1600x900
* Audio: Sunrise Point-LP HD Audio
* Wi-Fi: BCM94360CS2
* Bluetooth: Broadcom Bluetooth 4.0
* Ethernet: Intel
* Touchpad: Synaptics SMBus TouchPad
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

## Credits 
OSXLatitude - Herve, Jake Lo  
TonyMacx86 - Feartech  
EliteMacx86 - EliteMacx86  
Opencore Dev Team  

