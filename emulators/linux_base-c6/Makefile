# Created by: Svyatoslav Lempert <svyatoslav.lempert@gmail dot com>
# $FreeBSD$

PORTNAME=		c6
PORTVERSION=		6.5
CATEGORIES=		emulators linux
MASTER_SITES=	http://mirror.centos.org/centos/6/os/i386/Packages/:bin
PKGNAMEPREFIX=		linux_base-
DISTFILES=		${BIN_DISTFILES} ${SRC_DISTFILES}
EXTRACT_ONLY=		${BIN_DISTFILES}

MAINTAINER=	emulation@FreeBSD.org
COMMENT=	Base set of packages needed in Linux mode for i386/amd64 (Linux CentOS 6)

LINUX_DIST=	centos
LINUX_DIST_VER=6.5
DIST_SUBDIR=   rpm/${LINUX_RPM_ARCH}/${LINUX_DIST}/${LINUX_DIST_VER}

BIN_DISTFILES=	basesystem-10.0-4.el6.noarch.rpm:bin \
		bash-4.1.2-15.el6_4.${LINUX_RPM_ARCH}.rpm:bin \
		bzip2-1.0.5-7.el6_0.${LINUX_RPM_ARCH}.rpm:bin \
		bzip2-libs-1.0.5-7.el6_0.${LINUX_RPM_ARCH}.rpm:bin \
		compat-db43-4.3.29-15.el6.${LINUX_RPM_ARCH}.rpm:bin \
		compat-libstdc++-33-3.2.3-69.el6.${LINUX_RPM_ARCH}.rpm:bin \
		compat-libstdc++-296-2.96-144.el6.${LINUX_RPM_ARCH}.rpm:bin \
		coreutils-8.4-31.el6.${LINUX_RPM_ARCH}.rpm:bin \
		db4-4.7.25-18.el6_4.${LINUX_RPM_ARCH}.rpm:bin \
		e2fsprogs-1.41.12-18.el6.${LINUX_RPM_ARCH}.rpm:bin \
		e2fsprogs-libs-1.41.12-18.el6.${LINUX_RPM_ARCH}.rpm:bin \
		elfutils-0.152-1.el6.${LINUX_RPM_ARCH}.rpm:bin \
		centos-release-6-5.el6.centos.11.1.${LINUX_RPM_ARCH}.rpm:bin \
		filesystem-2.4.30-3.el6.${LINUX_RPM_ARCH}.rpm:bin \
		findutils-4.4.2-6.el6.${LINUX_RPM_ARCH}.rpm:bin \
		freetype-2.3.11-14.el6_3.1.${LINUX_RPM_ARCH}.rpm:bin \
		gdbm-1.8.0-36.el6.${LINUX_RPM_ARCH}.rpm:bin \
		glib2-2.26.1-3.el6.${LINUX_RPM_ARCH}.rpm:bin \
		glibc-2.12-1.132.el6.${LINUX_RPM_ARCH}.rpm:bin \
		glibc-common-2.12-1.132.el6.${LINUX_RPM_ARCH}.rpm:bin \
		grep-2.6.3-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		info-4.13a-8.el6.${LINUX_RPM_ARCH}.rpm:bin \
		keyutils-1.4-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		keyutils-libs-1.4-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		krb5-libs-1.10.3-10.el6_4.6.${LINUX_RPM_ARCH}.rpm:bin \
		less-436-10.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libacl-2.2.49-6.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libattr-2.4.44-7.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libcom_err-1.41.12-18.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libcap-2.16-5.5.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libgcc-4.4.7-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libidn-1.18-2.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libselinux-2.0.94-5.3.el6_4.1.${LINUX_RPM_ARCH}.rpm:bin \
		libsepol-2.0.41-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libstdc++-4.4.7-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		libuuid-2.17.2-12.14.el6.${LINUX_RPM_ARCH}.rpm:bin \
		ncurses-5.7-3.20090208.el6.${LINUX_RPM_ARCH}.rpm:bin \
		ncurses-libs-5.7-3.20090208.el6.${LINUX_RPM_ARCH}.rpm:bin \
		pcre-7.8-6.el6.${LINUX_RPM_ARCH}.rpm:bin \
		popt-1.13-7.el6.${LINUX_RPM_ARCH}.rpm:bin \
		readline-6.0-4.el6.${LINUX_RPM_ARCH}.rpm:bin \
		setserial-2.17-25.el6.${LINUX_RPM_ARCH}.rpm:bin \
		setup-2.8.14-20.el6_4.1.noarch.rpm:bin \
		slang-2.2.1-1.el6.${LINUX_RPM_ARCH}.rpm:bin \
		which-2.19-6.el6.${LINUX_RPM_ARCH}.rpm:bin \
		zlib-1.2.3-29.el6.${LINUX_RPM_ARCH}.rpm:bin

