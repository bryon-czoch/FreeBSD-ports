# Created by: Jonathan Chen <jonc@chen.org.nz>
# $FreeBSD$

PORTNAME=	eclipse
PORTVERSION=	4.21
CATEGORIES=	java devel

# Update to eclipse.platform.releng.aggregator.git git-tag on git.eclipse.org
ECLIPSE_TAG=	R4_21
ECLIPSE_TSTAMP=	20210915-1206

ECLIPSE_SUFX=	${ECLIPSE_TAG}.tar.xz
ECLIPSE_MODULES=jdt/eclipse.jdt \
		jdt/eclipse.jdt.core \
		jdt/eclipse.jdt.core.binaries \
		jdt/eclipse.jdt.debug \
		jdt/eclipse.jdt.ui \
		pde/eclipse.pde.build \
		pde/eclipse.pde.ui \
		platform/eclipse.platform \
		platform/eclipse.platform.common \
		platform/eclipse.platform.debug \
		platform/eclipse.platform.releng \
		platform/eclipse.platform.releng.aggregator \
		platform/eclipse.platform.resources \
		platform/eclipse.platform.runtime \
		platform/eclipse.platform.swt \
		platform/eclipse.platform.swt.binaries \
		platform/eclipse.platform.team \
		platform/eclipse.platform.text \
		platform/eclipse.platform.ua \
		platform/eclipse.platform.ui \
		platform/eclipse.platform.ui.tools \
		equinox/rt.equinox.binaries \
		equinox/rt.equinox.bundles \
		equinox/rt.equinox.framework \
		equinox/rt.equinox.p2
# Each Eclipse module has its own MASTER_SITE
.for M in ${ECLIPSE_MODULES}
MASTER_SITES+=	https://github.com/${GH_ACCOUNT}/${GH_PROJECT}/releases/download/${PORTVERSION}/:${M:C/[\.\/]//g} \
		https://git.eclipse.org/c/${M}.git/snapshot/:${M:C/[\.\/]//g}
DISTFILES+=	${M:C/.*\///}-${ECLIPSE_SUFX}:${M:C/[\.\/]//g}
.endfor

CEF_FILE=	cef_binary_3.3071.1649.g98725e6_linux64_minimal
MASTER_SITES+=	https://cef-builds.spotifycdn.com/:spotify \
		https://github.com/${GH_ACCOUNT}/${GH_PROJECT}/releases/download/${PORTVERSION}/:github
DISTFILES+=	${CEF_FILE}.tar.bz2:spotify

DIST_SUBDIR=	${PORTNAME}

MAINTAINER=	jonc@chen.org.nz
COMMENT=	Eclipse IDE 2020-09

LICENSE=	EPL

ONLY_FOR_ARCHS=	aarch64 amd64 powerpc64 powerpc64le

BUILD_DEPENDS=	git:devel/git@lite \
		${LOCALBASE}/share/java/maven/bin/mvn:devel/maven \
		zip:archivers/zip
LIB_DEPENDS=	libsecret-1.so:security/libsecret \
		libwebkit2gtk-4.0.so:www/webkit2-gtk3
USES=		compiler:c++11-lang gmake pkgconfig gnome
USE_GNOME=	gtk30

USE_GITHUB=	yes
GH_ACCOUNT=	daemonblade
GH_PROJECT=	eclipse-maven-repo

USE_JAVA=	11+

DESKTOP_ENTRIES="Eclipse" \
		"${COMMENT}" \
		"${PORTNAME}" \
		"${PORTNAME}" \
		"Development;IDE;Java;" \
		"false"

SUB_FILES=	${PORTNAME}

MAVEN_ENV=	MAVEN_OPTS=-Xmx1024m CC=${CC} JAVA_HOME=${JAVA_HOME} HOME=${WRKDIR}/githome
MAVEN_ECLIPSE=	-Dmaven.repo.local=${WRKDIR}/${GH_PROJECT}-${PORTVERSION} \
		-Dlocal.cefsource=${WRKDIR}/${CEF_FILE} \
		-Dlocal.patchfiles=${FILESDIR} \
		-Dnative=gtk.freebsd.${ARCH} \
		-DforceContextQualifier=v${ECLIPSE_TSTAMP}

ECLIPSE_RESULT=	eclipse.platform.releng.tychoeclipsebuilder/eclipse.platform.repository/target/products/org.eclipse.sdk.ide-freebsd.gtk.${ARCH}.tar.gz

# Let's abuse this to get to the right place.
WRKSRC_SUBDIR=	../eclipse.platform.releng.aggregator-${ECLIPSE_TAG}

do-build:
	cd ${WRKSRC} && ${SETENV} ${MAVEN_ENV} mvn --offline ${MAVEN_ECLIPSE} -DskipTests clean verify

do-install:
	${MKDIR} ${STAGEDIR}${DATADIR}
	${TAR} -x --directory ${STAGEDIR}${DATADIR}/.. --file ${WRKSRC}/${ECLIPSE_RESULT}
	${INSTALL_SCRIPT} ${WRKDIR}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

# generate dynamic plist, to cater for different ARCHS
post-install:
	cd ${STAGEDIR}${PREFIX} && ${FIND} -s bin/${PORTNAME} share/${PORTNAME} -not -type d >> ${TMPPLIST}
	cd ${STAGEDIR}${PREFIX} && ${FIND} -ds share/${PORTNAME} -type d | ${SED} -e 's,^,@dir ,' >> ${TMPPLIST}

.include <bsd.port.mk>
