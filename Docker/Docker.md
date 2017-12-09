# Docker

## Volume
### Créer

`docker volume create --name [name]`

### Supprimer
`docker volume create rm [name]`

## Maintenance

### Supprimer tous les containers

`docker rm ($docker ps -a -q)`


## Install

### Uninstall old

`sudo apt-get remove docker docker-engine docker.io`

### Install packages

`sudo apt-get install apt-transport-https ca-certificates curl software-properties-common`

### Repository

`sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`

### GPG key

`curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`

### Install

`sudo apt update && sudo apt install docker-ce`

`sudo usermod -aG docker $USER`


## Save/load

### Save
`docker save [image] > image.tar`

ou

`docker save --output busybox.tar busybox`

### Load

`docker load < image.tar

### Copy

`docker cp [OPTIONS] CONTAINER:SRC_PATH DEST_PATH|-`

`docker cp [OPTIONS] SRC_PATH|- CONTAINER:DEST_PATH`


## Links

http://training.play-with-docker.com/
