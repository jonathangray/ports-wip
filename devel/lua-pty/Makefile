#	$OpenBSD$

COMMENT=	pty control for lua
V=		1.2.1
DISTNAME=	lpty-${V}-1
PKGNAME=	lua-pty-${V}
CATEGORIES=	devel

HOMEPAGE=	http://tset.de/lpty/
MAINTAINER=	Jonathan Gray <jsg@openbsd.org>

MODULES=	lang/lua

FLAVORS=	lua52 lua53
FLAVOR?=

# MIT
PERMIT_PACKAGE_CDROM=Yes

MASTER_SITES=	http://tset.de/downloads/

NO_TEST=	Yes

do-build:
	cd ${WRKSRC} && ${MODLUA_BIN} ${WRKSRC}/mkinc.lua expectsrc
	${CC} ${CFLAGS} -fPIC -I${MODLUA_INCL_DIR} -I${WRKSRC} -shared \
	    ${WRKSRC}/lpty.c -o ${WRKBUILD}/lpty.so

do-install:
	${INSTALL_DATA_DIR} ${MODLUA_LIBDIR}
	${INSTALL_DATA} ${WRKBUILD}/lpty.so ${MODLUA_LIBDIR}

.include <bsd.port.mk>
