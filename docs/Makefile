LATEX = latex -shell-escape
DVI2PDF = dvipdf
OPEN = evince
FILENAME = added_mass_transformations

define cleanup =
rm $(FILENAME).aux -f
rm $(FILENAME).dvi -f
rm $(FILENAME).log -f
rm $(FILENAME).out -f
rm _minted-$(FILENAME) -rf
endef

.PHONY: all view cleanup clean update

all : $(FILENAME).pdf

view :
	$(OPEN) $(FILENAME).pdf &

cleanup :
	$(cleanup)

clean :
	$(cleanup)
	rm $(FILENAME).pdf -f

update :
	$(cleanup)
	rm $(FILENAME).pdf -f
	$(LATEX) $(FILENAME).tex
	$(LATEX) $(FILENAME).tex
	$(DVI2PDF) $(FILENAME).dvi

$(FILENAME).pdf : $(FILENAME).dvi
	$(DVI2PDF) $(FILENAME).dvi

$(FILENAME).dvi :
	$(LATEX) $(FILENAME).tex
	$(LATEX) $(FILENAME).tex
