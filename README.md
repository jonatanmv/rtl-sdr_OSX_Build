# rtl-sdr_OSX_Build
Notes on building rtl-sdr on MacOSX

## Device used
You can use a number of compatible devices. The one I used was: \
![Image of Nooelec NESDR SMArTee v2 device](https://archive.org/download/hamradio_utils/Nooelec%20NESDR%20SMArTee%20v2.jpg)
```Nooelec NESDR SMArTee v2 (Generic RTL2832U``` \
For more info and compatible devices you can check https://osmocom.org/projects/rtl-sdr/wiki/Rtl-sdr
http://sdr.osmocom.org/trac/wiki/rtl-sdr

## Install pre-requisites (check your own environment)
This may be deifferent for your specifiy enviroment, so check it and adapt it. I used a MacOS laptop as platform, using homebrew https://brew.sh
```shell
brew install cmake libusb pkgconfig
```
Optionally you can install ```brew install sox``` (Sound eXchange for easy audio)

## Get Source code and install it
git clone git://git.osmocom.org/rtl-sdr.git \
For more information on the installation you can check https://osmocom.org/projects/rtl-sdr/wiki/Rtl-sdr#Source-Code . I put here the steps for you:
```shell
cd rtl-sdr/
mkdir build
cd build/
cmake ../
make LIBRARY_PATH=/usr/local/lib
sudo make install
```

## Test installation
To test the installation just open a terminal and try this command:
```shell
rtl_test -t
```
The output should be something similar to:
```shell
Found 1 device(s):
  0:  Realtek, RTL2838UHIDIR, SN: 00000001

Using device 0: Generic RTL2832U OEM
Found Rafael Micro R820T tuner
Supported gain values (29): 0.0 0.9 1.4 2.7 3.7 7.7 8.7 12.5 14.4 15.7 16.6 19.7 20.7 22.9 25.4 28.0 29.7 32.8 33.8 36.4 37.2 38.6 40.2 42.1 43.4 43.9 44.5 48.0 49.6 
[R82XX] PLL not locked!
Sampling at 2048000 S/s.
No E4000 tuner found, aborting.
```
If this is the case... Congratulations ! \
