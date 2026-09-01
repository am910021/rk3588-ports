PORTNAME=	rk3588-uboot-flash
DISTVERSION=	0.1.0
CATEGORIES=	sysutils

MAINTAINER=	am910021@gmail.com
COMMENT=	Stage verified RK3588 U-Boot SPI updates

LICENSE=	BSD2CLAUSE

DISTFILES=
NO_ARCH=	yes
NO_BUILD=	yes

SUB_FILES=	rk3588-uboot-flash

PLIST_FILES=	sbin/rk3588-uboot-flash

do-install:
	${INSTALL_SCRIPT} ${WRKDIR}/rk3588-uboot-flash \
	    ${STAGEDIR}${PREFIX}/sbin/rk3588-uboot-flash

do-test:
	${SH} -n ${WRKDIR}/rk3588-uboot-flash
	${SH} ${WRKDIR}/rk3588-uboot-flash self-test

.include <bsd.port.mk>
