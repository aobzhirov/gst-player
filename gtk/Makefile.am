bin_PROGRAMS = gtk-play

gtk-play-resources.c: resources/gresources.xml \
	resources/media_info_dialog.ui	\
	resources/toolbar.css						\
	resources/toolbar.ui
	$(AM_V_GEN)												\
	glib-compile-resources						\
	--sourcedir=$(srcdir)/resources		\
	--target=$@												\
	--generate-source									\
	--c-name as												\
	$(srcdir)/resources/gresources.xml

gtk-play-resources.h: resources/gresources.xml \
	resources/media_info_dialog.ui	\
	resources/toolbar.css						\
	resources/toolbar.ui
	$(AM_V_GEN)												\
	glib-compile-resources  					\
	--sourcedir=$(srcdir)/resources   \
	--target=$@												\
	--generate-header									\
	--c-name as												\
	$(srcdir)/resources/gresources.xml

BUILT_SOURCES: gtk-play-resources.c gtk-play-resources.h

gtk_play_SOURCES = gtk-play.c gtk-play-resources.c

LDADD = $(top_builddir)/lib/gst/player/.libs/libgstplayer-@GST_PLAYER_API_VERSION@.la \
	$(GSTREAMER_LIBS) $(GTK_LIBS) $(GTK_X11_LIBS) $(GLIB_LIBS) $(LIBM) $(GMODULE_LIBS)

AM_CFLAGS = -I$(top_srcdir)/lib -I$(top_builddir)/lib $(GSTREAMER_CFLAGS) $(GTK_CFLAGS) $(GTK_X11_CFLAGS) $(GLIB_CFLAGS) $(GMODULE_CFLAGS)

noinst_HEADERS = gtk-play-resources.h
