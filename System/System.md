# Système

## Permission

`usermod -a -G {group} {user}`

## Savoir quelle appli utilise un port

if needed `sudo apt-get install net-tools`

`netstat -pnlt | grep ":5900"`

`netstat -plntu`

## tester un port ouvert

`nc -v -w2 smtp.gmail.com 465`

## SSH double authentification

https://korben.info/activer-lauthentification-2-etapes-serve=ur-ssh.html

## Shutdown

`shutdown -r now`

## NGINX SSL

https://www.digitalocean.com/community/tutorials/how-to-create-an-ssl-certificate-on-nginx-for-ubuntu-14-04
