PORTNAME=	mpl-interactions
DISTVERSION=	0.21.0
PORTREVISION=	1
CATEGORIES=	graphics python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DISTNAME=	mpl_interactions-${DISTVERSION}

MAINTAINER=	makc@FreeBSD.org
COMMENT=	Simple interactive Matplotlib plots

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}matplotlib>0:math/py-matplotlib@${PY_FLAVOR}

USES=		python:3.7+
USE_PYTHON=	autoplist distutils

.include <bsd.port.mk>