.if defined(PACKAGE_BUILDING)
MASTER_SITES+=  http://vault.centos.org/${PORTVERSION}/os/Source/SPackages/:src

SRC_DISTFILES=	basesystem-10.0-4.el6.src.rpm:src \
		bash-4.1.2-15.el6_4.src.rpm:src \
		bzip2-1.0.5-7.el6_0.src.rpm:src \
		coreutils-8.4-31.el6.src.rpm:src \
		compat-db-4.6.21-15.el6.src.rpm:src \
		compat-gcc-296-2.96-144.el6.src.rpm:src \
		compat-gcc-32-3.2.3-69.el6.src.rpm:src \
		db4-4.7.25-18.el6_4.src.rpm:src \
		e2fsprogs-1.41.12-18.el6.src.rpm:src \
		elfutils-0.152-1.el6.src.rpm:src \
		centos-release-6-5.el6.centos.11.1.src.rpm:src \
		filesystem-2.4.30-3.el6.src.rpm:src \
		findutils-4.4.2-6.el6.src.rpm:src \
		freetype-2.3.11-14.el6_3.1.src.rpm:src \
		gdbm-1.8.0-36.el6.src.rpm:src \
		glib2-2.26.1-3.el6.src.rpm:src \
		glibc-2.12-1.132.el6.src.rpm:src \
		grep-2.6.3-4.el6.src.rpm:src \
		texinfo-4.13a-8.el6.src.rpm:src \
		keyutils-1.4-4.el6.src.rpm:src \
		krb5-1.10.3-10.el6_4.6.src.rpm:src \
		less-436-10.el6.src.rpm:src \
		acl-2.2.49-6.el6.src.rpm:src \
		attr-2.4.44-7.el6.src.rpm:src \
		libcap-2.16-5.5.el6.src.rpm:src \
		gcc-4.4.7-4.el6.src.rpm:src \
		libidn-1.18-2.el6.src.rpm:src \
		libselinux-2.0.94-5.3.el6_4.1.src.rpm:src \
		libsepol-2.0.41-4.el6.src.rpm:src \
		ncurses-5.7-3.20090208.el6.src.rpm:src \
		pcre-7.8-6.el6.src.rpm:src \
		popt-1.13-7.el6.src.rpm:src \
		readline-6.0-4.el6.src.rpm:src \
		setserial-2.17-25.el6.src.rpm:src \
		setup-2.8.14-20.el6_4.1.src.rpm:src \
		slang-2.2.1-1.el6.src.rpm:src \
		util-linux-ng-2.17.2-12.14.el6.src.rpm:src \
		which-2.19-6.el6.src.rpm:src \
		zlib-1.2.3-29.el6.src.rpm:src

ALWAYS_KEEP_DISTFILES=	yes
.endif

CONFLICTS=              linux_base-gentoo* linux_base-f* linux-glib2-*

ONLY_FOR_ARCHS=		i386 amd64
LINUX_RPM_ARCH=		i686
USE_LINUX_PREFIX=	yes
NO_WRKSUBDIR=		yes
DISTINFO_FILE?=		${MASTERDIR}/distinfo.${LINUX_RPM_ARCH}
PLIST_SUB=		GLIBCVER="2.12"

# TODO:
# - move master sites to bsd.sites.mk
# - add 2-3 mirrors from each country (http://www.centos.org/modules/tinycontent/index.php?id=31)
# - create centos infrastructure in bsd.linux*.mk
# - look for updates in the updates folder of the CentOS mirrors
# - research what are the important differences between 2.6.16 and 2.6.18, and
#   if we need to add something to the linuxulator

EXTRACT_ONLY=		${BIN_DISTFILES}

.include <bsd.port.pre.mk>

.if !defined(PACKAGE_BUILDING) || (defined(PACKAGE_BUILDING) && !defined(LINUX_OSRELEASE) )
LINUX_OSRELEASE!=	${ECHO_CMD} `${SYSCTL} -n compat.linux.osrelease 2>/dev/null`
.endif

.if ${LINUX_OSRELEASE}x == "x"
IGNORE=			linuxulator is not (kld)loaded
.elif ${LINUX_OSRELEASE} == "2.6.16"
IGNORE=			compat.linux.osrelease: ${LINUX_OSRELEASE} is not supported, please use 2.6.18, BEWARE this is highly experimental
.endif

