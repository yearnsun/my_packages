include $(TOPDIR)/rules.mk

PKG_NAME:=vlmcsd
PKG_VERSION=svn1111
PKG_RELEASE:=2017-06-17

PKG_MAINTAINER:=Hotbird64

PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/Wind4/vlmcsd.git
PKG_SOURCE_VERSION:=550df56794aa201fd2dd08153431ca20da2e6846

include $(INCLUDE_DIR)/package.mk

define Package/vlmcsd
	SECTION:=net
	CATEGORY:=Network
	TITLE:=vlmcsd for openwrt
	URL:=https://forums.mydigitallife.info/threads/50234
	DEPENDS:=+libc +libpthread
endef

MAKE_FLAGS += \
	VLMCSD_VERSION="$(PKG_VERSION)" \
	vlmcsd

define Package/vlmcsd/description
	vlmcsd is a KMS Emulator in C.
endef

define Package/vlmcsd/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/vlmcsd $(1)/usr/sbin/vlmcsd
endef

define Package/vlmcsd/prerm
#!/bin/sh
	if [ -f /etc/dnsmasq.conf ]; then
		sed -i '/^srv-host=_vlmcs\._tcp/d' /etc/dnsmasq.conf
	fi
	if [ -n "$$(awk '/vlmcsd\.log/{print $$0}' /etc/crontabs/root)" ];then
		sed -i '/vlmcsd\.log/d' /etc/crontabs/root >/dev/null 2>&1
	fi
	rm -rf /var/log/vlmcsd.log 2>/dev/null
	if pidof vlmcsd >/dev/null; then
	killall vlmcsd
	fi
	exit 0
endef

$(eval $(call BuildPackage,vlmcsd))
