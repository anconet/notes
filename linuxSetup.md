# Setup points for Linux
[← Return to Home](readMe.md)

---
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
ssh-keygen -t rsa -b 4096 -C "Anthony's Dev Laptop"
ssh-copy-id -i id_rsa <userId>@<remote>
```
#### Server Side again
Once you have the your key pair. Past the public key in .ssh/authorized_keys on the server.






