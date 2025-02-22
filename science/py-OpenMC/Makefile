PORTNAME=	OpenMC
DISTVERSIONPREFIX=	v
DISTVERSION=	0.13.0
CATEGORIES=	science
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Monte Carlo neutron and photon transport simulation code (Python)

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

PY_DEPENDS=	${PYNUMPY} \
		${PYTHON_PKGNAMEPREFIX}h5py>0:science/py-h5py@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}ipython>0:devel/ipython@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}lxml>0:devel/py-lxml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}matplotlib>0:math/py-matplotlib@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pandas>0:math/py-pandas@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}scipy>0:science/py-scipy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}uncertainties>0:math/py-uncertainties@${PY_FLAVOR}
BUILD_DEPENDS=	openmc>0:science/openmc \
		${PY_DEPENDS}
RUN_DEPENDS=	openmc>0:science/openmc \
		${PY_DEPENDS}

USES=		python
USE_PYTHON=	distutils concurrent autoplist

USE_GITHUB=	yes
GH_ACCOUNT=	${PORTNAME:tl}-dev
GH_PROJECT=	${PORTNAME:tl}

PLIST_FILES=	${PYTHON_SITELIBDIR}/openmc/lib/libopenmc.so

post-install:
	# strip
	@${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/openmc/data/*.so
	# link the library
	@${LN} -s ${LOCALBASE}/lib/libopenmc.so ${STAGEDIR}${PYTHON_SITELIBDIR}/openmc/lib/libopenmc.so

.include <bsd.port.mk>
