# Makefile
#
# transcontroller OpenSource project.
#
# Copyright (C) 2001-2012 Alexandre Cassen, <acassen@gmail.com>

TARFILES = AUTHOR bin ChangeLog configure configure.in CONTRIBUTORS COPYING \
	   doc genhash INSTALL install-sh transcontroller transcontroller.spec.in lib Makefile.in \
	   README TODO VERSION

TARBALL = transcontroller-.tar.gz

all:
	$(MAKE) -C lib || exit 1;
	$(MAKE) -C transcontroller
	@echo ""
	@echo "Make complete"

debug:
	$(MAKE) -C lib || exit 1;
	$(MAKE) -C transcontroller debug
	@echo ""
	@echo "Make complete"

profile:
	$(MAKE) -C lib || exit 1;
	$(MAKE) -C transcontroller profile
	@echo ""
	@echo "Make complete"

clean:
	$(MAKE) -C lib clean
	$(MAKE) -C transcontroller clean
	$(MAKE) -C genhash clean

distclean:
	$(MAKE) -C lib distclean
	$(MAKE) -C transcontroller distclean
	$(MAKE) -C genhash distclean
	rm -f Makefile
	rm -f transcontroller.spec

mrproper: distclean
	rm -f config.*

uninstall:
	$(MAKE) -C transcontroller uninstall
	$(MAKE) -C genhash uninstall

install:
	$(MAKE) -C transcontroller install
	$(MAKE) -C genhash install

tarball: mrproper
	mkdir transcontroller-
	cp -a $(TARFILES) transcontroller-
	tar --exclude .git -czf $(TARBALL) transcontroller-
	rm -rf transcontroller-

rpm:
	rpmbuild -ba transcontroller.spec
