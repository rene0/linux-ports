# Created by: bsam
# $FreeBSD: head/security/linux-f10-nss/Makefile 340722 2014-01-22 17:00:46Z mat $

PORTNAME=	nss
PORTVERSION=	3.12.3.99.3
PORTREVISION=	2
CATEGORIES=	security linux
MASTER_SITES=	CRITICAL/rpm/${LINUX_RPM_ARCH}/fedora/${LINUX_DIST_VER}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Network Security Services (Linux Fedora 10)

ONLY_FOR_ARCHS=	i386 amd64
USE_LINUX=	f10
USE_LINUX_RPM=	yes
USE_LINUX_APPS=	nspr sqlite3

RPMVERSION=	2.10.6.fc10
USE_LDCONFIG=	yes

DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr

.include <bsd.port.mk>
