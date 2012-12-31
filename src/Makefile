TARGETS=all check clean clobber distclean install uninstall
TARGET=all

PREFIX=${DESTDIR}/opt
SBINDIR=${PREFIX}/sbin
SUBDIRS=

INSTALL=install

.PHONY: ${TARGETS} ${SUBDIRS}

all::	sfdisk-cp

${TARGETS}::

clobber distclean:: clean

check::	sfdisk-cp
	./sfdisk-cp ${ARGS}

install:: sfdisk-cp
	${INSTALL} -D sfdisk-cp ${SBINDIR}/sfdisk-cp

uninstall::
	${RM} ${SBINDIR}/sfdisk-cp

ifneq	(,${SUBDIRS})
${TARGETS}::
	${MAKE} TARGET=$@ ${SUBDIRS}
${SUBDIRS}::
	${MAKE} -C $@ ${TARGET}
endif
