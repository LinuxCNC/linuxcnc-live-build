# linuxcnc-live-build

    [ -x /usr/bin/git ] || sudo apt install git
    git clone https://github.com/LinuxCNC/linuxcnc-live-build
    cd linuxcnc-live-build
    git checkout bookworm
    [ -x /usr/bin/lb ] || sudo apt install live-build
    lb config
    sudo lb build
    
    Puts the .iso file in images{desktop}
