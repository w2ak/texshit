LATEX:=lualatex -interaction=nonstopmode >/dev/null 2>/dev/null
.SECONDARY:

output.pdf: oneside.pdf twoside.pdf
	@echo PDFC oneside twoside \> output
	@pdftk A=oneside.pdf B=twoside.pdf cat A1-end B1-end output $@

%.pdf: %.aux
	@echo TEXC input \> $*
	@$(LATEX) -jobname=$* '\PassOptionsToClass{$*}{article}\input{input.tex}'

%.aux: input.tex
	@echo TEXC input \> $*
	@$(LATEX) -jobname=$* '\PassOptionsToClass{$*}{article}\input{$<}'
	@echo TEXC input \> $*
	@$(LATEX) -jobname=$* '\PassOptionsToClass{$*}{article}\input{$<}'
