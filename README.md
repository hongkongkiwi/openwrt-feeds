# openwrt-feeds
Here are my OpenWRT packages with updates.

## Repository usage
1. Move into the openwrt folder

  ```bash
  cd /path/to/openwrt
  ```
2. Add this repository into the feed configuration file

  ```bash
  echo "src-git extra_packages https://github.com/hongkongkiwi/openwrt-feeds.git" >> feeds.conf.default
  ```
3. Update and install the new feed packages

  ```bash
  ./scripts/feeds update -a
  ./scripts/feeds install -a
  ```

## Package List
