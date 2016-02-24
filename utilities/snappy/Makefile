#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=snappy
PKG_VERSION:=1.1.3
PKG_RELEASE:=1
PKG_LICENSE:=BSD
PKG_MAINTAINER:=Dmitri Bogomolov <4glitch@gmail.com>

PKG_SOURCE:=snappy-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/google/snappy/releases/download/$(PKG_VERSION)/
PKG_MD5SUM:=7358c82f133dc77798e4c2062a749b73

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/snappy
	DEPENDS:=+libstdcpp
	SECTION:=libs
	CATEGORY:=Libraries
	SUBMENU:=Compression
	TITLE:=A fast compressor/decompressor library
	URL:=https://github.com/google/snappy
endef

Build/Install=$(call Build/Install/Default)

define Package/snappy/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libsnappy.so* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_BUILD_DIR)/*.h $(1)/usr/include/
	$(call Package/$(PKG_NAME)/install, $(1))
endef

$(eval $(call BuildPackage,snappy))
