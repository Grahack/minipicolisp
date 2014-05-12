# 11jan09abu
# (c) Software Lab. Alexander Burger

.SILENT:

bin = ../bin
picoFiles = main.c gc.c apply.c flow.c sym.c subr.c math.c io.c tab.c

picolisp: $(bin)/picolisp

.c.o:
	echo $*.c:
	emcc -c -emit-llvm $*.c -o $*.bc

$(picoFiles:.c=.o): pico.h

$(bin)/picolisp: $(picoFiles:.c=.o)
	mkdir -p $(bin)
	echo "  " link picolisp:
	emcc -o $(bin)/picolisp.js $(picoFiles:.c=.bc)


# Clean up
clean:
	rm -f *.o *.bc

# vi:noet:ts=4:sw=4
