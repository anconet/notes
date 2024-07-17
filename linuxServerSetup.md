# Linux Server Setup
---
## Notes on Virtual Box
- Bridged Mode

## Ubuntu 24.04 Server
- Seems like there was an option for pull ssh pub key from github.
- git comes installed

```bash 
scp ./ssh/id_rsa.pub <userid>@<server>:~/.ssh
```
```bash
# Updates
sudo apt update
sudo apt upgrade -y
# SSH creature comforts
cat ~/.ssh/id_rsa.pub >> authorized_keys
# Docker
see [Docker Instructions](https://docs.docker.com/engine/install/ubuntu/)
```

Fixing the stupid undersizing of the drive (Here)[https://askubuntu.com/questions/1106795/ubuntu-server-18-04-lvm-out-of-space-with-improper-default-partitioning]

```bash
du -h
sudo lvm
lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
exit

sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
du -h
```

## Alpine

