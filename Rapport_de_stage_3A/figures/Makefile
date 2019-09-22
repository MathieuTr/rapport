PNG := $(wildcard *.png)
JPG := $(wildcard *.jpg)
PDF := $(wildcard *.pdf)
EPS := $(PNG:.png=.eps) $(JPG:.jpg=.eps) $(PDF:.pdf=.eps)
DEL := $(wildcard *.eps)

%.eps  : %.png
	/usr/bin/convert $< $@

%.eps  : %.jpg
	/usr/bin/convert $< $@

%.eps  : %.pdf
	/usr/bin/convert $< $@

all: $(EPS)

clean: $(DEL)
	@for file in $^; do \
		rm -f $${file} ; \
	done

distclean: clean

.PHONY: clean all distclean
