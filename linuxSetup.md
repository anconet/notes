# Setup points for Linux

## Always
- `sudo apt update`
- `sudo apt upgrade`

## SSH 
### Server
- `sudo apt instal openssh-server`

    Usually the server be added to Startup.\
    Server runs under the process `sshd`\
### Key Pair Generation
- `ssh-keygen -t rsa -b 4096`
- `ssh-copy-id -i id_rsa <userId>@<remote>`

### Agent






