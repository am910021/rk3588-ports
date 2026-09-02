PORTNAME=	yt921x
PORTVERSION=	20260902
CATEGORIES=	net
PKGNAMEPREFIX=	motorcomm-
PKGNAMESUFFIX=	-kmod

MAINTAINER=	am910021@gmail.com
COMMENT=	Kernel module for Motorcomm YT921x Ethernet switches

LICENSE=	BSD2CLAUSE

DISTFILES=
USES=		kmod uidfix

WRKSRC=		${WRKDIR}/src

MAKE_ENV+=	MACHINE="${MACHINE}" MACHINE_ARCH="${MACHINE_ARCH}"
.if defined(TARGET)
MAKE_ENV+=	TARGET="${TARGET}"
.endif
.if defined(TARGET_ARCH)
MAKE_ENV+=	TARGET_ARCH="${TARGET_ARCH}"
.endif
.if defined(KERNBUILDDIR)
MAKE_ENV+=	KERNBUILDDIR="${KERNBUILDDIR}"
.endif

PLIST_FILES=	${KMODDIR}/yt921x.ko

# ponytail: keep the validation snapshot self-contained until the source
# repository is published; replace this with USE_GITHUB for a release.
do-extract:
	${MKDIR} ${WRKSRC}
	${CP} ${FILESDIR}/Makefile ${FILESDIR}/if_yt921x.c ${WRKSRC}

.include <bsd.port.mk>
