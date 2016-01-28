OPTIONS= -pthread -Wall
SHELL=/bin/bash

all : GOL

GOL : GoL.o
	mkdir -p bin
	@gcc ${OPTIONS} GoL.o -o bin/GOL

GoL.o : GoL.c
	@gcc ${OPTIONS} -c -o GoL.o GoL.c

clean:
	@rm -rf bin/GOL bin *~ *.o outputMatrix/*.txt testsMatrix/*.txt

mesures:
	@touch outputMatrix/matrixSeqRes_0{1..3}.txt
	@touch outputMatrix/matrixParaRes_0{1..3}.txt
	@touch outputMatrix/resultat.txt
	@for i in {1..3} ; do \
		./GOL inputMatrix/matrixSeq_0$$i.txt outputMatrix/matrixSeqRes_0$$i.txt seq >> outputMatrix/resultat.txt; \
	done;
	@for i in {1..3} ; do \
		./GOL inputMatrix/matrixPara_0$$i.txt outputMatrix/matrixParaRes_0$$i.txt para >> outputMatrix/resultat.txt; \
	done;
	@echo "Opération terminé";

tests:
	@for i in {1..3} ; do \
		grep -vxFf outputMatrix/matrixSeqRes_0$$i.txt outputMatrix/matrixParaRes_0$$i.txt > testsMatrix/diff_SeqVsParallel0$$i.txt || true; \
	done;
	@cmp testsMatrix/diff_SeqVsParallel01.txt testsMatrix/diff_SeqVsParallel02.txt > testsMatrix/resultatFinalTests.txt || true
	@cmp testsMatrix/diff_SeqVsParallel02.txt testsMatrix/diff_SeqVsParallel03.txt >> testsMatrix/resultatFinalTests.txt || true
	@if [ \! -s testsMatrix/resultatFinalTests.txt ]; then echo " IL N'Y A PAS D'ERREURS DANS LES TESTS"; else echo " IL Y A DES ERREURS DANS LES TESTS."; fi
