# Created by: Martin Wilke <miwi@FreeBSD.org>

PORTNAME=	gmpc-shout
PORTVERSION=	0.20.0
PORTREVISION=	8
CATEGORIES=	audio
MASTER_SITES=	http://download.sarine.nl/Programs/gmpc/${PORTVERSION}/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Shoutcast stream for gmpc

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING

DEPRECATED=	Abandonware, last release in 2011 and upstream is dead
EXPIRATION_DATE=2022-06-30

LIB_DEPENDS=	libmpd.so:audio/libmpd \
		libcairo.so:graphics/cairo
BUILD_DEPENDS=	${LOCALBASE}/libdata/pkgconfig/gmpc.pc:audio/gmpc
RUN_DEPENDS=	gmpc:audio/gmpc \
		ogg123:audio/vorbis-tools

GNU_CONFIGURE=	yes
CPPFLAGS+=	-I${LOCALBASE}/include
LIBS+=		-L${LOCALBASE}/lib
USES=		gettext gmake gnome libtool pkgconfig
USE_GNOME=	intltool glib20 gtk20 libxml2
INSTALL_TARGET=	install-strip

.include <bsd.port.mk>
