# Created by: bsam
# $FreeBSD: head/graphics/linux-f10-png/Makefile 340722 2014-01-22 17:00:46Z mat $

PORTNAME=	png
PORTVERSION=	1.2.37
PORTREVISION=	2
CATEGORIES=	graphics linux
MASTER_SITES=	CRITICAL/rpm/${LINUX_RPM_ARCH}/fedora/${LINUX_DIST_VER}
DISTNAME=	lib${PORTNAME}-${PORTVERSION}-${RPMVERSION}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	RPM of the PNG lib (Linux Fedora 10)

CONFLICTS=	linux-png-[0-9]* linux-f8-png-[0-9]*

ONLY_FOR_ARCHS=	i386 amd64
USE_LINUX=	f10
USE_LINUX_RPM=	yes
LINUX_NAME=	libpng

RPMVERSION=	1.fc10
USE_LDCONFIG=	yes

PLIST_FILES=	usr/lib/libpng.so.3 \
		usr/lib/libpng.so.3.37.0 \
		usr/lib/libpng12.so.0 \
		usr/lib/libpng12.so.0.37.0 \
		usr/share/man/man5/png.5.gz
DOCSDIR=	${PREFIX}/usr/share/doc/libpng-${PORTVERSION}
PORTDOCS=	CHANGES LICENSE README TODO example.c libpng-1.2.37.txt
DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr

.include <bsd.port.mk>
