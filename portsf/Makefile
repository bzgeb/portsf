#makefile for portsf
POBJS = ieee80.o portsf.o

# CFLAGS = -I ../include -D_DEBUG -g
# on strange 64 bit platforms must define CPLONG64
CFLAGS = -Dunix -O2 -I ../include

CC=gcc

.c.o:	$(CC) -c $(CFLAGS) $< -o $@ 

.PHONY:	clean veryclean
all:	libportsf.a


clean:
	-rm -f $(POBJS)

veryclean:
	-rm -f $(POBJS) 
	rm -f libportsf.a; 

libportsf.a:	$(POBJS)
	ar -rc libportsf.a $(POBJS)
	ranlib  libportsf.a

install:	libportsf.a
	cp libportsf.a ../lib
#
#	dependencies
#
portsf.c:	../include/portsf.h ieee80.h
