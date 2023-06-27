# Setup for Virtual Box

## Host 
- Windows 11

## Virtual Box Linux
Version 7.06
- Creating the Machine
    - Unbuntu Linux 22.04 LTS
    - Skip Unattended 
    - 16G Memory
    - 4 Cores
    - 25 to 50 GB Diskspace
    - 64K Video Memory
    - Networking
       - Typically Bridged
            -  Might need to reboot a couple of times.

- Display Sizing 
```console
sudo apt install update`
sudo apt install upgrade`
sudo apt install build-essentials dkms linux-headers-$(uname -r)`
```
- VM/InstallGuestAdditions
```console
/media/<user>/<vbox...>/autorun.sh
```
## Virtual Box WindowsXP Mode
This website has great instructions on downloading and installing Windows XP Mode
- https://www.makeuseof.com/tag/download-windows-xp-for-free-and-legally-straight-from-microsoft-si/
- Windows XP Mode is free

Black Screen Issue: 
- There is a point where you might get a black screen. Go into the VM and change the display to VMSVGA.
- https://www.youtube.com/watch?v=seGdSNimbOQ
