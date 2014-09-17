# Created by: bsam
# $FreeBSD: head/audio/linux-f10-libaudiofile/Makefile 329390 2013-10-04 21:35:35Z rene $

PORTNAME=	lib${LINUX_NAME}
PORTVERSION=	0.2.6
CATEGORIES=	audio linux
MASTER_SITES=	CRITICAL/rpm/${LINUX_RPM_ARCH}/fedora/${LINUX_DIST_VER}
DISTNAME=	${LINUX_NAME}-${PORTVERSION}-${RPMVERSION}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Implementation of the Audio File Library from SGI (Linux Fedora 10)

FORBIDDEN=	http://www.freshports.org/vuxml.php?vid=09f47c51-c1a6-11e3-a5ac-001b21614864

CONTFLICTS=	linux-libaudiofile-[0-9]* linux-f8-libaudiofile-[0-9]*

USE_LINUX=	f10
USE_LINUX_RPM=	yes
LINUX_NAME=	audiofile

RPMVERSION=	9.fc10
BRANDELF_DIRS=	usr/bin
USE_LDCONFIG=	yes
PLIST=		${PKGDIR}/pkg-plist.${LINUX_RPM_ARCH}

DESCR=		${.CURDIR}/../${PORTNAME}/pkg-descr

.include <bsd.port.mk>
