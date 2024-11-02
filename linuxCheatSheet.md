# Linux Cheat Sheet
---
## Package Management
`apt` is a front end to `dpkg`
```bash
# To instsall a specific downloaded .deb.
dpkg --install <file.deb>
#or 
apt install ./<file.deb>
dpkg --list # List only installed files

apt list # All packages, Installed or not.
apt list --installed #Only packages that are installed.

```

## Find

Finding Files by Name in a Directory
```bash 
find <directories> -type f -name <file_name>
```

## Curl
Download thngs from websits
```bash
# -L follows redirects
# -O use file name from the website
curl -LO [URL] 
```

## Stats
```bash
# size of disk
df -h or -m
# size of directories
du -h or -m
# Running stats
top
top -o %MEM #sort by memory usage
# Simper view of memory
free -tm # total and in mb
```

## Check Open ports
```bash
less /etc/services
ss -tunlp
```