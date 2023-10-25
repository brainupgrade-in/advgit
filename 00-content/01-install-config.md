# Installation 
## Ubuntu
```
sudo apt install git python3-pip
sudo pip3 install gitsome
```

# Configuration
git config --global user.name ""
git config --global user.email ""
git config --global color.ui true
git config --global core.editor "vim"
## Window 
git config --global core.autocrlf true
## Linux 
git config --global core.autocrlf input

## VSCode for diff
git config --global diff.tool vscode
git config --global difftool.vscode.cmd "code -wait"