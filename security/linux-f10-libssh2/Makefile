# Created by: bsam
# $FreeBSD: head/security/linux-f10-libssh2/Makefile 340722 2014-01-22 17:00:46Z mat $

PORTNAME=	libssh2
PORTVERSION=	0.18
PORTREVISION=	1
CATEGORIES=	security linux
MASTER_SITES=	CRITICAL/rpm/${LINUX_RPM_ARCH}/fedora/${LINUX_DIST_VER}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Library implementing the SSH2 protocol (Linux Fedora 10)

CONFLICTS=	linux-f8-libssh2-[0-9]*

USE_LINUX=	f10
USE_LINUX_RPM=	yes
USE_LINUX_APPS=	openssl

RPMVERSION=	7.fc9
USE_LDCONFIG=	yes

PLIST_FILES=	usr/lib/libssh2.so.1 usr/lib/libssh2.so.1.0.0
DOCSDIR=	${PREFIX}/usr/share/doc/${PORTNAME}-${PORTVERSION}
PORTDOCS=	AUTHORS COPYING ChangeLog NEWS README
DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr

.include <bsd.port.mk>
