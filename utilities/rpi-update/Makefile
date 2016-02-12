#
# Copyright (C) 2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=rpi-update
PKG_VERSION:=0.41
PKG_RELEASE:=1
PKG_REV:=22636d3dd58a127560d93a1eeedf087910aa090c

PKG_SOURCE:=$(PKG_REV).tar.gz
PKG_SOURCE_URL:=https://github.com/rpi-openwrt/rpi-update/archive/
PKG_MD5SUM:=836f14525de65295bb16cf107f3968cf
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_REV)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/rpi-update
  SECTION:=rpi-utilities
  CATEGORY:=Raspberry Pi
  SUBMENU:=Utilities
  TITLE:=rpi-update
  DEPENDS:=+kmod-nls-iso8859-1 +kmod-nls-cp437 +kmod-fs-vfat +curl
endef

define Package/rpi-update/description
	An easier way to update the firmware of your Raspberry Pi.
	OpenWrt port of rpi-update from https://github.com/Hexxeh/rpi-update.
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

define Package/rpi-update/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/rpi-update $(1)/sbin/
endef

$(eval $(call BuildPackage,rpi-update))
