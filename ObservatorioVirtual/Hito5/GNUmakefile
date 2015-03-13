# LaTeX Makefile
TEXFILE = hito5.tex
BIBFILE = $(TEXFILE:.tex=)
ISTFILE = $(TEXFILE:.tex=.ist)
GLGFILE = $(TEXFILE:.tex=.glg)
GLSFILE = $(TEXFILE:.tex=.gls)
GLOFILE = $(TEXFILE:.tex=.glo)
ALGFILE = $(TEXFILE:.tex=.alg)
ACRFILE = $(TEXFILE:.tex=.acr)
ACNFILE = $(TEXFILE:.tex=.acn)
PDFFILE = $(TEXFILE:.tex=.pdf)

.PHONY: pdf all compile clean


all: compile pdf clean

compile:
	@pdflatex $(TEXFILE)
	@bibtex $(BIBFILE)
#	@makeindex -s $(ISTFILE) -t $(GLGFILE) -o $(GLSFILE) $(GLOFILE)
#	@makeindex -s $(ISTFILE) -t $(ALGFILE) -o $(ACRFILE) $(ACNFILE)
	@pdflatex $(TEXFILE)
	@pdflatex $(TEXFILE)

pdf: $(PDFFILE)
	@if [ -d publish ];then mv *.pdf publish; else mkdir publish; mv *.pdf publish/;fi

clean:
	@rm -f *.log *.aux *.out *.dvi *.lof *.lot *.toc *.acn *.acr *.alg *.glo *.gls *.glg *.idx *.ist *.bbl *.blg *.pdf
	@rm -f include/*.aux
