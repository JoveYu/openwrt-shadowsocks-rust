include $(TOPDIR)/rules.mk

PKG_NAME:=luci-app-shadowsocks-rust
PKG_VERSION:=1.0.0
PKG_RELEASE:=1
PKG_LICENSE:=GPL-3.0
PKG_MAINTAINER:=Jove Yu <yushijun110@gmail.com>

LUCI_TITLE:=LuCI support for Shadowsocks Rust
LUCI_DEPENDS:=+ucode +ucode-mod-fs +ucode-mod-uci
LUCI_PKGARCH:=all

include $(TOPDIR)/feeds/luci/luci.mk

# call BuildPackage - OpenWrt buildroot signature
