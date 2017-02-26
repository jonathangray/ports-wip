# $OpenBSD$

COMMENT=	Go TrueType fonts
GH_ACCOUNT=	golang
GH_PROJECT=	image
GH_COMMIT=	c8ae36c95e9b791117fe12e441bb0047b52eaa24
DISTNAME=	go-image-20170224
PKGNAME=	${DISTNAME:S/image/fonts/}
HOMEPAGE=	https://blog.golang.org/go-fonts

CATEGORIES=	fonts x11

# BSD
PERMIT_PACKAGE_CDROM=	Yes

NO_BUILD=	Yes
NO_TEST=	Yes

FONTDIR=	${PREFIX}/share/fonts/go
DOCDIR=		${PREFIX}/share/doc/go-fonts

do-install:
	${INSTALL_DATA_DIR} ${FONTDIR} ${DOCDIR}
	${INSTALL_DATA} ${WRKDIST}/font/gofont/ttfs/*.ttf ${FONTDIR}
	${INSTALL_DATA} ${WRKDIST}/font/gofont/ttfs/README ${DOCDIR}

.include <bsd.port.mk>
