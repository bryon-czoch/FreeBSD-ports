PORTNAME=	nmsg
PORTVERSION=	1.0.1
PORTREVISION=	1
CATEGORIES=	net
MASTER_SITES=	FARSIGHT LOCAL/truckman/farsight

MAINTAINER=	truckman@FreeBSD.org
COMMENT=	Network message encapsulation system

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/COPYRIGHT

LIB_DEPENDS=	libprotobuf-c.so:devel/protobuf-c \
		libwdns.so:dns/wdns

GNU_CONFIGURE=	yes
USES=		gmake libtool pathfix pkgconfig
USE_LDCONFIG=	yes
CONFIGURE_ARGS=	--with-pkgconfigdir='$${exec_prefix}/libdata/pkgconfig'
INSTALL_TARGET=	install-strip

PORTDOCS=	*

# The DOXYGEN option is best effort.
# If doxygen is installed, it will get used if the option is set to NO.
OPTIONS_DEFINE=		YAJL ZEROMQ DOXYGEN EXAMPLES MANPAGES DOCS
OPTIONS_DEFAULT=	YAJL ZEROMQ DOXYGEN MANPAGES
OPTIONS_SUB=		yes

YAJL_DESC=		JSON support via libyajl
YAJL_CONFIGURE_WITH=	yajl
YAJL_LIB_DEPENDS=	libyajl.so:devel/yajl
ZEROMQ_DESC=		ZeroMQ support
ZEROMQ_CONFIGURE_WITH=	libzmq
ZEROMQ_LIB_DEPENDS=	libzmq.so:net/libzmq4

ALL_TARGET=	all
DOXYGEN_IMPLIES=	DOCS
DOXYGEN_BUILD_DEPENDS=	doxygen:devel/doxygen
DOXYGEN_ALL_TARGET=	html-local
DOCBOOK_XML=	${LOCALBASE}/share/xml/docbook/4.2
MANPAGES_BUILD_DEPENDS=	xsltproc:textproc/libxslt \
			docbook-xml>0:textproc/docbook-xml \
			docbook-xsl-ns>0:textproc/docbook-xsl-ns
MANPAGES_CONFIGURE_WITH=	xsltproc

post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	cd ${WRKSRC} && ${INSTALL_DATA} README.md README.FILTERS.md \
		${STAGEDIR}${DOCSDIR}

post-install-DOXYGEN-on:
	(cd ${WRKSRC}/doc/doxygen && \
	${COPYTREE_SHARE} html ${STAGEDIR}${DOCSDIR})

post-install-EXAMPLES-on:
	@${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	(cd ${WRKSRC}/examples && \
	${INSTALL_DATA} *.c *.py ${STAGEDIR}${EXAMPLESDIR})

.include <bsd.port.mk>
