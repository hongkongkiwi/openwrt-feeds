#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=leveldb
PKG_VERSION:=1.18
PKG_RELEASE:=1
PKG_LICENSE:=BSD
PKG_MAINTAINER:=Dmitri Bogomolov <4glitch@gmail.com>

PKG_USE_MIPS16:=0

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/google/$(PKG_NAME)/archive/
PKG_MD5SUM:=73770de34a2a5ab34498d2e05b2b7fa0

PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/leveldb
	DEPENDS:=+libpthread +snappy
	SECTION:=libs
	CATEGORY:=Libraries
	SUBMENU:=database
	TITLE:=A fast and lightweight key/value database library
	URL:=http://leveldb.org/
endef

define Package/leveldb/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_BUILD_DIR)/libleveldb.so* $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/libmemenv.so* $(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/leveldb/helpers/
	$(CP) $(PKG_BUILD_DIR)/include/leveldb/*.h $(1)/usr/include/leveldb/
	$(CP) $(PKG_BUILD_DIR)/helpers/memenv/*.h $(1)/usr/include/leveldb/helpers/
	$(call Package/$(PKG_NAME)/install, $(1))
endef

$(eval $(call BuildPackage,leveldb))
