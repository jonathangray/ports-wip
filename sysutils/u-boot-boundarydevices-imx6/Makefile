#	$OpenBSD$

COMMENT=	boundary devices U-Boot firmware
GH_ACCOUNT=	boundarydevices
GH_PROJECT=	u-boot-imx6
GH_COMMIT=	2f30f6f1a1f04ed056d9a9342764c2a6e59afe64
VERSION=	2017.01.20170116

DISTNAME=	u-boot-boundarydevices-imx6-${VERSION}
PKGNAME=	${DISTNAME}
CATEGORIES=	sysutils

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

PKG_ARCH=	*

BUILD_DEPENDS=	devel/dtc
MAKE_ENV=	KBUILD_VERBOSE=1

BUILD_DEPENDS+=	devel/arm-none-eabi/gcc-linaro
MAKE_ENV+=	CROSS_COMPILE="arm-none-eabi-"

USE_GMAKE=	Yes
NO_TEST=	Yes

IMX=\
	nit6xlite \
	nit6xlite1g \
	nitrogen51_vm_256m \
	nitrogen51_vm_512m \
	nitrogen6_lum_dl1 \
	nitrogen6_max_4gr0 \
	nitrogen6_max \
	nitrogen6_max_dl2g \
	nitrogen6_max_dl4g \
	nitrogen6_scm \
	nitrogen6_som2_s1g \
	nitrogen6_som2_s512m \
	nitrogen6_vm1g \
	nitrogen6_vm \
	nitrogen6dl2g \
	nitrogen6dl \
	nitrogen6q2g \
	nitrogen6q \
	nitrogen6q_fl \
	nitrogen6q_som2_1g \
	nitrogen6q_som2_2g \
	nitrogen6q_som2_4g \
	nitrogen6qp_max \
	nitrogen6qp_som2_4g \
	nitrogen6s1g \
	nitrogen6s \
	nitrogen6sx \
	nitrogen7
BOARDS=\
	${IMX}

FILES=\
	MLO \
	SPL \
	u-boot \
	u-boot.img \
	u-boot.bin \
	u-boot-sunxi-with-spl.bin \
	u-boot.imx \
	u-boot-spl.kwb

do-build:
.for BOARD in ${BOARDS}
	cd ${WRKSRC} && \
	    mkdir -p build/${BOARD} && \
	    ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} ${MAKE_FLAGS} \
	        O="build/${BOARD}" \
	        -f ${MAKE_FILE} "${BOARD}"_defconfig && \
	    ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} ${MAKE_FLAGS} \
	        O="build/${BOARD}" \
	        -f ${MAKE_FILE} ${ALL_TARGET}
.endfor

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/u-boot-boundarydevices-imx6
.for BOARD in ${BOARDS}
	${INSTALL_DATA_DIR} ${PREFIX}/share/u-boot-boundarydevices-imx6/${BOARD}
	-cd ${WRKSRC}/build/${BOARD} && \
	    cp ${FILES} ${PREFIX}/share/u-boot-boundarydevices-imx6/${BOARD}/
.endfor

.include <bsd.port.mk>
