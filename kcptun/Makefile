#
# Copyright © 2016 Daniel Fu
# Copyright © 2017 EasyPi Software Foundation
#
# This is free software, licensed under the MIT License.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=kcptun
PKG_VERSION:=20171021
PKG_RELEASE:=1

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=EasyPi Software Foundation

ifeq ($(ARCH),mipsel)
	PKG_ARCH:=mipsle
	MD5SUM:=eda5483cc2fd335b13ba1b7c91a2d09ac16beb4f
endif
ifeq ($(ARCH),mips)
	PKG_ARCH:=mips
	MD5SUM:=c4d42c1a214b75a5c3129dff2188ab5c26d73ecf
endif
ifeq ($(ARCH),i386)
	PKG_ARCH:=386
	MD5SUM:=7fdfa465f78675b733f699d0a6643fae
endif
ifeq ($(ARCH),x86_64)
	PKG_ARCH:=amd64
	MD5SUM:=dc98db3f64b297a75e1c1a12143d1ccf54d963f4
endif

PKG_SOURCE:=$(PKG_NAME)-linux-$(PKG_ARCH)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/xtaci/kcptun/releases/download/v$(PKG_VERSION)
PKG_MD5SUM:=$(MD5SUM)
PKG_CAT:=zcat

include $(INCLUDE_DIR)/package.mk

define Package/kcptun
	SECTION:=net
	CATEGORY:=Network
	TITLE:=An extremely simple udp tunnel based on KCP
	URL:=https://github.com/xtaci/kcptun
endef

define Package/kcptun/description
An extremely simple udp tunnel based on KCP.
endef

define Build/Compile
endef

define Package/kcptun/postinst
endef

define Package/kcptun/conffiles
/etc/config/kcptun
endef

define Package/kcptun/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(BUILD_DIR)/client_linux_$(PKG_ARCH) $(1)/usr/bin/ssr-kcptun
endef

$(eval $(call BuildPackage,kcptun))
