PORTNAME=		kallisto
DISTVERSIONPREFIX=	v
DISTVERSION=		0.48.0
PORTEPOCH=		1
CATEGORIES=		biology

MAINTAINER=	jwb@FreeBSD.org
COMMENT=	Quantify abundances of transcripts from RNA-Seq data

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/license.txt

BUILD_DEPENDS=	autoconf>=0:devel/autoconf
LIB_DEPENDS=	libhdf5.so:science/hdf5 \
		libsz.so:science/szip \
		libhts.so:biology/htslib

USES=		cmake:noninja compiler:c++11-lang gmake localbase:ldflags
USE_GITHUB=	yes
GH_ACCOUNT=	pachterlab

SUB_FILES=	kallisto-test

PORTEXAMPLES=		*
PLIST_FILES=		bin/kallisto
EXAMPLES_PLIST_FILES=	bin/kallisto-test

# hdf5 is being phased out and is no longer built in by default, but is still
# required for Sleuth (requires kallisto bootstrap estimates) and other
# downstream tools.  Remove this after Sleuth et al catch up.
CMAKE_ARGS+=		-DUSE_HDF5:BOOL=ON
MAKE_JOBS_UNSAFE=	yes
LDFLAGS+=		-lhts -lz

OPTIONS_DEFINE=	EXAMPLES

post-extract:
	${RM} -rf ${WRKSRC}/ext/htslib

post-install-EXAMPLES-on:
	${INSTALL_SCRIPT} ${WRKDIR}/kallisto-test ${STAGEDIR}${PREFIX}/bin
	cd ${WRKSRC}/test && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR}

.include <bsd.port.mk>
