# Git Setup
---
Useful things I always have to do.

```bash
git config --global user.name "<first> <last>"
git config --global user.email <email>
git config --global core.editor vim
```
Setting Up a silly Credentials Manager
```bash
# Download the .deb
curl -LO https://github.com/git-ecosystem/git-credential-manager/releases/download/v2.1.2/gcm-linux_amd64.2.1.2.deb

# Found the instructions here https://github.com/git-ecosystem/git-credential-manager/blob/release/docs/install.md

# Install the .deb
sudo dpkg -i <path-to-package>
# Or
sudo apt install ./<file.deb>
# configure GCM
git-credential-manager configure
# Tell git to use GCM
git config --global credential.credentialStore cache
```
