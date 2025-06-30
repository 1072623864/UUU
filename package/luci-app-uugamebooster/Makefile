
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/luci.mk

PKG_NAME:=luci-app-uugamebooster
PKG_RELEASE:=1
PKG_VERSION:=1.0.0
PKG_LICENSE:=GPL-2.0
PKG_MAINTAINER:=YourName <you@example.com>

LUCI_TITLE:=LuCI support for UU Game Booster
LUCI_DEPENDS:=+uugamebooster
PKG_ARCH:=all

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include/luci

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/luci.mk

define Package/luci-app-uugamebooster/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) files/uugamebooster.init $(1)/etc/init.d/uugamebooster
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller
	$(INSTALL_DATA) files/controller/* $(1)/usr/lib/lua/luci/controller/
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view/uugamebooster
	$(INSTALL_DATA) files/view/* $(1)/usr/lib/lua/luci/view/uugamebooster/
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	$(INSTALL_DATA) files/i18n/* $(1)/usr/lib/lua/luci/i18n/
endef

$(eval $(call BuildPackage,luci-app-uugamebooster))
