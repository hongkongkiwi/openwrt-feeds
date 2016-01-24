# 
# Copyright (C) 2012-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=brcm2708-gpu-fw-custom
PKG_REV:=d3e6f4a27d87c5229ad6c74fa9022a9451046add
PKG_VERSION:=20150620
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_REV).tar.gz
PKG_SOURCE_URL:=https://github.com/Hexxeh/rpi-firmware/archive/
PKG_MD5SUM:=9620351c37b4aa63c1e2531451daadf5

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)/rpi-firmware-$(PKG_REV)

include $(INCLUDE_DIR)/package.mk

define Package/brcm2708-gpu-fw-custom
  SECTION:=boot
  CATEGORY:=Boot Loaders
  DEPENDS:=@(!PACKAGE_brcm2708-gpu-fw) +ldconfig +ldconfig-backbone
  TITLE:=brcm2708-gpu-fw-custom
endef

define Package/brcm2708-gpu-fw-custom/description
  GPU and kernel boot firmware for brcm2708.
endef

define Build/Compile
	true
endef

define Package/brcm2708-gpu-fw-custom/install
	$(INSTALL_DIR) $(1)/opt
	$(CP) $(PKG_BUILD_DIR)/vc/softfp/opt/vc $(1)/opt/
	$(INSTALL_DIR) $(1)/etc/ld.so.conf.d
	echo "/opt/vc/lib" > $(1)/etc/ld.so.conf.d/vc.conf
endef

define Build/InstallDev
	$(CP) $(PKG_BUILD_DIR)/bootcode.bin $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/COPYING.linux $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/LICENCE.broadcom $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start_cd.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup_cd.dat $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/start_x.elf $(KERNEL_BUILD_DIR)
	$(CP) $(PKG_BUILD_DIR)/fixup_x.dat $(KERNEL_BUILD_DIR)
endef

$(eval $(call BuildPackage,brcm2708-gpu-fw-custom))
