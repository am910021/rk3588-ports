PORTNAME=	rk3588-uboot-tools
DISTVERSION=	0.4.1
CATEGORIES=	sysutils

MAINTAINER=	am910021@gmail.com
COMMENT=	Configure RK3588 U-Boot and stage verified firmware updates

LICENSE=	BSD2CLAUSE

DISTFILES=
NO_ARCH=	yes
NO_BUILD=	yes

CONFLICTS_INSTALL=	rk3588-uboot-config-* rk3588-uboot-flash-*

SUB_FILES=	rk3588-uboot-tools

PLIST_FILES=	sbin/rk3588-uboot-tools

do-install:
	${INSTALL_SCRIPT} ${WRKDIR}/rk3588-uboot-tools \
	    ${STAGEDIR}${PREFIX}/sbin/rk3588-uboot-tools

do-test:
	${SH} -n ${WRKDIR}/rk3588-uboot-tools
	${SH} ${WRKDIR}/rk3588-uboot-tools self-test

.include <bsd.port.mk>
