# $OpenBSD$

COMMENT=	bit32 compatibility module for Lua 5.1
CATEGORIES=	devel

V=		5.3.0
DISTNAME=	${GH_TAGNAME}
PKGNAME=	lua-bit32-${V}

GH_ACCOUNT=	keplerproject
GH_PROJECT=	lua-compat-5.2
GH_TAGNAME=	bitlib-${V}

MAINTAINER=	Jonathan Gray <jsg@openbsd.org>

MODULES=	lang/lua
NO_TEST=	Yes

FLAVORS=	luajit52

# MIT
PERMIT_PACKAGE_CDROM=	Yes

do-build:
	${CC} ${CPPFLAGS} ${CFLAGS} -fPIC -shared \
	    -I${MODLUA_INCL_DIR} -I${WRKDIST}/c-api \
	    ${WRKDIST}/lbitlib.c -o ${WRKDIST}/bit32.so

do-install:
	${INSTALL_DATA_DIR} ${MODLUA_LIBDIR}
	${INSTALL_DATA} ${WRKSRC}/bit32.so ${MODLUA_LIBDIR}

.include <bsd.port.mk>
