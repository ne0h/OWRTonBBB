# OpenWRT on BeagleBone Black

## Build

1. Clone OpenWRT repository: `git clone git://git.openwrt.org/openwrt.git`
2. Update LUCI dependencies: `cd openwrt && ./scripts/feeds update packages luci && ./scripts/feeds install -a -p luci`
3. Run `make menuconfig` to install base system or take `config_base-system`
4. Run `make world`

## Notes

* Build LUCI web gui: https://forum.openwrt.org/viewtopic.php?id=16599
