# Windows Subsystem for Linux

## Setup
```bash
wsl --list --online // Distro options
wsl --list // for what is installed
wsl --install -d [Distro] 
```
## Create Multiple Instances of the same distro.
https://www.mourtada.se/installing-multiple-instances-of-ubuntu-in-wsl2/

## Default User Password
When WSL is created the default user is whoever is logged in to Windows. For example `anthony`. There is no password. Because there is no password you can't run sudo. 

To set the password, from a windows prompt.
```bash
# From a Windows Terminal
wsl --list
<distro> config --default-user root
# From WSL
passwd anthony
# From Windows Terminal
<distro> config --default-user <user>
```

