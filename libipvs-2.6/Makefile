# Makefile for libipvs

CC		= gcc
CFLAGS		= -g -O2  -I/usr/src/linux/include -I/usr/src/linux/include -DLIBIPVS_USE_NL -Wall -Wunused

export OBJS += libipvs.a

STATIC_LIB	= libipvs.a

all:		$(STATIC_LIB)

$(STATIC_LIB):	libipvs.o ip_vs_nl_policy.o
		ar rv $@ $^
		rm $^

%.o:		%.c
		$(CC) $(CFLAGS) -c -o $@ $<

clean:
		rm -f *.[ao] *~ *.orig *.rej core

distclean:	clean
		rm -f Makefile
