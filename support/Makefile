#BASENAME = ED-Initiation-LaTeX
BASENAME = M2-Initiation-LaTeX

default: pdf

all: pdf bw preview

dvi:
	latex $(BASENAME)-couleur

ps: dvi
	dvips -o $(BASENAME)-couleur.ps $(BASENAME)-couleur.dvi

bib: clean
	latex $(BASENAME)-couleur
	bibtex $(BASENAME)-couleur
	latex $(BASENAME)-bw
	bibtex $(BASENAME)-bw

pdf: dvi ps
	ps2pdf -dPDFSETTINGS=/prepress $(BASENAME)-couleur.ps $(BASENAME)-couleur.pdf

bw:
	latex $(BASENAME)-bw
	dvips -o $(BASENAME)-bw.ps $(BASENAME)-bw.dvi
	ps2pdf -dPDFSETTINGS=/prepress $(BASENAME)-bw.ps $(BASENAME)-bw.pdf

html:
	hevea $(BASENAME)

web:
	cp *.pdf $(HOME)/home/www/sdl/site/teaching/master/latex/

preview: bw
# for regular paper
#	psnup -2 -m30 $(BASENAME).ps preview-$(BASENAME).ps ##	
# for multimedia slides
	psnup -2 -m80 -pa4 -W650 -H500 $(BASENAME)-bw.ps $(BASENAME)-preview.ps
	ps2pdf -dPDFSETTINGS=/prepress $(BASENAME)-preview.ps $(BASENAME)-preview.pdf

thumb: ps
	ps2pdf -dPDFSETTINGS=/prepress $(BASENAME).ps $(BASENAME).pdf
	thumbpdf --makepng --verbose --level2 --modes=ps2pdf $(BASENAME)
	latex $(BASENAME)
	dvips -o $(BASENAME).ps $(BASENAME).dvi
	ps2pdf -dPDFSETTINGS=/prepress $(BASENAME).ps $(BASENAME).pdf

clean:
	rm -f *.tpm
	rm -f *.aux
	rm -f *.out
	rm -f *.bbl
	rm -f *.tmp
	rm -f *.toc
	rm -f *.lo?
	rm -f *.tex~
	find ./ -iname '*.ps' -exec gzip -f '{}' ';'

resume:
	find ./ -iname '*.ps.gz' -exec gzip -d '{}' ';'
	find ./ -iname '*.eps.gz' -exec gzip -d '{}' ';'


decoupe:
	pdftk $(BASENAME)-couleur.pdf cat 1-9 output chapters/$(BASENAME)-couleur-00.pdf
	pdftk $(BASENAME)-couleur.pdf cat 10-29 output chapters/$(BASENAME)-couleur-01.pdf
	pdftk $(BASENAME)-couleur.pdf cat 30-36 output chapters/$(BASENAME)-couleur-02.pdf
	pdftk $(BASENAME)-couleur.pdf cat 37-54 output chapters/$(BASENAME)-couleur-03.pdf
	pdftk $(BASENAME)-couleur.pdf cat 55-62 output chapters/$(BASENAME)-couleur-04.pdf
	pdftk $(BASENAME)-couleur.pdf cat 63-66 output chapters/$(BASENAME)-couleur-05.pdf
	pdftk $(BASENAME)-couleur.pdf cat 67-81 output chapters/$(BASENAME)-couleur-06.pdf
	pdftk $(BASENAME)-couleur.pdf cat 82-93 output chapters/$(BASENAME)-couleur-07.pdf
	pdftk $(BASENAME)-couleur.pdf cat 94-124 output chapters/$(BASENAME)-couleur-08.pdf
	pdftk $(BASENAME)-couleur.pdf cat 125-147 output chapters/$(BASENAME)-couleur-09.pdf
	pdftk $(BASENAME)-couleur.pdf cat 148-151 output chapters/$(BASENAME)-couleur-10.pdf
	pdftk $(BASENAME)-couleur.pdf cat 152-155 output chapters/$(BASENAME)-couleur-11.pdf
	pdftk $(BASENAME)-couleur.pdf cat 156-168 output chapters/$(BASENAME)-couleur-12.pdf
	pdftk $(BASENAME)-bw.pdf cat 1-9 output chapters/$(BASENAME)-bw-00.pdf
	pdftk $(BASENAME)-bw.pdf cat 10-29 output chapters/$(BASENAME)-bw-01.pdf
	pdftk $(BASENAME)-bw.pdf cat 30-36 output chapters/$(BASENAME)-bw-02.pdf
	pdftk $(BASENAME)-bw.pdf cat 37-54 output chapters/$(BASENAME)-bw-03.pdf
	pdftk $(BASENAME)-bw.pdf cat 55-62 output chapters/$(BASENAME)-bw-04.pdf
	pdftk $(BASENAME)-bw.pdf cat 63-66 output chapters/$(BASENAME)-bw-05.pdf
	pdftk $(BASENAME)-bw.pdf cat 67-81 output chapters/$(BASENAME)-bw-06.pdf
	pdftk $(BASENAME)-bw.pdf cat 82-93 output chapters/$(BASENAME)-bw-07.pdf
	pdftk $(BASENAME)-bw.pdf cat 94-124 output chapters/$(BASENAME)-bw-08.pdf
	pdftk $(BASENAME)-bw.pdf cat 125-147 output chapters/$(BASENAME)-bw-09.pdf
	pdftk $(BASENAME)-bw.pdf cat 148-151 output chapters/$(BASENAME)-bw-10.pdf
	pdftk $(BASENAME)-bw.pdf cat 152-155 output chapters/$(BASENAME)-bw-11.pdf
	pdftk $(BASENAME)-bw.pdf cat 156-168 output chapters/$(BASENAME)-bw-12.pdf

