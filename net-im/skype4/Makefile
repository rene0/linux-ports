# Created by: netchild@FreeBSD.org
# $FreeBSD: head/net-im/skype/Makefile 327756 2013-09-20 22:13:34Z bapt $

PORTNAME=	skype
PORTVERSION=	4.2.0.13
PORTEPOCH=	1
CATEGORIES=	net-im
MASTER_SITES=	http://download.skype.com/linux/
DISTNAME=	skype-${DISTVERSION}

MAINTAINER=	xmj@chaot.net
COMMENT=	P2P VoIP software

CONFLICTS=	skype-devel-[0-9]*

OPTIONS_DEFINE=	VIDEO #NVIDIA_GL
#NVIDIA_GL_DESC=	libGL provided by NVidia binary drivers

OPTIONS_DEFAULT=	VIDEO

NO_BUILD=	yes

USE_BZIP2=	yes
USE_LINUX=	c6
USE_LINUX_APPS+=alsalib alsa-plugins-oss fontconfig xorglibs qt47 qt47-x11 qt47-webkit openssl-compat
RESTRICTED=	Redistribution prohibited.

SKYPEDIR=	share/skype
PORTDOCS=	LICENSE README
PLIST_SUB+=	SKYPEDIR=${SKYPEDIR}
SUB_FILES=	skype.sh
SUB_LIST+=	SKYPEDIR=${SKYPEDIR}

NO_STAGE=	yes
.include <bsd.port.options.mk>
.include <bsd.port.pre.mk>

#.if ${PORT_OPTIONS:MNVIDIA_GL}
#RUN_DEPENDS+=	${LINUXBASE}/usr/lib/libGL.so.1:${PORTSDIR}/x11/nvidia-driver
#USE_LINUX_APPS+=xorglibs
#.else
#USE_LINUX_APPS+=dri
#.endif

.if ${PORT_OPTIONS:MVIDEO}
RUN_DEPENDS+=	webcamd>0:${PORTSDIR}/multimedia/webcamd
USE_LINUX_APPS+=	libv4l
SUB_LIST+=	VIDEO="LD_PRELOAD=/usr/lib/libv4l/v4l2convert.so "
.else
SUB_LIST+=	VIDEO=""
.endif

do-install:
	@${INSTALL} -d ${PREFIX}/share/applications
	@${INSTALL_DATA} ${WRKSRC}/skype.desktop ${PREFIX}/share/applications/
	@${INSTALL_DATA} ${WRKSRC}/icons/SkypeBlue_48x48.png ${PREFIX}/share/pixmaps/skype.png
	@cd ${WRKSRC}/ && ${MKDIR} ${PREFIX}/${SKYPEDIR} && ${COPYTREE_SHARE} "avatars icons sounds lang" ${PREFIX}/${SKYPEDIR}/

# The binary main program
	@${INSTALL_PROGRAM} ${WRKSRC}/skype ${PREFIX}/${SKYPEDIR}/

# The wrapper for main program
	@${INSTALL_SCRIPT} ${WRKDIR}/skype.sh ${PREFIX}/bin/skype

.if ${PORT_OPTIONS:MDOCS}
	@${INSTALL} -d ${DOCSDIR}
	@cd ${WRKSRC} && ${INSTALL_DATA} ${PORTDOCS} ${DOCSDIR}
.endif
	@${CAT} ${PKGMESSAGE}

.include <bsd.port.post.mk>
