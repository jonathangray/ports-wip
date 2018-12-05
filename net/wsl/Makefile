#	$OpenBSD$

COMMENT=	Wsman Shell Command Line

V=		0.2.2
DISTNAME=	wsl-${V}-1.el6.src.rpm
PKGNAME=	wsl-${V}
CATEGORIES=	net
EXTRACT_SUFX=
WRKSRC=		${WRKDIR}/wsl-${V}
WRKDIST=	${WRKSRC}

MASTER_SITES=	https://linux.dell.com/files/wsl/

CMDS=	viwsl wsl wslcred wslecn wslenum wslget wslid wslinvoke \
	wslput wxmlgetvalue

# BSD
PERMIT_PACKAGE_CDROM=	Yes

BUILD_DEPENDS=	rpm-*|rpm2cpio-*:converters/rpm2cpio
RUN_DEPENDS=	textproc/libxml \
		net/curl \
		shells/bash

NO_BUILD=	Yes
NO_TEST=	Yes

do-extract:
	cd ${WRKDIR} && \
		${LOCALBASE}/bin/rpm2cpio ${FULLDISTDIR}/${DISTNAME} | cpio -id
	cd ${WRKDIR} && \
		${TAR} zxf wsl-${V}.tar.gz

post-extract:
.for cmd in ${CMDS}
	sed -i "s,/bin/bash,/usr/bin/env bash," \
		${WRKSRC}/${cmd}
	sed -i "s,/etc/wsl,${LOCALBASE}/share/wsl," \
		${WRKSRC}/${cmd}
.endfor
	${SUBST_CMD} ${WRKSRC}/wsl-functions ${WRKSRC}/wxmlgetvalue

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/wsl
	${INSTALL_SCRIPT} ${WRKSRC}/wsl-functions ${PREFIX}/share/wsl
	${INSTALL_SCRIPT} ${WRKSRC}/wsl-ws2textc.xsl ${PREFIX}/share/wsl
.for cmd in ${CMDS}
	${INSTALL_SCRIPT} ${WRKSRC}/${cmd} ${PREFIX}/bin
.endfor

.include <bsd.port.mk>
