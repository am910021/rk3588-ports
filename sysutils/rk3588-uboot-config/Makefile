PORTNAME=	rk3588-uboot-config
DISTVERSION=	0.3.0
CATEGORIES=	sysutils

MAINTAINER=	am910021@gmail.com
COMMENT=	Configure the RK3588 FreeBSD U-Boot menu

LICENSE=	BSD2CLAUSE

DISTFILES=
NO_ARCH=	yes
NO_BUILD=	yes

SUB_FILES=	rk3588-uboot-config

PLIST_FILES=	sbin/rk3588-uboot-config

do-install:
	${INSTALL_SCRIPT} ${WRKDIR}/rk3588-uboot-config \
	    ${STAGEDIR}${PREFIX}/sbin/rk3588-uboot-config

do-test:
	${SH} ${WRKDIR}/rk3588-uboot-config self-test

.include <bsd.port.mk>
