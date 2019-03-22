# $OpenBSD$

COMMENT=	Vulkan Utilities and Tools

GH_TAGNAME=	sdk-${V}
GH_ACCOUNT=	KhronosGroup
GH_PROJECT=	Vulkan-Tools
V=		1.1.101.0
PKGNAME=	vulkan-tools-${V}

CATEGORIES=	devel graphics

HOMEPAGE=	https://www.khronos.org/vulkan/

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${COMPILER_LIBCXX} ICE SM X11 Xext c m vulkan xcb

BUILD_DEPENDS=	graphics/glslang \
		graphics/vulkan-headers
LIB_DEPENDS=	graphics/vulkan-loader

MODULES=	devel/cmake

CONFIGURE_ARGS+=	-DGLSLANG_INSTALL_DIR="${LOCALBASE}" \
			-DBUILD_WSI_WAYLAND_SUPPORT:Bool=False

.include <bsd.port.mk>
