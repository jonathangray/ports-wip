# $OpenBSD: Makefile,v 1.20 2016/03/18 20:49:28 naddy Exp $

COMMENT=	posix library for the lua language
V=		33.4.0
DISTNAME=	luaposix-${V}
EPOCH=		0
CATEGORIES=	devel

GH_ACCOUNT=	luaposix
GH_PROJECT=	luaposix
GH_TAGNAME=	release-v${V}

# Public domain
PERMIT_PACKAGE_CDROM=	Yes
NO_TEST=		Yes

MODULES=		lang/lua

.if "${MODLUA_VERSION}" == "5.1"
RUN_DEPENDS=		devel/lua-bit32
.endif

CONFIGURE_STYLE=	gnu

CONFIGURE_ENV+=		LUA=${MODLUA_BIN} \
			LUA_INCLUDE=-I${MODLUA_INCL_DIR}

.include <bsd.port.mk>
