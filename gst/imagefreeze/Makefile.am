plugin_LTLIBRARIES = libgstimagefreeze.la

libgstimagefreeze_la_SOURCES = gstimagefreeze.c

libgstimagefreeze_la_CFLAGS = $(GST_CFLAGS)
libgstimagefreeze_la_LIBADD = $(GST_LIBS)
libgstimagefreeze_la_LDFLAGS = $(GST_PLUGIN_LDFLAGS)
if !GST_PLUGIN_BUILD_STATIC
libgstimagefreeze_la_LIBTOOLFLAGS = --tag=disable-static
endif

noinst_HEADERS = gstimagefreeze.h

Android.mk: Makefile.am $(BUILT_SOURCES)
	androgenizer \
	-:PROJECT libgstimagefreeze -:SHARED libgstimagefreeze \
	 -:TAGS eng debug \
         -:REL_TOP $(top_srcdir) -:ABS_TOP $(abs_top_srcdir) \
	 -:SOURCES $(libgstimagefreeze_la_SOURCES) \
	 -:CFLAGS $(DEFS) $(DEFAULT_INCLUDES) $(libgstimagefreeze_la_CFLAGS) \
	 -:LDFLAGS $(libgstimagefreeze_la_LDFLAGS) \
	           $(libgstimagefreeze_la_LIBADD) \
	           -ldl \
	 -:PASSTHROUGH LOCAL_ARM_MODE:=arm \
		       LOCAL_MODULE_PATH:='$$(TARGET_OUT)/lib/gstreamer-0.10' \
	> $@
