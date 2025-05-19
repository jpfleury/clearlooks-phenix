OUTDIR = ../gtk-3.0/img
SVGS = $(wildcard *.svg)
PNGS = $(SVGS:%.svg=$(OUTDIR)/%.png) $(SVGS:%.svg=$(OUTDIR)/%@2.png)

all: $(PNGS)

clean:
	-rm -f $(PNGS)

$(OUTDIR)/%.png: %.svg
	inkscape $< --export-type=png --export-filename=$@ --export-dpi=90 --export-background-opacity=0

$(OUTDIR)/%@2.png: %.svg
	inkscape $< --export-type=png --export-filename=$@ --export-dpi=180 --export-background-opacity=0
