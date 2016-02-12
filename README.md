# openwrt-feeds
Here are my OpenWRT packages with updates.

## Repository usage
1. Move into the openwrt folder

  ```bash
  cd /path/to/openwrt
  ```
2. Add this repository into the feed configuration file

  ```bash
  echo "src-git hongkongkiwi_feed https://github.com/hongkongkiwi/openwrt-feeds.git" >> feeds.conf.default
  ```
3. Update and install the new feed packages

  ```bash
  ./scripts/feeds update -a
  ./scripts/feeds install -a
  ```

## Package List

* brcm2708-gpu-fw-custom (kernel/firmware) - Raspberry Pi Specific
* luci-shadowsocks (luci/luci-shadowsocks)
* autossh (network/services)
* c-icap (network/services)
* c-icap-modules (network/services)
* chinadns (network/services)
* redsocks2 (network/services)
* shadowsocks (network/services)
* shadowvpn (network/services)
* squid (network/services)
* squidguard (network/services)
* ufdbguard (network/services)
* ubus-json-server (network)
* dialog (utilities)
* jxcore (utilities)
* nodejs (utilities)
* rpi-extendfs (utilities) - Raspberry Pi Specific
* rpi-update (utilities) - Raspberry Pi Specific
