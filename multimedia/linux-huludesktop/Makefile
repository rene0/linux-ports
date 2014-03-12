# Created by: Joseph S. Atkinson <jsa@wickedmachine.net>
# $FreeBSD$

PORTNAME=	huludesktop
PORTVERSION=	0.9.8
PORTREVISION?=	4
CATEGORIES=	multimedia linux
MASTER_SITES=	http://download.hulu.com/
PKGNAMEPREFIX=	linux-
DISTNAME=	${PORTNAME}-${LINUX_RPM_ARCH}
EXTRACT_SUFX=	.rpm

MAINTAINER=	jsa@FreeBSD.org
COMMENT=	Streaming video client for TV and movies on Hulu.com

ONLY_FOR_ARCHS=	i386 amd64
LINUX_RPM_ARCH=	i386

USE_LINUX=	yes
USE_LINUX_APPS=	gtk2
NO_BUILD=	yes

RPM2CPIO?=	${LOCALBASE}/bin/rpm2cpio.pl
FLASHPLUGIN=	linux-${USE_LINUX}-flashplugin
FLASHPATH=	${LOCALBASE}/lib/browser_plugins/${FLASHPLUGIN}/libflashplayer.so
EXTRACT_DEPENDS+=	${RPM2CPIO}:${PORTSDIR}/archivers/rpm2cpio
RUN_DEPENDS+=	${FLASHPATH}:${PORTSDIR}/www/${FLASHPLUGIN}11

RESTRICTED=	Non-redistributable, non-commercial, export controlled

SUB_FILES=	${PORTNAME}

.include <bsd.port.pre.mk>
.include <bsd.port.options.mk>

.if ${OSVERSION} >= 90000
IGNORE= has known issues under 9.x. Define NO_IGNORE to install without support
.endif

do-extract:
	${MKDIR} ${WRKSRC}
	${RPM2CPIO} ${DISTDIR}/${DISTNAME}${EXTRACT_SUFX} | \
		${TAR} xf - -C ${WRKSRC}

do-install:
	${MKDIR} ${STAGEDIR}${PREFIX}/etc/${PORTNAME} \
		${STAGEDIR}${PREFIX}/share/applications
	${INSTALL_SCRIPT} ${WRKDIR}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin/${PORTNAME}
	${INSTALL_PROGRAM} ${WRKSRC}/usr/bin/${PORTNAME} \
		${STAGEDIR}${PREFIX}/libexec/${PORTNAME}.bin
	${INSTALL_DATA} ${WRKSRC}/etc/${PORTNAME}/hd_keymap.ini \
		${STAGEDIR}${PREFIX}/etc/${PORTNAME}
.	for FILE in applications/${PORTNAME}.desktop pixmaps/${PORTNAME}.png
		${INSTALL_DATA} ${WRKSRC}/usr/share/${FILE} \
			${STAGEDIR}${PREFIX}/share/${FILE}
.	endfor
.if ${PORT_OPTIONS:MDOCS}
	${MKDIR} ${STAGEDIR}${DOCSDIR}
.	for FILE in EULA LICENSE README
		${INSTALL_DATA} ${WRKSRC}/usr/share/doc/${PORTNAME}/${FILE} \
			${STAGEDIR}${DOCSDIR}
.	endfor
.endif

.include <bsd.port.post.mk>
