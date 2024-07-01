include $(TOPDIR)/rules.mk

PKG_NAME:=cloak
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/cbeuw/Cloak.git
PKG_SOURCE_VERSION:=v2.8.0
PKG_MIRROR_HASH:=skip

PKG_BUILD_DEPENDS:=golang/host
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=

PKG_MAINTAINER:=Andy Wang <cbeuw.andy@gmail.com>

GO_PKG:=github.com/cbeuw/Cloak

include $(INCLUDE_DIR)/package.mk
include ../../lang/golang/golang-package.mk

define Package/cloak
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=VPN
  TITLE:=Pluggable transport protocol
  DEPENDS:=$(GO_ARCH_DEPENDS)
endef

GO_PKG_BUILD_VARS += GO111MODULE=auto

define Package/cloak/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(GO_PKG_BUILD_BIN_DIR)/ck-server $(1)/usr/sbin/
	$(INSTALL_BIN) $(GO_PKG_BUILD_BIN_DIR)/ck-client $(1)/usr/sbin/
endef

$(eval $(call GoBinPackage,cloak))
$(eval $(call BuildPackage,cloak))
