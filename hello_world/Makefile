# Sample package makefile for a trivial demo package

include $(TOPDIR)/rules.mk

PKG_NAME:=hellodemo
PKG_VERSION:=1
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/hellodemo
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Demo package for SDK
  MAINTAINER:= Karl Palsson <karlp@etactica.com>
  DEPENDS:= #nothing! perhaps +libmodbus or similar
endef

define Package/hellodemo/description
 This package is used simply to demonstrate how to use the SDK.
It is a basic, traditional C hello world style program.
endef

# Override Prepare as our source is included in our package
define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/hellodemo/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hello $(1)/usr/bin
endef

$(eval $(call BuildPackage,hellodemo))



