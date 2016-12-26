# $OpenBSD$

COMMENT=	'The Reckoning' for Yamagi Quake II
N=		yquake2-xatrix
V=		2.04
PKGNAME=	${N}-${V}
DISTNAME=	quake2-xatrix-${V}
CATEGORIES=	games

HOMEPAGE=	http://www.yamagi.org/quake2/
MASTER_SITES=	http://deponie.yamagi.org/quake2/
EXTRACT_SUFX=	.tar.xz

# GPLv2
PERMIT_PACKAGE_CDROM=   Yes

RUN_DEPENDS=	games/yquake2

MAKE_ENV+=	VERBOSE=1
USE_GMAKE=	Yes

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/yquake2
	${INSTALL_DATA_DIR} ${PREFIX}/share/yquake2/xatrix
	${INSTALL_PROGRAM} ${WRKBUILD}/release/game.so \
	    ${PREFIX}/share/yquake2/xatrix/

.include <bsd.port.mk>
