
plugin_LTLIBRARIES = libgstosxvideosink.la

libgstosxvideosink_la_SOURCES = osxvideosink.m cocoawindow.m 
libgstosxvideosink_la_CFLAGS = $(GST_CFLAGS) $(GST_BASE_CFLAGS) \
	$(GST_PLUGINS_BASE_CFLAGS) -DRUN_NS_APP_THREAD
libgstosxvideosink_la_OBJCFLAGS = $(GST_OBJCFLAGS) $(GST_BASE_CFLAGS) \
	$(GST_PLUGINS_BASE_CFLAGS) -DRUN_NS_APP_THREAD
libgstosxvideosink_la_LIBADD =  \
	$(GST_LIBS) \
	$(GST_BASE_LIBS) \
	$(GST_PLUGINS_BASE_LIBS) \
	-lgstvideo-$(GST_MAJORMINOR) \
	-lgstinterfaces-$(GST_MAJORMINOR)

libgstosxvideosink_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS) -Wl,-framework -Wl,Cocoa -Wl,-framework -Wl,QuickTime -Wl,-framework -Wl,OpenGL
if !GST_PLUGIN_BUILD_STATIC
libgstosxvideosink_la_LIBTOOLFLAGS = --tag=disable-static
endif

noinst_HEADERS = osxvideosink.h cocoawindow.h
