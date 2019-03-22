# $OpenBSD$

COMMENT=	API and commands for processing SPIR-V

GH_COMMIT=	61dfd8492b6e324f684863ecbd79c299a06e6517
GH_ACCOUNT=	KhronosGroup
GH_PROJECT=	SPIRV-Tools
V=		2019.2
DISTNAME=	spirv-tools-${V}

CATEGORIES=	devel graphics

HOMEPAGE=	https://www.khronos.org/vulkan/

# Apache 2.0
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ${COMPILER_LIBCXX} c m

BUILD_DEPENDS=	graphics/spirv-headers

CONFIGURE_ARGS=		-DSPIRV_HEADER_DIR:String="${LOCALBASE}"

MODULES=	devel/cmake

.include <bsd.port.mk>
