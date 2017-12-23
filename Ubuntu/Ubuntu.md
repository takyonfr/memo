# Ubuntu

## How to fix non bootable ubuntu system

http://www.webupd8.org/2014/01/how-to-fix-non-bootable-ubuntu-system.html


## Terminator

### Install

`sudo apt-get install terminator`

### Remove gnome-terminal
`sudo apt-get remove gnome-terminal`

### Symlink terminator to gnome-terminal

`sudo ln -s /usr/bin/terminator /usr/bin/gnome-terminal`


## SDCard

`sudo dd bs=4M if=~/SDCardBackup.img of=/dev/sdd`

## Virtualbox

`sudo usermod -a -G vboxsf user`

## Accidentally deleted folder

http://askubuntu.com/questions/150671/accidentally-deleted-a-folder
