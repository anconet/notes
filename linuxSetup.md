[Home](readMe.md)
# Setup points for Linux

## Always
```console
sudo apt update
sudo apt upgrade
```
## SSH 
### Server
```console 
sudo apt install openssh-server
```
Usually the server is added to Startup. Server runs under the process `sshd`
### Client
#### Key Pair Generation
```console
ssh-keygen -t rsa -b 4096
ssh-copy-id -i id_rsa <userId>@<remote>
```

### Agent
[Virtual Box Setup](virtualBox.md)





