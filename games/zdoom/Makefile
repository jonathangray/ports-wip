#	$OpenBSD$

COMMENT=	enhanced port of the DOOM source code
CATEGORIES=	games x11

GH_ACCOUNT=	rheit
GH_PROJECT=	zdoom
GH_TAGNAME=	2.8.1

HOMEPAGE=	http://zdoom.org

# 'doomlic.txt' and 'BUILDLIC.TXT' don't grant (m)any rights
# though the doom source was later relicensed under GPLv2
PERMIT_PACKAGE_CDROM=	No
PERMIT_PACKAGE_FTP=	No
PERMIT_DISTFILES_FTP=	Yes

WANTLIB += SDL2  bz2 c 
WANTLIB += jpeg m openal pthread sndfile stdc++ z

LIB_DEPENDS=	audio/openal \
		audio/libsndfile \
		devel/sdl2 \
		graphics/jpeg \
		archivers/bzip2

MODULES=	devel/cmake
CONFIGURE_ARGS=	-DNO_GTK:Bool=True \
		-DCMAKE_CXX_FLAGS="${CXXFLAGS} -I${X11BASE}/include -Dunix"

post-extract:
		cp ${FILESDIR}/wordexp.{c,h} ${WRKSRC}/src/sound/

do-install:
		${INSTALL_DATA_DIR} ${PREFIX}/share/zdoom
		${INSTALL_DATA} ${WRKBUILD}/zdoom.pk3 ${PREFIX}/share/zdoom
		${INSTALL_PROGRAM} ${WRKBUILD}/zdoom ${PREFIX}/bin

.include <bsd.port.mk>
