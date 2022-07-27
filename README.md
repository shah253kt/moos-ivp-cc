# MOOS-IvP CC

Original repo:
[https://github.com/HeroCC/moos-ivp-cc](https://github.com/HeroCC/moos-ivp-cc)

I was building the library for Raspberry Pi 4 using the original instruction, but failed. The main one I use for now is pWebSocketServer, so I disabled the ones I did not use from compiling.

## Dependencies

Run the following in terminal:

```
sudo apt install libsndfile-dev portaudio19-dev libssl-dev libprotobuf-dev libgrpc++-dev liblog4cpp5-dev
```

## Boost 1.5.4

This pWebSocketServer will only build using Boost version 1.5.4 and below.

```
cd
wget http://downloads.sourceforge.net/project/boost/boost/1.54.0/boost_1_54_0.tar.gz
tar -zxvf boost_1_54_0.tar.gz
cd boost_1_54_0
./bootstrap.sh
sudo ./b2 --with=all -j 4 install
```

## Installing

To get my MOOS IvP tree, you will need to do the following:
 * Clone this repo next to your normal `moos-ivp/` directory
 * Run `git submodule update --init` from within this tree
 * Run `./build.sh` and wait for the compilation to complete
 * Add the newly generated `bin/` directory to your $PATH environmental variable

## What's Included 
> Note that I might have disabled some MOOS app from compiling.
 * pWebSocketServer: A websocket server that forwards and receives moos mail to connected applications (see MOOSMobile)
 * iMumbleClient: A VoIP bridge for the Mumble protocol
 * uRaspiMon: A wrapper for raspbian tools to measure system temperature and throttling status
 * iNeptune (and related NMEA tools): An interface between Seebyte's Neptune platform and MOOS
 * MIT 2.680 applications and missions
