PORTNAME=	nemu
DISTVERSIONPREFIX=	v
DISTVERSION=	3.0.0
PORTREVISION=	2
CATEGORIES=	emulators

MAINTAINER=	arrowd@FreeBSD.org
COMMENT=	Ncurses UI for QEMU

LICENSE=	BSD2CLAUSE

LIB_DEPENDS=	libudev.so:devel/libudev-devd \
		libjson-c.so:devel/json-c

USES=		cmake gettext-runtime gettext-tools gnome libarchive pkgconfig \
		sqlite

USE_GITHUB=	yes
GH_ACCOUNT=	nemuTUI

USE_GNOME=	libxml2

.include <bsd.port.mk>
