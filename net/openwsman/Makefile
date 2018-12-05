#	$OpenBSD$

COMMENT=	Openwsman server implementation and client api

CATEGORIES=	net

V=		2.6.9
GH_ACCOUNT=	Openwsman
GH_PROJECT=	openwsman
GH_TAGNAME=	v${V}
PKGNAME=	openwsman-${V}

# BSD
PERMIT_PACKAGE_CDROM=	Yes

SHARED_LIBS +=  wsman			0.0 # 1.0
SHARED_LIBS +=  wsman_client		0.0 # 4.0
SHARED_LIBS +=  wsman_clientpp		0.0 # 1.0
SHARED_LIBS +=  wsman_curl_client_transport 0.0 # 1.0
SHARED_LIBS +=  wsman_server		0.0 # 1.0
SHARED_LIBS +=  wsman_file_auth		0.0 # 1.0
SHARED_LIBS +=  redirect		0.0 # 1.0
SHARED_LIBS +=  wsman_cim_plugin	0.0 # 1.0
SHARED_LIBS +=  wsman_identify_plugin	0.0 # 1.0
SHARED_LIBS +=  wsman_test		0.0 # 1.0

MODULES=	devel/cmake \
		lang/python

CONFIGURE_ARGS=	-DUSE_PAM:Bool=False \
		-DBUILD_PERL:Bool=False \
		-DBUILD_RUBY:Bool=False \
		-DBUILD_JAVA:Bool=False \
		-DBUILD_PYTHON:Bool=False \
		-DBUILD_PYTHON3:Bool=False

BUILD_DEPENDS=	devel/swig
LIB_DEPENDS=	textproc/libxml \
		net/sblim-sfcc \
		net/curl

WANTLIB += ${COMPILER_LIBCXX} c cmpisfcc crypto curl m ssl xml2

.include <bsd.port.mk>
