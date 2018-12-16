#
# Copyright (C) 2006-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=onig
PKG_VERSION:=6.9.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/kkos/oniguruma/releases/download/v$(PKG_VERSION)/
PKG_HASH:=a9240b653d02e8cfc52db48e8c4224426e528e1faa09b65e8ca08a197fad210b
PKG_MAINTAINER:=
PKG_LICENSE:=

PKG_FIXUP:=libtool autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/oniguruma
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

TARGET_CFLAGS += $(FPIC)

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

define Package/confuse/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libonig.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,oniguruma))
