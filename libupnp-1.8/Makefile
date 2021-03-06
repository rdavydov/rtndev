#
# Copyright (C) 2011-2017 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# Used by gerbera package
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libupnp-1.8
PKG_VERSION:=1.8.1
PKG_REV:=b8a81b0324a9e08add5066c5fe39ed70e6ef31a6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/mrjimenez/pupnp.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libupnp-1.8
	SECTION:=libs
	CATEGORY:=Libraries
	DEPENDS:=+libpthread
	TITLE:=UPnP 1.8 SDK library
	URL:=http://pupnp.sourceforge.net/
	MAINTAINER:=Entware team, http://entware.net
endef

define Package/libupnp-1.8/description
 The portable SDK for UPnP Devices (libupnp 1.8).
endef

CONFIGURE_ARGS += \
	--enable-reuseaddr \
	--disable-samples

define Build/InstallDev
	$(INSTALL_DIR) $(1)/opt/include
	$(CP) $(PKG_INSTALL_DIR)/opt/include/upnp-1.8 $(1)/opt/include
	$(INSTALL_DIR) $(1)/opt/lib
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/lib{ixml,upnp}-1.8.{a,so*} $(1)/opt/lib
	$(INSTALL_DIR) $(1)/opt/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/pkgconfig/libupnp-1.8.pc $(1)/opt/lib/pkgconfig
endef

define Package/libupnp-1.8/install
	$(INSTALL_DIR) $(1)/opt/lib
	$(CP) $(PKG_INSTALL_DIR)/opt/lib/lib{ixml,upnp}-1.8.so* $(1)/opt/lib
endef

$(eval $(call BuildPackage,libupnp-1.8))
