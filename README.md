# linuxcnc-live-build

    [ -x /usr/bin/git ] || sudo apt install git
    git clone https://github.com/LinuxCNC/linuxcnc-live-build
    cd linuxcnc-live-build
    git checkout bookworm
    [ -x /usr/bin/lb ] || sudo apt install live-build
    lb config
    sudo su
    lb build

Puts the .iso file in the ```linuxcnc-live-build``` folder.

# Changes for Bookworm as per 2.9 Getting Linuxcnc Docs
- Changed to live build for installer: ```--debian-installer live``` (installer was not installing linuxcnc).
- Use the repositories at: http://buildbot2.highlab.com/
- Replaced buggy ```nmtray``` with ```network-manager```.
- Changed ```README.md``` to use ```su``` for lb build.
- Added ```ethercat``` repository. To install: ```sudo apt update``` then ```sudo apt install ethercat-master libethercat-dev```. Licencing requirements from the Ethercat Technology Group should be complied with.
- Added ```QTPYVCP``` repository. To install: ```sudo apt update``` then ```sudo apt install python3-qtpyvcp```
- Added ```Probe Basic``` repository. To install: ```sudo apt update``` then ```sudo apt install python3-probe-basic```

- NOTE: External repositories provided as a convenience to users if they wish to use companion products. No Software to be installed by this installer.
   


   
