#	$OpenBSD$

COMMENT=	Small Footprint CIM Client
CATEGORIES=	net

DISTNAME=	sblim-sfcc-2.2.8
EXTRACT_SUFX=	.tar.bz2
MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=sblim/sblim-sfcc/}

HOMEPAGE=	http://sblim.sourceforge.net/wiki/index.php/Sfcc

SHARED_LIBS +=  cimcClientXML		0.0
SHARED_LIBS +=  cimcclient		0.0
SHARED_LIBS +=  cmpisfcc		0.0

# Eclipse Public License
PERMIT_PACKAGE_CDROM=	Yes

LIB_DEPENDS=		net/curl

CONFIGURE_STYLE=	gnu
CONFIGURE_ENV=		CPPFLAGS="-I${LOCALBASE}/include" \
			LDFLAGS="-L${LOCALBASE}/lib"

WANTLIB=	crypto curl nghttp2 pthread ssl z

.include <bsd.port.mk>
