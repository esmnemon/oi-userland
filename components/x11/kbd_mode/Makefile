#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Aurelien Larcher
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=           kbd_mode
COMPONENT_VERSION=        7.5
COMPONENT_FMRI=           system/keyboard/kbd_mode
COMPONENT_CLASSIFICATION= System/Hardware
COMPONENT_SUMMARY=  			kbd_mode - utility to change the Solaris kernel key event reporting mode
COMPONENT_SRC=      			src
COMPONENT_PROJECT_URL = 	https://hg.java.net/hg/solaris-x11~x-s12-clone
COMPONENT_LICENSE=      	Oracle
COMPONENT_LICENSE_FILE= 	kbd_mode.license

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/justmake.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

COMPONENT_COMMON_ENV= CC=$(CC)
COMPONENT_COMMON_ENV+= CFLAGS="$(CFLAGS)"
COMPONENT_COMMON_ENV+= LDFLAGS="$(LDFLAGS)"

XLOCK_BINDIR.32 =	$(USRBINDIR)
XLOCK_BINDIR.64 =	$(USRBINDIR64)

COMPONENT_BUILD_ENV+= $(COMPONENT_COMMON_ENV)
COMPONENT_BUILD_ARGS= VPATH=$(SOURCE_DIR) -f $(SOURCE_DIR)/Makefile
COMPONENT_INSTALL_ENV+= INSTALL=$(INSTALL)
COMPONENT_INSTALL_ENV+= DESTDIR=$(PROTO_DIR)
COMPONENT_INSTALL_ENV+= PREFIX=$(USRDIR)
COMPONENT_INSTALL_ENV+= bindir=$(XLOCK_BINDIR.$(BITS))
COMPONENT_INSTALL_ENV+= mandir=$(USRSHAREMANDIR)

build: $(BUILD_32) $(BUILD_64)

install: $(INSTALL_32) $(INSTALL_64)

test: $(NO_TESTS)


REQUIRED_PACKAGES += system/library
