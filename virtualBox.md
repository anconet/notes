# Setup for Virtual Box

Host 
- Windows 11

Virtual Box
- Version 7.06
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
            - NAT might give a more predictable IP address.
                - Need this to be able to hit the machine consistenly from VC Code.
- Display Sizing 
    - `sudo apt install update`
    - `sudo apt install upgrade`
    - `sudo apt install build-essentials dkms linux-headers-$(uname -r)`
    - VM/InstallGuestAdditions
    - `/media/<user>/<vbox...>/autorun.sh `

