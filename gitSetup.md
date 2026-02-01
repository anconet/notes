# Git Setup
[← Return to Home](readMe.md)

---
Useful things I always have to do.

```bash
git config --global user.name "<first> <last>"
git config --global user.email <email>
git config --global core.editor vim
```
## Adding Branch to the Bash Prompt
Add the following to the old `.bashrc`

Reference: [Chi Thuc Nguyen @ Medium](https://thucnc.medium.com/how-to-show-current-git-branch-with-colors-in-bash-prompt-380d05a24745)

```bash
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="\u@\h \[\e[32m\]\w \[\e[91m\]\$(parse_git_branch)\[\e[00m\]$ "
```
## Adding Branch to the Bash Prompt
Add the following to the old `.bashrc`

Reference: [Chi Thuc Nguyen @ Medium](https://thucnc.medium.com/how-to-show-current-git-branch-with-colors-in-bash-prompt-380d05a24745)

```bash
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
export PS1="\u@\h \[\e[32m\]\w \[\e[91m\]\$(parse_git_branch)\[\e[00m\]$ "
```
## Setting Up a silly Credentials Manager
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

## More stupid Github notes
A note to my friend Future Anthony...

Stupid Github doesn't take passwords anymore on the command line. So you have to use a credentials manager (like above) or you have to use ssh. SSH is probably the best path.

However, I'm running VS code on Windows. VSCode on windows has it's own credentials manager. So when you go to do a first ever operation against github with VSCode, VSCode will pop up a window to ask you to sign into github. From that point on, VScode can do operations with Github.

However, However, running a terminal in VSCode does not leverage the credentials manager. So if you go for a while without using the VSCode, Github may timeout and say "Hey, you gotta log in again. And we're fricking stupid, so you have to use a credentials manager."

So if you perform any operation with VSCode, that registers my laptop against github. And now I can use command lines again.

## Just running SSH against Github
Here is a greate write up on (Setting Up SSH)[https://gist.github.com/xirixiz/b6b0c6f4917ce17a90e00f9b60566278]
* Generate Key pair
* Copy Pub Key to github account
* run `ssh -T git@github.com` to verify connection

