SPK_NAME = spip
SPK_VERS = 3.1.8
# SPK_REV = 2
SPK_ICON = src/logo-spip2.gif
DSM_UI_DIR = app

# DEPENDS  = cross/$(SPK_NAME)
DEPENDS  = cross/$(SPK_NAME)

MAINTAINER = emthanh
DESCRIPTION = SPIP is a publishing system for the Internet in which great importance is attached to collaborative working, to multilingual environments, and to simplicity of use for web authors.
DESCRIPTION_FRE = SPIP est un système de publication pour l’Internet qui s’attache particulièrement au fonctionnement collectif, au multilinguisme et à la facilité d’emploi.
ADMIN_URL = /spip/
RELOAD_UI = yes
DISPLAY_NAME = spip
CHANGELOG = 3.1.8

HOMEPAGE   = https://www.spip.net
LICENSE    = Apache License 2.0 or GPL 2

INSTALLER_SCRIPT = src/installer.sh
SSS_SCRIPT       = src/dsm-control.sh

INSTALL_DEP_SERVICES = apache-web
START_DEP_SERVICES = apache-web
INSTUNINST_RESTART_SERVICES = apache-web

INSTALL_PREFIX = /usr/local/$(SPK_NAME)

POST_STRIP_TARGET = spip_extra_install

# Pure PHP package, make sure ARCH is not defined
override ARCH=

include ../../mk/spksrc.spk.mk

.PHONY: spip_extra_install
spip_extra_install:
	install -m 755 -d $(STAGING_DIR)/app
	install -m 644 src/app/config $(STAGING_DIR)/app/config
