# Created by: dburr@FreeBSD.org
# $FreeBSD$

PORTNAME=	sharefonts
PORTVERSION=	0.10
PORTREVISION=	5
CATEGORIES=	x11-fonts
MASTER_SITES=	http://download.gimp.org/pub/%SUBDIR%/ \
		ftp://ftp.sunet.se/pub/gnu/%SUBDIR%/   \
		http://ftp.gwdg.de/pub/misc/grafik/gimp/%SUBDIR%/ \
		http://mirrors.xmission.com/gimp/%SUBDIR%/
MASTER_SITE_SUBDIR=	gimp/fonts

MAINTAINER=	olgeni@FreeBSD.org
COMMENT=	Collection of shareware ATM fonts from the CICA archives

RESTRICTED=	Shareware: cannot be distributed without prior authorization

NO_BUILD=	yes

USES=		fonts
SUB_FILES=	pkg-message

do-install:
	@${MKDIR} ${STAGEDIR}${FONTSDIR}
	${INSTALL_DATA} ${WRKDIR}/sharefont/* ${STAGEDIR}${FONTSDIR}

.include <bsd.port.mk>
