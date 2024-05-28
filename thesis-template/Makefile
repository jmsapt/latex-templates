# Inputs
OUTDIR=./output
TYPE=pdf
NAME=$$(basename `pwd`)
SOURCE=./main.tex

RED=\033[0;31m
GREEN=\033[0;32m
NC=\033[0m

build:
	$(info Compiling PDF...)
	@ \
	pdflatex -interaction=nonstopmode -output-format=$(TYPE) -output-directory=$(OUTDIR) $(SOURCE); \
	if [ $$? -eq 0 ] ; then \
		rm -f $(NAME).$(TYPE); \
		cp $(OUTDIR)/main.$(TYPE) $(NAME).$(TYPE); \
	else \
		exit 1; \
	fi

check:
	$(info Compiling with draftmode...)
	@pdflatex -interaction=nonstopmode -draftmode -output-directory=$(OUTDIR) $(SOURCE) > /dev/null; \
	if [ $$? -eq 0 ] ; then \
		printf "$(GREEN)Success!$(NC)\n"; \
	else\
		printf "$(RED)FAILURE!$(NC)\n"; \
	fi
clean:
	rm $(OUTDIR)/**/*.* 

