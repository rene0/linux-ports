# Created by: Stas Timokhin <devel@stasyan.com>
# $FreeBSD: head/security/linux-f10-gnutls/Makefile 340722 2014-01-22 17:00:46Z mat $

PORTNAME=	gnutls
PORTVERSION=	2.4.2
PORTREVISION=	2
CATEGORIES=	security linux

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	GNU Transport Layer Security library

FORBIDDEN=	http://www.freshports.org/vuxml.php?vid=f645aa90-a3e8-11e3-a422-3c970e169bc2

USE_LINUX=	f10
USE_LINUX_RPM=	yes
USE_LINUX_APPS=	libtasn1 libgcrypt libgpg-error

RPMVERSION=	5.fc10
USE_LDCONFIG=	yes

PLIST_SUB=	PORTVERSION="${PORTVERSION}"
DESCR=		${PORTSDIR}/security/gnutls/pkg-descr

.include <bsd.port.mk>
