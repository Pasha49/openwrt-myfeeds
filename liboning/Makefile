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

PKG_FIXUP:=autoreconf -vfi

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libonig/default
  SECTION:=libs
  CATEGORY:=Libraries
  URL:=https://github.com/kkos/oniguruma
endef

define Package/libonig
  $(call Package/libonig/default)
  TITLE:=Oniguruma is a modern and flexible regular expressions library
endef


define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/local/include/onig*.h \
		$(1)/usr/include/

	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/local/lib/libonig*.{a,so*} \
		$(1)/usr/lib/

	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/local/lib/pkgconfig/libonig.pc \
		$(1)/usr/lib/pkgconfig/
endef

define Package/libonig/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/local/lib/libonig*.{a,so*} \
		$(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,libonig))
