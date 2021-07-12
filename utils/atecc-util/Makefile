
include $(TOPDIR)/rules.mk

PKG_NAME:=atecc-util
PKG_VERSION:=0.4.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/wirenboard/atecc-util.git
PKG_SOURCE_VERSION:=8c156299d9d0b8511247a662e53fc9aa67aa091e

include $(INCLUDE_DIR)/package.mk

define Package/atecc-util
  SECTION:=prism
  CATEGORY:=EVSE
  TITLE:=ATECC508A/608A command line utility
endef

define Build/Prepare
	$(call Build/Prepare/Default,)
endef

define Build/Configure
endef

define Build/Compile
	+$(MAKE_VARS) $(MAKE) -C $(PKG_BUILD_DIR)/$(MAKE_PATH) \
		$(MAKE_FLAGS) atecc
endef

define Package/atecc-util/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/atecc $(1)/usr/bin/
endef

$(eval $(call BuildPackage,atecc-util))
