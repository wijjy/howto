## Update rpi compute module on slice

[Flashing the compute module](https://www.raspberrypi.org/documentation/hardware/computemodule/cm-emmc-flashing.md)

[5ninja's forum on this](http://forums.fiveninjas.com/t/raspberry-pi-compute-module-3-has-been-released/1412)


### What I did

1) Went through the instructions on [here](https://www.raspberrypi.org/documentation/hardware/computemodule/cm-emmc-flashing.md)
to clone a repository, and then build 

```
cd ~/src
git clone --depth=1 https://github.com/raspberrypi/usbboot
cd usbboot
sudo apt-get install libusb-1.0.0-dev
make
mkdir ~/src/slice3
```

2) - Download the installer from LibreELEC from https://libreelec.tv/downloads/

Got `LibreELEC.USB-SD.Creator.Linux-64bit.bin`

put in directory `src/slice3`


3) Download the build from http://chewitt.libreelec.tv/slice/

I got the img.gz file for the CM3
` gunzip LibreELEC-Slice3.arm-8.0.0.img.gz `

put in directory `src/slice3`





2) Now wait for my ordered compute model to come through
