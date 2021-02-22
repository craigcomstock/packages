#
# Copyright (C) 2021 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ed
PKG_VERSION:=1.17
PKG_RELEASE:=0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.lz
PKG_SOURCE_URL:=http://gnu.askapache.com/ed/
PKG_HASH:=71de39883c25b6fab44add80635382a10c9bf154515b94729f4a6529ddcc5e54
PKG_MAINTAINER:=Craig Comstock <craig@unreasonablefarm.org>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)$(PKG_VERSION)
PKG_BUILD_PARALLEL:=1


HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/$(PKG_NAME)$(PKG_VERSION)
HOST_BUILD_PARALLEL:=1

UNPACK_CMD=tar --lzip --strip-components=1 -C $(1) -xf "$(DL_DIR)/$(PKG_SOURCE)"

include $(INCLUDE_DIR)/package.mk

define Package/ed
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Ed - A line-oriented text editor
  URL:=http://www.gnu.org/software/ed/
  SUBMENU:=Editors
endef

define Package/ed/description
  ed - the standard unix editor
endef

define Build/Configure
	$(call Build/Configure/Default)
endef

define Package/ed/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ed $(1)/usr/bin/
endef

$(eval $(call BuildPackage,ed))
