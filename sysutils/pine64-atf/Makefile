COMMENT=	ARM Trusted Firmware for pine64
GH_ACCOUNT=	apritzel
GH_PROJECT=	arm-trusted-firmware
GH_COMMIT=	cd7fa4893dd204e419a8403a8d1dc1c295e3d698
VERSION=	20161111

DISTNAME=	${GH_PROJECT}-pine64-${VERSION}
PKGNAME=	pine64-atf-${VERSION}
CATEGORIES=	sysutils

PERMIT_PACKAGE_CDROM=	Yes

PKG_ARCH=		*

BUILD_DEPENDS+= devel/arm-none-eabi/gcc-linaro,aarch64
MAKE_ENV+= CROSS_COMPILE="aarch64-none-elf-"
MAKE_ENV+= BUILD_STRING="${VERSION}"

NO_TEST=	Yes
USE_GMAKE=	Yes

do-build:
	cd ${WRKSRC} && \
	    ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} ${MAKE_FLAGS} \
	        -f ${MAKE_FILE} PLAT=sun50iw1p1 DEBUG=1 bl31

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/u-boot/pine64_plus/
	${INSTALL_DATA} ${WRKBUILD}/build/sun50iw1p1/debug/bl31.bin \
	    ${PREFIX}/share/u-boot/pine64_plus/

.include <bsd.port.mk>
