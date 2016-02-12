include $(TOPDIR)/rules.mk

PKG_NAME:=leveldb
PKG_VERSION:=v1.18
PKG_RELEASE:=1

PKG_SOURCE:=iojs-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://iojs.org/dist/latest/
PKG_SHA256SUM:=e84a649858e6f5c1458c0d5d7bf1952f78e93a26ea6bc519222e92e43e2fadde
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

define Package/leveldb
  DEPENDS:=+snappy
  SECTION:=libs
  SUBMENU:=database
  TITLE:=A fast and lightweight key/value database library
  URL:=https://code.google.com/p/leveldb/
endef

define Package/leveldb/description
A fast and lightweight key/value database library
endef

define Build/Compile
  $(call Build/Compile/Default)
endef

define Package/iojs/install
  $(MAKE) $(PKG_JOBS) -C $(PKG_BUILD_DIR) DESTDIR="$(1)" install
endef

$(eval $(call BuildPackage,leveldb))
