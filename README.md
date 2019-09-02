## How to install tvheadend in ubuntu

### Install Tvheadend
```
sudo apt-get -y install coreutils wget apt-transport-https lsb-release ca-certificates
sudo wget -qO- https://doozer.io/keys/tvheadend/tvheadend/pgp | sudo apt-key add -
sudo sh -c 'echo "deb https://apt.tvheadend.org/stable $(lsb_release -sc) main" | tee -a /etc/apt/sources.list.d/tvheadend.list'

sudo apt-get update
sudo apt-get install tvheadend
```

### Install Kodi
```
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:team-xbmc/ppa
sudo apt-get update
sudo apt-get install kodi
```

### Install hts tvheadend client
```
sudo apt-get install kodi-pvr-hts
sudo apt-get install kodi-pvr-iptvsimple
```


