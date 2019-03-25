# $OpenBSD$

COMMENT=	Vulkan ICD loader

SHARED_LIBS += vulkan	0.0 # 1.1

GH_TAGNAME=	sdk-${V}
GH_ACCOUNT=	KhronosGroup
GH_PROJECT=	Vulkan-Loader
V=		1.1.101.0
PKGNAME=	vulkan-loader-${V}

CATEGORIES=	devel graphics

HOMEPAGE=	https://www.khronos.org/vulkan/

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += m pthread

BUILD_DEPENDS=	graphics/vulkan-headers
RUN_DEPENDS=	graphics/vulkan-headers

CONFIGURE_ARGS=		-DBUILD_WSI_WAYLAND_SUPPORT:Bool=False

MODULES=	devel/cmake \
		lang/python
MODPY_VERSION=	${MODPY_DEFAULT_VERSION_3}
MODPY_RUNDEP=	No

.include <bsd.port.mk>
