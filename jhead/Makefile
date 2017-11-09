#
# Copyright (C) 2009-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=jhead
PKG_VERSION:=3.00
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=http://www.sentex.net/~mwandel/jhead
PKG_MD5SUM:=

include $(INCLUDE_DIR)/package.mk

define Package/jhead
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Exif Jpeg header manipulation tool
  URL:= http://www.sentex.net/~mwandel/jhead/
endef

define Package/jhead/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/jhead $(1)/usr/bin/
endef

$(eval $(call BuildPackage,jhead))
