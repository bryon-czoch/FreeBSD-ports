PORTNAME=	openarc
PORTVERSION=	1.0.0.b3.20201016
PORTREVISION=	1
CATEGORIES=	www

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Library to validate use of certain identifiers in messages

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	autoconf-archive>0:devel/autoconf-archive
LIB_DEPENDS=	libjansson.so:devel/jansson

USES=		autoreconf gmake libtool pkgconfig ssl
USE_LDCONFIG=	yes

USE_GITHUB=	yes
GH_ACCOUNT=	trusteddomainproject
GH_PROJECT=	OpenARC
GH_TAGNAME=	eb430db

GNU_CONFIGURE=	yes

USE_RC_SUBR=	${PORTNAME}

INSTALL_TARGET=	install-strip

OPTIONS_DEFINE=	DOCS

PORTDOCS=	*

.include <bsd.port.mk>
