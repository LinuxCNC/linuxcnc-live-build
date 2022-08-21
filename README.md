# Build live boot ISO

This is the set of recipes and configuration needed to build the
LinuxCNC live boot images.

## Fetch the code:

    git clone https://github.com/LinuxCNC/linuxcnc-live-build
    cd linuxcnc-live-build
    git checkout bookworm

## Install dependencies and build native architecture ISO

This will build for the same architecture as the machine where it is
running:

    sudo apt install live-build
    lb config
    sudo lb build
    
The resulting iso end up as images{desktop} .


## Install dependencies and cross build for foreign architecture ISO

It is also possible to cross build to a different architecture, using
QEMU and by removing the old configuration.  This is the recipe for
armhf, used on Raspberry Pi 4:

    sudo apt install qemu-user-static
    sudo modprobe binfmt_misc
    sudo lb clean
    rm -rf config
    git checkout config
    lb config \
      --architecture arm64 \
      --linux-flavours arm64 \
      --bootstrap-qemu-arch arm64 \
      --bootstrap-qemu-static /usr/bin/qemu-arm-static \
      --compression gzip \
      --gzip-options '-9 --rsyncable' \
      --mode debian \
      --binary-filesystem fat32 \
      --binary-images hdd \
      --chroot-filesystem squashfs \
      --hdd-size 4096 \
      --initramfs live-boot \
      --system live
    sudo lb build
