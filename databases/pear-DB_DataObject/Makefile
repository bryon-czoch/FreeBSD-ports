# Created by: Antonio Carlos Venancio Junior (<antonio@php.net>)

PORTNAME=	DB_DataObject
PORTVERSION=	1.11.5
PORTREVISION=	1
CATEGORIES=	databases pear

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	SQL Builder, Object Interface to Database Tables

LICENSE=	PHP301
LICENSE_FILE=	${WRKSRC}/docs/LICENCE.txt

RUN_DEPENDS=	${PEAR_PKGNAMEPREFIX}Date>=1.4.3:devel/pear-Date@${PHP_FLAVOR}

USES=		pear

CONFLICTS_INSTALL=	php*-pear-DB_DataObject

NO_ARCH=	yes

OPTIONS_DEFINE=	DB MDB2 VALIDATE
OPTIONS_DEFAULT=DB
DB_DESC=	DB support
MDB2_DESC=	MDB2 support
VALIDATE_DESC=	Validate support

DB_RUN_DEPENDS=		${PEAR_PKGNAMEPREFIX}DB>=1.7.0:databases/pear-DB@${PHP_FLAVOR}
MDB2_RUN_DEPENDS=	${PEAR_PKGNAMEPREFIX}MDB2>=2.0.0.r1:databases/pear-MDB2@${PHP_FLAVOR}
VALIDATE_RUN_DEPENDS=	${PEAR_PKGNAMEPREFIX}Validate>=0.1.1:devel/pear-Validate@${PHP_FLAVOR}

.include <bsd.port.mk>
