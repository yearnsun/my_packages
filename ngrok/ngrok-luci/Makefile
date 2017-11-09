#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-ngrokc
PKG_VERSION:=1.4.1
PKG_RELEASE:=1
PKG_MAINTAINER:=
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk

define Package/luci-app-ngrokc
	SECTION:=luci
	CATEGORY:=LuCI
	SUBMENU:=3. Applications
	TITLE:=LuCI app for ngrokc
	DEPENDS:=+ngrokc
	PKGARCH:=all
endef

define Package/luci-app-ngrokc/description
	This package contains LuCI configuration pages for ngrokc.
endef

define Build/Compile
endef

define Package/luci-app-ngrokc/install
	$(CP) ./files/* $(1)
endef

$(eval $(call BuildPackage,luci-app-ngrokc))
