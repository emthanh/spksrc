PKG_NAME = SPIP
PKG_VERS = v3.1.8
PKG_EXT = zip
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://files.spip.net/spip/archives
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS =

HOMEPAGE = https://www.spip.net/
COMMENT  = .
LICENSE  = GPL

EXTRACT_PATH = $(WORK_DIR)
CONFIGURE_TARGET = nop
COMPILE_TARGET = nop
INSTALL_TARGET = myInstall

override ARCH=

include ../../mk/spksrc.cross-cc.mk

.PHONY: myInstall
myInstall:
	mkdir -p $(STAGING_INSTALL_PREFIX)/share/spip
	mkdir -p $(WORK_DIR)/spip/plugins/auto
	cat $(WORK_DIR)/../src/htaccess-patch >> $(WORK_DIR)/spip/.htaccess
	cat $(WORK_DIR)/spip/htaccess.txt >> $(WORK_DIR)/spip/.htaccess
	tar -cf - -C $(WORK_DIR)/spip . | tar -xf - -C $(STAGING_INSTALL_PREFIX)/share/spip
	chmod -R 755 $(STAGING_INSTALL_PREFIX)/share/spip
	chmod 777 $(STAGING_INSTALL_PREFIX)/share/spip
