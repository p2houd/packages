include $(TOPDIR)/rules.mk

PKG_NAME:=accel-ppp
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/accel-ppp/accel-ppp.git
PKG_SOURCE_DATE:=2024-04-21
PKG_SOURCE_VERSION:=6afbc5075a3cf88a47f01c9051dd0a7fdcb06299
PKG_MIRROR_HASH:=skip
CMAKE_INSTALL:=1

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=

PKG_MAINTAINER:=Dmitriy Eshenko <dima@accel-ppp.org>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_BINARY_DIR:=$(PKG_BUILD_DIR)/../test
CMAKE_OPTIONS += -DCMAKE_CROSSCOMPILING=1 -DCMAKE_INSTALL_LIBDIR=lib/accel-ppp


define Package/accel-ppp
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=VPN
  DEPENDS:=+libpcre +libopenssl +libnl
  TITLE:=Protocol PPTP/PPPoE/L2TP/SSTP
endef

define Package/accel-ppp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/usr/etc
	$(INSTALL_DIR) $(1)/usr/lib/accel-ppp
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(CP) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin/
	$(CP) $(PKG_INSTALL_DIR)/usr/lib64/accel-ppp/* $(1)/usr/lib/accel-ppp/
endef

$(eval $(call BuildPackage,accel-ppp))
