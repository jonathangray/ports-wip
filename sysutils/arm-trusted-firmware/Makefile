COMMENT=	ARM Trusted Firmware
GH_ACCOUNT=	ARM-software
GH_PROJECT=	arm-trusted-firmware
GH_COMMIT=	4fd4af26cb650d34876c058a7142c91233ba5475
VERSION=	20170517

DISTNAME=	${GH_PROJECT}-${VERSION}
PKGNAME=	${GH_PROJECT}-${VERSION}
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
	        -f ${MAKE_FILE} V=1 PLAT=rk3399 bl31

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/atf/rk3399/
	${INSTALL_DATA} ${WRKBUILD}/build/rk3399/release/bl31.bin \
	    ${PREFIX}/share/atf/rk3399/

.include <bsd.port.mk>
