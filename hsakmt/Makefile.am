include $(top_srcdir)/hsakmt/Makefile.sources

lib_LTLIBRARIES = libhsakmt-1.la

libhsakmt_1_la_LDFLAGS = -version-info $(LT_VERSION_INFO) -no-undefined @PTHREAD_LDFLAGS@ 
libhsakmt_1_la_LIBADD = @PTHREAD_LIBS@ -lm
libhsakmt_1_la_SOURCES = $(libhsakmt_sources) $(libhsakmt_headers)

libhsakmtincludedir = $(includedir)/hsakmt-1
libhsakmtinclude_HEADERS = hsakmt.h hsakmttypes.h kfd_ioctl.h hsakmt-version.h
noinst_LTLIBRARIES = 

.c.s : $(libhsakmtinclude_HEADERS)
	$(CC) $(CFLAGS) $(ASM_CFLAGS_$(@:hsakmt-%.s=%)) -DHAVE_CONFIG_H -I$(srcdir) -I$(builddir) -I$(top_builddir) -S -o $@ $<
