SVGS = $(wildcard *.svg)
PNGS = $(SVGS:%.svg=../gtk-3.0/img/%.png) $(SVGS:%.svg=../gtk-3.0/img/%@2.png)

all: $(PNGS)

clean:
	-rm -f $(PNGS)

../gtk-3.0/img/%.png: %.svg
	inkscape --without-gui --export-dpi=90 --export-background-opacity=0 --export-png=$@ $<

../gtk-3.0/img/%@2.png: %.svg
	inkscape --without-gui --export-dpi=180 --export-background-opacity=0 --export-png=$@ $<
