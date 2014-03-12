# Created by: Michael Durian <durian@shadetreesoftware.com>
# $FreeBSD$

PORTNAME=	linux-eagle5
EAGLEBASEVERSION?=	5.12
EAGLEBUGFIX?=	0
EAGLEVERSION=	${EAGLEBASEVERSION}.${EAGLEBUGFIX}
PORTVERSION=	${EAGLEVERSION:S/r/./}
PORTREVISION?=	3
CATEGORIES?=	cad linux
MASTER_SITES=	ftp://ftp.cadsoft.de/eagle/program/${EAGLEBASEVERSION}/
DISTNAME=	eagle-${EAGLEVERSION}
DISTFILES=	eagle-lin-${EAGLEVERSION}.run

MAINTAINER?=	thomas.e.zander@googlemail.com
COMMENT?=	An easy to use, yet powerful tool for designing printed circuit boards

ONLY_FOR_ARCHS=	i386 amd64

DATADIR=	${PREFIX}/share/${PORTNAME:S/linux-//}
EXTRACT_CMD=	${SED}
EXTRACT_BEFORE_ARGS=	-e '1,/^__DATA__$$/d'
EXTRACT_AFTER_ARGS=	| ${BZCAT} -c 2>/dev/null | ${TAR} -xf -

RESTRICTED=	Usage permitted for non-commercial purposes only
NO_CDROM=	Sale for profit is not permitted

CONFLICTS=	linux-eagle-* de-linux-eagle-*

USE_LINUX=	yes
USE_LINUX_APPS=	xorglibs jpeg png
NO_BUILD=	yes
PKGMESSAGE=	${WRKDIR}/pkg-message
SUB_FILES=	pkg-deinstall

CPIO?=		/usr/bin/cpio --quiet -pdum -R

DESKTOP_ENTRIES=	"Eagle5" "Tool for designing printed circuit boards" \
			${DATADIR}/ulp/eagle.bmp \
			"eagle" "Development;Electronics;Engineering;" "false"

.include <bsd.port.pre.mk>

PLIST_SUB+=	LINUXBASE=${LINUXBASE}

do-install:
	@${MKDIR} ${STAGEDIR}${DATADIR}
	@ cd ${WRKSRC} && ${FIND} * -type f -print | ${CPIO} ${BINOWN}:${BINGRP} ${STAGEDIR}${DATADIR}
	@ cd ${STAGEDIR}${DATADIR} && ${FIND} * -type d -print | ${XARGS} ${CHMOD} 0755
	@${INSTALL_MAN} ${STAGEDIR}${DATADIR}/doc/eagle.1 ${STAGEDIR}${PREFIX}/man/man1/eagle.1
	@${SED} -e "s:%%DATADIR%%:${DATADIR}:g" ${FILESDIR}/eagle.sh > ${STAGEDIR}${PREFIX}/bin/eagle
	@${CHMOD} 0555 ${STAGEDIR}${PREFIX}/bin/eagle

post-install:
	@${SED} -e "s:%%PREFIX%%:${PREFIX}:g" ${PKGDIR}/pkg-message > \
		${PKGMESSAGE}
.if !defined(BATCH)
	@${ECHO_MSG}
	@${CAT} ${PKGMESSAGE}
	@${ECHO_MSG}
.endif

.include <bsd.port.post.mk>
