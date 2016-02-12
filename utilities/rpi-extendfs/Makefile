#
# Copyright (C) 2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=rpi-extendfs
PKG_VERSION:=0.2
PKG_RELEASE:=1
PKG_REV:=29c702a6c6592904294fe2ff88f04bd075c4cf07

PKG_SOURCE:=$(PKG_REV).tar.gz
PKG_SOURCE_URL:=https://github.com/rpi-openwrt/rpi-extendfs/archive/
PKG_MD5SUM:=3113daf3e1f5923dff17571394dec193
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_REV)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/rpi-extendfs
  SECTION:=rpi-utilities
  CATEGORY:=Raspberry Pi
  SUBMENU:=Utilities
  TITLE:=rpi-extendfs
  DEPENDS:=+fdisk +resize2fs +dialog
endef

define Package/rpi-extendfs/description
	Menu-driven dialog using utility for extending size of root filesystem.
	Similar to raspi-config from other distributions, but at the moment does
	nothing more than resizing of root filesystem. Original project name was
	rpi-config, which was supposed to be port of raspi-config for OpenWrt.
	Instead of options from raspi-config, this only supports root fs extending. Currently.
endef

define Build/Configure
	true
endef

define Build/Compile
	true
endef

define Build/Install
	true
endef

define Package/rpi-extendfs/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rpi-extendfs $(1)/sbin/
endef

$(eval $(call BuildPackage,rpi-extendfs))
