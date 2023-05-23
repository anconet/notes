[Home](readMe.md)
# Setup points for Linux

## Always
```console
sudo apt update
sudo apt upgrade
```
---
## Host Name
Edit the below files by replace `old-hostname` with `new-hostname`
```bash
sudo vim /etc/hostname
sudo vim /etc/hosts
reboot
```
---
## SSH 
### Server Side
Install and create the server. The process will run under `sshd`. Will automatically go into the startup file.
```console 
sudo apt install openssh-server
```
### Client Side
Key Pair Generation
```console
ssh-keygen -t rsa -b 4096
ssh-copy-id -i id_rsa <userId>@<remote>
```







