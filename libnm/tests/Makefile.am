if ENABLE_TESTS

AM_CPPFLAGS = \
	-I$(top_srcdir)/shared \
	-I$(top_builddir)/shared \
	-I$(top_srcdir)/libnm \
	-I$(top_builddir)/libnm \
	-I$(top_srcdir)/libnm-core \
	-I$(top_builddir)/libnm-core \
	-DNETWORKMANAGER_COMPILATION=NM_NETWORKMANAGER_COMPILATION_LIB \
	-DTEST_NM_SERVICE=\"$(abs_top_srcdir)/tools/test-networkmanager-service.py\" \
	$(GLIB_CFLAGS)

LDADD = \
	$(top_builddir)/libnm/libnm.la \
	$(GLIB_LIBS)

noinst_PROGRAMS = $(TESTS)

if WITH_VALGRIND
@VALGRIND_RULES@ --launch-dbus
else
LOG_COMPILER = $(top_srcdir)/tools/run-test-dbus-session.sh
endif
TESTS = test-nm-client test-remote-settings-client test-secret-agent

test_nm_client_SOURCES = \
	$(top_builddir)/shared/nm-test-utils-impl.c \
	$(top_builddir)/shared/nm-test-libnm-utils.h \
	test-nm-client.c

test_remote_settings_client_SOURCES = \
	$(top_builddir)/shared/nm-test-utils-impl.c \
	$(top_builddir)/shared/nm-test-libnm-utils.h \
	test-remote-settings-client.c

test_secret_agent_SOURCES = \
	$(top_builddir)/shared/nm-test-utils-impl.c \
	$(top_builddir)/shared/nm-test-libnm-utils.h \
	test-secret-agent.c
endif

###############################################################################

noinst_LTLIBRARIES = \
    libnm-vpn-plugin-utils-test.la

libnm_vpn_plugin_utils_test_la_SOURCES = \
     $(top_srcdir)/shared/nm-utils/nm-vpn-plugin-utils.c \
     $(top_srcdir)/shared/nm-utils/nm-vpn-plugin-utils.h \
     $(NULL)

libnm_vpn_plugin_utils_test_la_CFLAGS = \
    $(GLIB_CFLAGS) \
    -I$(top_srcdir)/shared \
    -I$(top_srcdir)/libnm-core \
    -I$(top_srcdir)/libnm \
    $(NULL)

libnm_vpn_plugin_utils_test_la_LIBADD = \
    $(GLIB_LIBS) \
    $(NULL)

###############################################################################

