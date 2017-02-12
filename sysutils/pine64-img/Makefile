COMMENT=	Combined boot0, ATF and u-boot for pine64
GH_ACCOUNT=	apritzel
GH_PROJECT=	pine64
GH_COMMIT=	0558929fa4964fb20725d641655f840071aa945e

DISTNAME=	pine64-img-20160710
PKGNAME=	pine64-img-20172010
CATEGORIES=	sysutils

PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	No
PERMIT_DISTFILES_FTP=	No

PKG_ARCH=		*

BUILD_DEPENDS=	sysutils/pine64-boot0 \
		sysutils/pine64-atf \
		sysutils/u-boot,aarch64

NO_TEST=	Yes
USE_GMAKE=	Yes

BOOT0=${LOCALBASE}/share/u-boot/pine64_plus/boot0.bin
ATF=${LOCALBASE}/share/u-boot/pine64_plus/bl31.bin
UBOOT=${LOCALBASE}/share/u-boot/pine64_plus/u-boot.bin

do-build:
	cd ${WRKSRC}/tools && \
	    ${SETENV} ${MAKE_ENV} ${MAKE_PROGRAM} ${MAKE_FLAGS} \
	        -f ${MAKE_FILE} boot0img
	${WRKSRC}/tools/boot0img -B ${BOOT0} -s ${ATF} -a 0x44008 -d trampoline64:0x44000 \
	    -u ${UBOOT} -e -p 100 -o ${WRKBUILD}/pine64.img

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/u-boot/pine64_plus/
	${INSTALL_DATA} ${WRKBUILD}/pine64.img \
	    ${PREFIX}/share/u-boot/pine64_plus/

.include <bsd.port.mk>
