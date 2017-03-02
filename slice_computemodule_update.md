## Update rpi compute module on slice

[Flashing the compute module](https://www.raspberrypi.org/documentation/hardware/computemodule/cm-emmc-flashing.md)

[5ninja's forum on this](http://forums.fiveninjas.com/t/raspberry-pi-compute-module-3-has-been-released/1412)


### What I did

1) Went through the instructions on [here](https://www.raspberrypi.org/documentation/hardware/computemodule/cm-emmc-flashing.md) to clone a repository, and then build 
```
cd ~/src
git clone --depth=1 https://github.com/raspberrypi/usbboot
cd usbboot
sudo apt-get install libusb-1.0.0-dev
make
mkdir ~/src/slice3
```

2) Download the installer from LibreELEC from https://libreelec.tv/downloads/
* Got `LibreELEC.USB-SD.Creator.Linux-64bit.bin`
* put in directory `src/slice3`

3) Download the build from http://chewitt.libreelec.tv/slice/

*  I got the img.gz file for the CM3
*  put in directory `src/slice3`
*  `gunzip LibreELEC-Slice3.arm-8.0.0.img.gz`

4) Computer module arrived

5) plugged in a usb cable to the slice the ran sudo ./rpiboot 

6)  /dev/sde appears

7)  `sudo dd if=LibreELEC-Slice3.arm-8.0.0.img of=/dev/sde bs=4MiB`

8) Finished but then /dev/sde1 and /dev/sde2 do not appear when I unplug and replug in the slice

9) Works when I switch on though.  ssh default root, password libreelec
