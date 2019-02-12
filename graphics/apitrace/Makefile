# $OpenBSD$

COMMENT=	tools for tracing OpenGL

GH_ACCOUNT=	apitrace
GH_PROJECT=	apitrace
GH_TAGNAME=	7.1

CATEGORIES=	graphics

HOMEPAGE=	https://apitrace.github.io

# MIT
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	Qt5Core Qt5Gui Qt5Network Qt5WebKit Qt5WebKitWidgets \
		Qt5Widgets X11 c m pthread \
		${COMPILER_LIBCXX}

COMPILER=	base-clang ports-gcc

MODULES=	devel/cmake \
		x11/qt5

LIB_DEPENDS=	x11/qt5/qtwebkit

.include <bsd.port.mk>
