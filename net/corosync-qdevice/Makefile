#corosync-qdevice
include $(TOPDIR)/rules.mk
 
PKG_NAME:=corosync-qdevice
PKG_VERSION:=3.0.3
PKG_RELEASE:=1
 
PKG_SOURCE:=corosync-qdevice-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/corosync/corosync-qdevice/releases/download/v$(PKG_VERSION)/
PKG_HASH:=0a4705abd17af795287ad3bb18c0abacf3c0027222e45f149cb9bebeb6056926
PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:=nss corosync
 
include $(INCLUDE_DIR)/package.mk
 
define Package/corosync-qdevice
  SECTION:=corosync
  CATEGORY:=Corosync
  TITLE:=Corosync Qdevice
  DEPENDS:=+corosync +libnss
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/share/pkgconfig
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/share/pkgconfig/corosync-qdevice.pc $(1)/usr/share/pkgconfig
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef

define Package/corosync-qdevice/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/* $(1)/usr/sbin
endef
 
$(eval $(call BuildPackage,corosync-qdevice))

