IMAGES := branch1 branch2 branch3 branch4 branch5 branch6 branch7 branch8 branch9 \
	branching_full_example

all: $(IMAGES)

$(IMAGES): %: ../%.png

../%.png: %.pdf
	magick -density 192 $< $@

%.pdf: %.tex
	pdflatex $<
