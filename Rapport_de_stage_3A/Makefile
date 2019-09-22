.DEFAULT_GOAL := main.pdf
EPS := ./figures

$(EPS):
	$(MAKE) -C $@ $(MAKECMDGOALS)

main.aux: $(EPS) main.tex
	latex main.tex

main.gls: main.bib
	makeglossaries main

main.bib: main.aux
	bibtex main.aux

main.pdf: main.gls
	pdflatex main.tex
	pdflatex main.tex

all: main.pdf

clean: $(EPS)
	rm -f *.aux
	rm -f *.dvi
	rm -f *.glo
	rm -f *.gls
	rm -f *.glsdefs
	rm -f *.glg
	rm -f *.ist
	rm -f *.lof
	rm -f *.log
	rm -f *.lol
	rm -f *.lot
	rm -f *.out
	rm -f *.bbl
	rm -f *.blg
	rm -f *.brf
	rm -f *.fig
	rm -f *.toc

distclean: clean
	rm -f *.pdf

.PHONY: all clean distclean $(EPS)
