# USAGE:

## First clone it

    git clone git@github.com:Lupino/rpi-chroot.git
    cd rpi-chroot

## Second edit the rpi-config

    export ROOT=${HOME}/chroot-raspbian-armhf
    export MIRROR=http://mirror.nus.edu.sg/raspbian/raspbian
    export SCRIPTROOT=`dirname $0`

    export RPI_INIT=${SCRIPTROOT}/rpi-init
    export PASSWD=raspberry
    export USER=rpi

## Build the rootfs

    ./rpi-build-rootfs

## Enter the chroot

    ./rpi-chroot

# Scripts details

* `rpi-build-rootfs` build the base chroot env.
* `rpi-init` the init script, run on the rpi-build-rootfs
* `rpi-chroot` the chroot script you run it to enter the chroot. you also `rpi-chroot [command]`
* `rpi-install-kernel` install the kernel for the chroot. make sure it can run on the raspberry pi board.

# Denpend

    sudo apt-get install qemu-user-static debootstrap

# Install to a SD disk

    ./rpi-install-kernel
    # split the SD disk two partent 50M fat and ext4 left
    # copy boot to the first partent and other to the next.
