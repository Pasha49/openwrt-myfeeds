#
# Copyright (C) 2006-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=liboning
PKG_VERSION:=5.9.6
PKG_RELEASE:=1

PKG_SOURCE:=oning-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/kkos/oniguruma/releases/download/v$(PKG_VERSION)/
PKG_HASH:=d5642010336a6f68b7f2e34b1f1cb14be333e4d95c2ac02b38c162caf44e47a7
PKG_MAINTAINER:=
PKG_LICENSE:=
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/liboning
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=Oniguruma is a modern and flexible regular expressions library
  URL:=https://github.com/kkos/oniguruma
endef

define Package/oniguruma/description
	Oniguruma is a modern and flexible regular expressions library. 
	It encompasses features from different regular expression
	implementations that traditionally exist in different languages.
endef
define Build/Compile
	$(call Build/Compile/Default)
endef
define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/onig*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libonig.{a,so*} $(1)/usr/lib/
	$(CP) $(PKG_BUILD_DIR)/oniguruma.pc $(1)/usr/lib/pkgconfig/
endef

define Build/UninstallDev
	rm -rf \
	$(STAGING_DIR)/usr/include/onig*.h \
	$(STAGING_DIR)/usr/lib/libonig.{a,so*}
endef

define Package/liboning/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libonig.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,liboning))
