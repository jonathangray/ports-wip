# $OpenBSD$

COMMENT=	tools for tracing OpenGL
V=		7.1
DISTNAME=	apitrace-${V}
CATEGORIES=	graphics

HOMEPAGE=	http://apitrace.github.io/
MASTER_SITES=	https://github.com/apitrace/apitrace/archive/
DISTFILES=	apitrace-${V}${EXTRACT_SUFX}{${V}${EXTRACT_SUFX}}

WANTLIB=	Qt5Core Qt5Gui Qt5Network Qt5WebKit Qt5WebKitWidgets \
		Qt5Widgets X11 c m pthread \
		${COMPILER_LIBCXX}

COMPILER=	base-clang ports-gcc

# MIT
PERMIT_PACKAGE_CDROM=	Yes

MODULES=	devel/cmake

LIB_DEPENDS=	x11/qt5/qtbase \
		x11/qt5/qtwebkit

.include <bsd.port.mk>
