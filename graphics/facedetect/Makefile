# Created by: Emanuel Haupt <ehaupt@FreeBSD.org>
# $FreeBSD$

PORTNAME=	facedetect
PORTVERSION=	0.1
DISTVERSIONPREFIX=	v
PORTREVISION=	5
CATEGORIES=	graphics

MAINTAINER=	ehaupt@FreeBSD.org
COMMENT=	Simple face detector for batch processing

LICENSE=	GPLv2+
LICENSE_FILE=	${WRKSRC}/COPYING.txt

RUN_DEPENDS=	${PYTHON_SITELIBDIR}/cv2.so:graphics/py-opencv@${PY_FLAVOR}

USES=		python:3.6+,run shebangfix
USE_GITHUB=	yes
GH_ACCOUNT=	wavexx

SHEBANG_FILES=	facedetect

NO_ARCH=	yes
NO_BUILD=	yes

PLIST_FILES=	bin/facedetect

post-patch:
	@${REINPLACE_CMD} -e 's|%%LOCALBASE%%|${LOCALBASE}|g' \
		${WRKSRC}/${PORTNAME}

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/bin

.include <bsd.port.mk>
