# 11jan09abu
# (c) Software Lab. Alexander Burger

.SILENT:

bin = ../bin
picoFiles = main.c gc.c apply.c flow.c sym.c subr.c math.c io.c tab.c

picolisp: $(bin)/picolisp

.c.o:
	echo $*.c:
	clang $*.c

$(picoFiles:.c=.o): pico.h

$(bin)/picolisp: $(picoFiles:.c=.o)
	mkdir -p $(bin)
	echo "  " link picolisp:
	gcc -o $(bin)/picolisp $(picoFiles:.c=.o) -lc -lm
	strip $(bin)/picolisp


# Clean up
clean:
	rm -f *.o

# vi:noet:ts=4:sw=4
