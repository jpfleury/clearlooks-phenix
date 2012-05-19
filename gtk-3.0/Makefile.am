SUBDIRS = assets borders

themedir = $(datadir)/themes/Adwaita/gtk-3.0
theme_DATA = 		\
	gtk.gresource	\
	gtk.css 	\
	gtk-dark.css	\
	settings.ini

gtk.gresource: gtk.gresource.xml  $(shell $(GLIB_COMPILE_RESOURCES) --generate-dependencies $(srcdir)/gtk.gresource.xml)
	$(AM_V_GEN) $(GLIB_COMPILE_RESOURCES) --target=$@ --sourcedir=$(srcdir)  $<

EXTRA_DIST = \
	gnome-applications.css \
	gtk.gresource.xml \
	gtk.css \
	gtk-dark.css \
	gtk-main.css \
	gtk-main-common.css \
	gtk-main-dark.css \
	gtk-widgets.css \
	gtk-widgets-backgrounds.css \
	gtk-widgets-borders.css \
	gtk-widgets-borders-dark.css \
	gtk-widgets-dark-overrides.css \
	gtk-widgets-assets.css \
	gtk-widgets-assets-dark.css \
	settings.ini

CLEANFILES = \
	gtk.gresource

-include $(top_srcdir)/git.mk
