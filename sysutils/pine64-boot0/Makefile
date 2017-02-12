COMMENT=	closed pine64 boot0
GH_ACCOUNT=	longsleep
GH_PROJECT=	build-pine64-image
GH_COMMIT=	68d0fa955b858e7e6b5bbc90752faa5cf5605ab7
VERSION=	20170110

DISTNAME=	${GH_PROJECT}-${VERSION}
PKGNAME=	pine64-boot0-${VERSION}
CATEGORIES=	sysutils

PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	No
PERMIT_DISTFILES_FTP=	No

PKG_ARCH=		*

NO_BUILD=		Yes
NO_TEST=		Yes

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/u-boot/pine64_plus/
	${INSTALL_DATA} ${WRKSRC}/blobs/boot0.bin \
	    ${PREFIX}/share/u-boot/pine64_plus/

.include <bsd.port.mk>
