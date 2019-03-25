# $OpenBSD$

COMMENT=	Vulkan Validation Layers

GH_TAGNAME=	sdk-${V}
GH_ACCOUNT=	KhronosGroup
GH_PROJECT=	Vulkan-ValidationLayers
V=		1.1.101.0
PKGNAME=	vulkan-validation-layers-${V}

CATEGORIES=	devel graphics

HOMEPAGE=	https://www.khronos.org/vulkan/

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${COMPILER_LIBCXX} m

BUILD_DEPENDS=	graphics/glslang \
		graphics/vulkan-headers \
		graphics/spirv-tools

MODULES=	devel/cmake \
		lang/python
MODPY_VERSION=	${MODPY_DEFAULT_VERSION_3}
MODPY_RUNDEP=	No

CONFIGURE_ARGS+=	-DGLSLANG_INSTALL_DIR="${LOCALBASE}" \
			-DBUILD_WSI_WAYLAND_SUPPORT:Bool=False

.include <bsd.port.mk>
