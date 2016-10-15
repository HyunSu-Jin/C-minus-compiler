#
# makefile for TINY
# Borland C Version
# K. Louden 2/3/98
#

CC = gcc

CFLAGS = 

OBJS = y.tab.o lex.yy.o main.o util.o symtab.o

cminus: $(OBJS)
	$(CC) $(CFLAGS) $(OBJS) -o cminus

y.tab.o: cminus.y globals.h
	bison -d cminus.y --yacc
	$(CC) $(CFLAGS) -c y.tab.c

lex.yy.o: cminus.l scan.h util.h globals.h
	flex -o lex.yy.c cminus.l
	$(CC) $(CFLAGS) -c lex.yy.c

main.o: main.c globals.h util.h scan.h
	$(CC) $(CFLAGS) -c main.c

util.o: util.c util.h globals.h
	$(CC) $(CFLAGS) -c util.c

symtab.o: symtab.c symtab.h
	$(CC) $(CFLAGS) -c symtab.c


