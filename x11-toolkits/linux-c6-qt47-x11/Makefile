# Created by: Artyom Mirgorodskiy <artyom.mirgorodsky@gmail.com>
# $FreeBSD$

PORTNAME=	qt47-x11
PORTVERSION=	4.7.2
CATEGORIES=	x11-toolkits linux
MASTER_SITES=	http://dl.atrpms.net/el5-i386/atrpms/testing/
DIST_SUBDIR=	rpm/${LINUX_RPM_ARCH}/centos/c5
SRC_DISTFILES:=		# unretrievable.

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	RPM of QT4 (Linux CentOS 5)

ONLY_FOR_ARCHS=	i386 amd64
RPMVERSION=	1_18.el5
USE_LINUX=	c6
LINUX_RPM_ARCH=	i386
USE_LINUX_APPS=	fontconfig png  xorglibs png alsalib dri jpeg tiff qt47
USE_LINUX_RPM=	yes
LINUX_DIST_VER=	5
DESCR=	${.CURDIR}/../../devel/qt4/pkg-descr
USE_LDCONFIG=	yes

.include <bsd.port.mk>
