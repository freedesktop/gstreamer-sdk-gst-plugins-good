plugin_LTLIBRARIES = libgstflac.la

libgstflac_la_SOURCES = gstflac.c gstflacdec.c gstflacenc.c gstflactag.c
libgstflac_la_CFLAGS = -DGST_USE_UNSTABLE_API \
	$(GST_PLUGINS_BASE_CFLAGS) $(GST_BASE_CFLAGS) $(GST_CFLAGS) $(FLAC_CFLAGS)
libgstflac_la_LIBADD = \
	$(GST_PLUGINS_BASE_LIBS) -lgsttag-$(GST_MAJORMINOR) \
	-lgstaudio-$(GST_MAJORMINOR) \
	$(GST_BASE_LIBS) $(GST_LIBS) $(FLAC_LIBS)
libgstflac_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)
if !GST_PLUGIN_BUILD_STATIC
libgstflac_la_LIBTOOLFLAGS = --tag=disable-static
endif

noinst_HEADERS = gstflacenc.h gstflacdec.h gstflactag.h
