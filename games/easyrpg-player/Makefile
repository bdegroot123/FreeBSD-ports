# Created by: Dmitry Marakasov <amdmi3@FreeBSD.org>
# $FreeBSD$

PORTNAME=	easyrpg-player
PORTVERSION=	0.4.1
CATEGORIES=	games

MAINTAINER=	amdmi3@FreeBSD.org
COMMENT=	RPG Maker 2000/2003 and EasyRPG games interpreter

LICENSE=	GPLv3+
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libfreetype.so:print/freetype2 \
		libpng.so:graphics/png \
		liblcf.so:games/liblcf
BUILD_DEPENDS=	asciidoc:textproc/asciidoc \
		${LOCALBASE}/include/boost/shared_ptr.hpp:devel/boost-libs

BROKEN_FreeBSD_9=	does not build

USE_GITHUB=	yes
GH_ACCOUNT=	EasyRPG
GH_PROJECT=	Player

USES=		autoreconf compiler:c++11-lib gmake libtool localbase pkgconfig
GNU_CONFIGURE=	yes
USE_XORG=	pixman
USE_SDL=	sdl2 mixer2

PORTDOCS=	AUTHORS README

OPTIONS_DEFINE=	DOCS

.include <bsd.port.pre.mk>

.if ${OPSYS} == FreeBSD && ${OSVERSION} < 1000000
CONFIGURE_ENV+=	ZLIB_CFLAGS=" " ZLIB_LIBS=-lz
.endif

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
.for f in ${PORTDOCS}
	${INSTALL_DATA} ${WRKSRC}/${f} ${STAGEDIR}${DOCSDIR}/
.endfor

.include <bsd.port.post.mk>
