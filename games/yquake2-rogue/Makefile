# $OpenBSD$

COMMENT=	'Ground Zero' for Yamagi Quake II
N=		yquake2-rogue
V=		2.03
PKGNAME=	${N}-${V}
DISTNAME=	quake2-rogue-${V}
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
	${INSTALL_DATA_DIR} ${PREFIX}/share/yquake2/rogue
	${INSTALL_PROGRAM} ${WRKBUILD}/release/game.so \
	    ${PREFIX}/share/yquake2/rogue/

.include <bsd.port.mk>
