# OpenWRT on BeagleBone Black

Current version at this time is `CHAOS CALMER (Bleeding Edge r45702)`.

## Build

1. Clone OpenWRT repository: `git clone git://git.openwrt.org/openwrt.git`
2. Update LUCI dependencies: `cd openwrt && ./scripts/feeds update packages luci && ./scripts/feeds install -a -p luci`
3. Run `make menuconfig` to install base system or make use `config_base-system`
4. Run `make world`

## Install

1. Set up two partitions
    1. Boot partition
        - Id: c; Type: W95 FAT32 (LBA); about 128M
        - Contains bootload and boot kernel image
            - am335x-boneblack.dtb
            - MLO
            - u-boot.img
            - uEnv.txt (not included in openwrt, can be found in this repo)
            - zImage
    2. Root partition
        - Id: 83; Type: Linux; formatted with ext4 (this is important since yout have to define it in `uEnv.txt`)
        - Contains the the root filesystem
2. Copy newly build packages to beaglebone and install them via `opkg install $package`


## Notes

* BeagleBone Black: http://beagleboard.org/black
* General information with mini sd card layout: http://wiki.openwrt.org/toh/beaglebone/black
* Build LUCI web gui: https://forum.openwrt.org/viewtopic.php?id=16599
