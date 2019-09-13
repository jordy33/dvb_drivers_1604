## How to install tvheadend in ubuntu

### Install Tvheadend

Dependencies

```
sudo apt-get install gitk
sudo apt-get install libiconv
sudo apt-get install libic6
sudo apt-get install libc6
sudo apt-get install libiconv-dev
sudo apt-get install libc6-dev
sudo apt-get install clang
sudo apt-get install libdvbcsa-dev
sudo apt-get install dvb-apps
git clone https://github.com/tvheadend/dtv-scan-tables.git
cd dtv-scan-tables/
make clean
sudo make dvbv3
sudo make install

git clone https://github.com/tvheadend/tvheadend.git
gitk --all
git checkout 9874ab0b1d4a6752840a9a23bf7502c3e623825f
```

### Configure Options
```
 ./configure --enable-dvbcsa --enable-constcw  --enable-bundle
```

### Compile
```
make
```

### Test

```
./build.linux/tvheadend
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

### Install FFmpeg
```
sudo apt-get install ffmpeg
ffmpeg -version
```

In Kodi, create a user * with password * 
Provide all streaimg access


In tvh add an IPTV network (no automatic).  Add a mux for that network and use a URL like this....

For version 2.8.15

```
pipe:///usr/bin/ffmpeg -loglevel fatal -re -i http://localhost:9981/stream/channel/6a86ca950c6198ef2c992d4437955e18?ticket=A36A476830B5BFA62BCD75C7B6B5893512ED567 -c:v copy -filter_complex [0:1][0:2][0:3]amerge=inputs=3,pan=5.1|FL=c0|FR=c1|FC=c2|LFE=c3|BL=c4|BR=c5 -c:a eac3 -f mpegts pipe:1
```

(Get the http link openning the link to open the channel)

It'll scan in a new service and you just map that to a new channel.  

