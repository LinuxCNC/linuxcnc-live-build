# linuxcnc-live-build

    [ -x /usr/bin/git ] || sudo apt install git
    git clone https://github.com/LinuxCNC/linuxcnc-live-build
    cd linuxcnc-live-build
    git checkout bookworm
    [ -x /usr/bin/lb ] || sudo apt install live-build
    lb config
    sudo su
    lb build
    
    Puts the .iso file in images{desktop}
    
# Changes for Bookworm as per 2.9 Getting Linuxcnc Docs
    changed to live build for installer: 	--debian-installer live  (installer was not installing linuxcnc)
    use the repositories at: http://buildbot2.highlab.com/   
    replaced buggy nmtray with network-manager  
    changed READ.me to use su for lb build 
    added  utilities.list to config/package-lists to include some utilities that are useful when following Getting Linuxcnc docs.
    
 # To do
    Add some apt trickery to allow select non-free packages as R8168/R8125 NIC drivers are in non-free because they are not kernel firmware.
    Add QTPYVCP repositories now they have one.
    Add Ethercat repositories now they have an official Debian Repository
    NOTE: external repositories provided as a convenience to users if they wish to use companion products. No Software to be installed by this installer.
