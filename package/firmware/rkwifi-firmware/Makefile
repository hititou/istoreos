
include $(TOPDIR)/rules.mk

PKG_NAME:=rkwifi-firmware
PKG_VERSION:=2023-12-06
PKG_RELEASE:=1

PKG_SOURCE_VERSION:=9bd1a056ba1e4e97bb2f5a0d39df7c9f35bd618a
PKG_HASH:=dba5047b33fe4b740d184148a27ed8ab3b7e9692f2dcd35aed5a6da2d29a193f
PKG_SOURCE_URL_FILE:=$(PKG_SOURCE_VERSION).tar.gz
PKG_SOURCE:=rkwifi-firmware-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/jjm2473/rockchip_wlan/archive/

PKG_MAINTAINER:=jjm2473 <jjm2473@gmail.com>

include $(INCLUDE_DIR)/package.mk

TAR_OPTIONS+= --strip-components 1
TAR_CMD=$(HOST_TAR) -C $(1) $(TAR_OPTIONS)

define Package/rkwifi-firmware
  SECTION:=firmware
  CATEGORY:=Firmware
  TITLE:=Rockchip wifi firmware
  DEPENDS:=@TARGET_rockchip
endef

define Build/Compile

endef

define Package/rkwifi-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/rkwifi
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/config.txt $(1)/lib/firmware/rkwifi/

	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/fw_bcm43455c0_ag.bin $(1)/lib/firmware/rkwifi/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/nvram_ap6255.txt $(1)/lib/firmware/rkwifi/

	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/fw_bcm43456c5_ag.bin $(1)/lib/firmware/rkwifi/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/nvram_ap6256.txt $(1)/lib/firmware/rkwifi/

	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/fw_bcm4356a2_ag.bin $(1)/lib/firmware/rkwifi/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/firmware/rkwifi/nvram_ap6356.txt $(1)/lib/firmware/rkwifi/
endef

$(eval $(call BuildPackage,rkwifi-firmware))

