
Squeezebox Stuff
=================


Open to the external world to listen at work
---------------------------------------------

* Forwarded port 9000 to the raspberry pi server
* opening location:9000 allows me to see server
* opening location:9000/stream.mp3 appears to open stream, but I can't hear anything.
* added block incoming connections to server interface.  192.168.0.*, 127.0.0.1, 128.240.*.* and 

*but I need to add password protection - added password connected.  on keepass2



## Setting up squeezebox without a remote

This is done using the perl library [net-udap](https://github.com/robinbowes/net-udap) by Robin Bowes, that I have in my `src/` directory.  

### Net-udap

Didn't work first time using

```
    perl Makefile.PL
    make
    make test
    make install
```

as it failed on the test.  Installing modules using

```
 sudo cpan install Log::StdLog Term::Shell Class::Accessor IO::Interface::Simple

```

seemed to make it work.



Instructions [here]( sudo cpan install Log::StdLog Term::Shell Class::Accessor IO::Interface::Simple) (link from github issues) also seems to help.

old getting started <https://projects.robinbowes.com/Net-UDAP/trac/wiki/GettingStarted>

Instructions for use on [wiki](https://github.com/robinbowes/net-udap/wiki/Configuring-the-device---an-example)

Press button for six seconds until flashes rapidly. 



#### Setup for wired system, DHCP

```perl
./scripts/udap_sell.pl

UDAP> discover
UDAP> list
UDAP> configure 1
UDAP> set squeezecenter_address=192.168.0.150
UDAP> set interface=1
UDAP> set lap_ip_mode=1
UDAP> save_data
UDAP> reset
```

Note that `fields` gives you an overview of what you can set and `list` shows what is set.

#### Setup for wireless system, static IP

```perl
./scripts/udap_sell.pl

UDAP> discover
UDAP> list
UDAP> configure 1
UDAP> set squeezecenter_address=192.168.0.160
UDAP> set interface=1
UDAP> set lap_ip_mode=1
UDAP> save_data
UDAP> reset
```





 

### References

 [Enjoying_your_music_from_another_place](http://wiki.slimdevices.com/index.php/Enjoying_your_music_from_another_place)

[Remote_streaming](http://wiki.slimdevices.com/index.php/Remote_streaming)

[Connecting_remotely](http://wiki.slimdevices.com/index.php/Connecting_remotely)

[softsqueeze](http://wiki.slimdevices.com/index.php/SoftSqueeze)

[squeezelite](http://wiki.slimdevices.com/index.php/Squeezelite)

[squeezelite manual](http://manpages.ubuntu.com/manpages/trusty/man1/squeezelite.1.html)

[another tutorial](http://wiki.slimdevices.com/index.php/Enjoying_your_music_from_another_place)

 