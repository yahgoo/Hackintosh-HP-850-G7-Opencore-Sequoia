# Hackintosh HP 850 G7 Opencore Sequoia
* Opencore EFI for HP 850 G7 running Sequoia

## Changes


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
- Right USB A port. To fix via usb port mapping
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

## Credits 
ikip  
Opencore Dev Team  

