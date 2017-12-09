# Software
## Wire

Chat voice, messaging

`sudo apt install apt-transport-https`

`sudo apt-key adv –fetch-keys http://wire-app.wire.com/linux/releases.key`

`echo “deb https://wire-app.wire.com/linux/debian stable main” | sudo tee /etc/apt/sources.list.d/wire-desktop.list`

`sudo apt update && sudo apt install wire-desktop`
