# Created by: Kubilay Kocak <koobs@FreeBSD.org>

PORTNAME=	pysha3
DISTVERSION=	1.0.2
CATEGORIES=	security python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	bofh@FreeBSD.org
COMMENT=	SHA-3 (Keccak) for Python

LICENSE=	PSFL
LICENSE_FILE=	${WRKSRC}/LICENSE

BROKEN_mips64=		fails to compile: KeccakP-1600-opt64.c: error: Not yet implemented

# Actually Python 2.7,3.4+
USES=		python:3.6+
USE_PYTHON=	autoplist distutils

post-install:
	${STRIP_CMD} ${STAGEDIR}${PYTHONPREFIX_SITELIBDIR}/_pysha3*.so

do-test:
	@cd ${TEST_WRKSRC} && ${SETENV} ${TEST_ENV} ${PYTHON_CMD} ${PYDISTUTILS_SETUP} test

.include <bsd.port.mk>