REMOVE_DIRS=		boot dev etc/fonts home initrd media root tmp var/log var/run var/tmp \
			usr/local usr/tmp
REMOVE_FILES=		bin/df bin/su etc/exports etc/group etc/localtime \
			etc/motd etc/passwd etc/printcap etc/services \
			etc/protocols
ADD_DIRS=		usr/X11R6/share usr/X11R6/man usr/X11R6/lib/tls \
			usr/X11R6/include usr/X11R6/bin
ADD_FILES=		#empty

.if (${MACHINE_ARCH} == "amd64")
FALLBACK_ELF_MIB=	kern.elf32.fallback_brand
.else
FALLBACK_ELF_MIB=	kern.fallback_elf_brand
.endif

.if (${ARCH} == "amd64")
LATEST_LINK:=		${PKGBASE:C/linux/linux32/}
ARCH=			i386
.endif

do-build:
	@for D in ${REMOVE_DIRS}; do \
		${RM} -rf ${WRKSRC}/$$D; \
	done
	@for F in ${REMOVE_FILES}; do \
		${RM} -f ${WRKSRC}/$$F; \
	done
	@for F in ${ADD_DIRS}; do \
		${MKDIR} ${WRKSRC}/$$F; \
	done
	@for F in ${ADD_FILES}; do \
		${TOUCH} ${WRKSRC}/$$F; \
	done
#
# Create a good ld.so.conf and touch ld.so.cache
#
	@${ECHO_CMD} -e '/lib\n/usr/lib\n${X11BASE}/lib' >> \
		${WRKSRC}/etc/ld.so.conf
	@${TOUCH} ${WRKSRC}/etc/ld.so.cache
#
# Create yp.conf as a hint to NIS users and make sure there's a
# mtab in etc, albeit an empty one. This is needed in a couple of
# cases. Most notably staroffice6. If yp.conf exists install only
# yp.conf.sample
#
	@${INSTALL} ${COPY} -m 644 ${FILESDIR}/yp.conf.sample ${WRKSRC}/etc
	@${TOUCH} ${WRKSRC}/etc/mtab
#
# If ${PREFIX}/etc/krb5.conf exists, don't touch it
#
	@${MV} ${WRKSRC}/etc/krb5.conf ${WRKSRC}/etc/krb5.conf.dist

# Fix usr/bin/*db4* permissions to allow "portupgrade -s"
#	@${CHMOD} u+w ${WRKSRC}/usr/bin/*db4*

	@${FIND} ${WRKSRC}/bin ${WRKSRC}/sbin/ ${WRKSRC}/usr/bin \
		${WRKSRC}/usr/sbin -type f -print0 | ${XARGS} -0 ${FILE} \
		| ${GREP} ELF | ${CUT} -d : -f 1 \
		| ${XARGS} ${BRANDELF} -t Linux
	@${BRANDELF} -t Linux ${WRKSRC}/lib/ld-2.12.so

# Restore the status quo for usr/bin/*db4* files
#	@${CHMOD} u-w ${WRKSRC}/usr/bin/*db4*

do-install:
#
# Do install without using linux rpm system
#
	@cd ${WRKSRC} && ${FIND} * ! -path "stage*" -type d -exec ${MKDIR} "${STAGEDIR}${PREFIX}/{}" \;
	@cd ${WRKSRC} && ${FIND} * ! -path "stage/*" ! -type d \
		| ${CPIO} -pm -R root:wheel ${STAGEDIR}${PREFIX}

	@${LN} -sf /var/tmp ${STAGEDIR}${PREFIX}/usr/tmp
	@${CHMOD} 755 ${STAGEDIR}${PREFIX}/var/lock ${STAGEDIR}${PREFIX}/var/spool/mail
#
# Let some linux applications (e.g. print/acroread8) print with default settings
#
	@${INSTALL_SCRIPT} ${FILESDIR}/lp ${STAGEDIR}${PREFIX}/usr/bin

post-install:
	if [ ! -f ${PREFIX}/etc/krb5.conf ] ; then \
		${CP} -p ${STAGEDIR}${PREFIX}/etc/krb5.conf.dist ${STAGEDIR}${PREFIX}/etc/krb5.conf ; \
	fi
	if [ ! -f ${PREFIX}/etc/yp.conf ] ; then \
		${CP} -p ${STAGEDIR}${PREFIX}/etc/yp.conf.sample ${STAGEDIR}${PREFIX}/etc/yp.conf ; \
	fi

.include <bsd.port.post.mk>
