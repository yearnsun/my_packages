#
# Copyright (C) 2016-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ariang
PKG_VERSION:=DailyBuild
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/mayswind/AriaNg-DailyBuild.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=bd7faea4ab5989733fa8d82b7f2d59e5bae619ed
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_LICENSE:=LGPL-3.0
PKG_MAINTAINER:=Mazige <gaomin@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/ariang
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Download Manager
  DEPENDS:=
  TITLE:=AriaNg aria2 web frontend
  URL:=https://github.com/mayswind/AriaNg-DailyBuild
  PKGARCH:=all
endef

define Package/ariang/description
	AriaNg is a modern web frontend making aria2 easier to use.
endef

define Build/Compile
endef

define Package/ariang/install
	$(INSTALL_DIR) $(1)/www/ariang
	$(CP) \
		$(PKG_BUILD_DIR)/{css,fonts,js,langs} \
		$(1)/www/ariang
	$(CP) \
		$(PKG_BUILD_DIR)/{index.html,index.manifest} \
		$(1)/www/ariang
endef

$(eval $(call BuildPackage,ariang))
