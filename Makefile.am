#

ACLOCAL_AMFLAGS = -I m4

SUBDIRS = include lib bin man etc doc

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = varnishapi.pc

EXTRA_DIST = LICENSE autogen.sh varnishapi.pc.in

DISTCHECK_CONFIGURE_FLAGS = \
    --enable-developer-warnings \
    --enable-debugging-symbols \
    --enable-dependency-tracking \
    --enable-diagnostics \
    --enable-extra-developer-warnings \
    --enable-tests \
    --enable-werror

install-data-local:
	$(install_sh) -d -m 0755 $(DESTDIR)$(localstatedir)/varnish

distcleancheck_listfiles = \
	find . -type f -exec sh -c 'test -f $(srcdir)/$$1 || echo $$1' \
		sh '{}' ';'
