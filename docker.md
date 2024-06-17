# Instructions for Installing Docker on Linux
---
From [Docker Install Instructions for Linux](https://docs.docker.com/engine/install/ubuntu/)
```bash
# Uninstal old version of Docker that came with the distro 
 for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

# Install Docker
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Test the Install
sudo docker run hello-world

sudo docker run -it ubuntu bash

# Messing with Containers and Images
sudo docker images
sudo docker ps
sudo docker ps --all #containers running or stoped.
sudo docker pull nginx:1.23
sudo docker run nginx:1.23
sudo docker run -d nginx:1.23 # Detached
sudo docker run --name myProxy -d nginx:1.23 # with a name
sudo docker logs <id>
sudo docker stop
sudo docker start
sudo docker run -d -p 9000:80 nginx:1.23 #Interna:External
```
## Docker Command FIle
```bash
FROM node:19-alpine 

# The second "/" tells docker to make the directory
COPY package.json  /app/
COPY src /app/
WORKDIR /app
RUN npm install 

CMD ["node","server.js"]
```
## Build
```bash
docker build --tag my-app:0.0.1 .
docker run --detach --publish 3000:3000 --name my-app-container my-app:0.0.1
```
Note: When running Docker inside of WSL. The docker ports are not nessarily exposed on the Host IP address (like 192.168.1.20 on the laptop). You can only hit the docker port on localhost or 127.0.0.1. To get from the host IP address to WSL. You have to go find the silly WSL address.
```bash
ip addr 

# eht0: is the WSL VM ip address
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:15:5d:42:40:9d brd ff:ff:ff:ff:ff:ff
    inet 172.29.201.131/20 brd 172.29.207.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::215:5dff:fe42:409d/64 scope link 
       valid_lft forever preferred_lft forever
3: br-65415284e72e: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:0a:b5:ec:4f brd ff:ff:ff:ff:ff:ff
    inet 172.18.0.1/16 brd 172.18.255.255 scope global br-65415284e72e
       valid_lft forever preferred_lft forever
    inet6 fe80::42:aff:feb5:ec4f/64 scope link 
       valid_lft forever preferred_lft forever
4: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:99:43:6d:4e brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
    inet6 fe80::42:99ff:fe43:6d4e/64 scope link 
       valid_lft forever preferred_lft forever
```
You then have to setup a power forward from the Host to WSL. In a windows terminal...
```bash
netsh interface portproxy add v4tov4 3000 172.29.201.131 3000
netsh interface portproxy show all

Listen on ipv4:             Connect to ipv4:

Address         Port        Address         Port
--------------- ----------  --------------- ----------
*               3000        172.29.201.131  3000
```

## Debug
```bash
sudo docker logs my-app-container
sudo docker exec --interactive my-app-container /bin/bash # Might not give you a prompt. But try ls.
```
## Networks
```bash
sudo docker network ls
sudo docker network create <name>
```
## Compose
```bash
sudo docker compose -f compose.yaml up -d
sudo docker compose -f compose.yaml down -d
```