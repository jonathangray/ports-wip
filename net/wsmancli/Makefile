#	$OpenBSD$

COMMENT=	Openwsman command line client

CATEGORIES=	net

V=		2.6.0
GH_ACCOUNT=	Openwsman
GH_PROJECT=	wsmancli
GH_TAGNAME=	v${V}
PKGNAME=	wsmancli-${V}

# BSD
PERMIT_PACKAGE_CDROM=	Yes

AUTOCONF_VERSION=	2.69
AUTOMAKE_VERSION=	1.12

WANTLIB=	c crypto curl iconv lzma m nghttp2 pthread ssl wsman \
		wsman_client wsman_curl_client_transport xml2 z

BUILD_DEPENDS=		devel/libtool
LIB_DEPENDS=		net/curl \
			textproc/libxml \
			net/openwsman \
			converters/libiconv \
			archivers/xz

CONFIGURE_STYLE=	gnu

pre-configure:
	cd ${WRKSRC} && env AUTOCONF_VERSION=${AUTOCONF_VERSION} \
	    AUTOMAKE_VERSION=${AUTOMAKE_VERSION} /bin/sh ./bootstrap

.include <bsd.port.mk>
