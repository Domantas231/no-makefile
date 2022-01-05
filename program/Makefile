CC:=gcc
LDFLAGS:=-Wall -o 
ASDFLAGS:=-Wall -c
BIN:=main
SRC:=$(wildcard *.c)
OBJS=$(wildcard *.o)

all: $(BIN)

$(BIN): main.o maths.o usage.o
	$(CC) $(LDFLAGS) $(BIN) main.o maths.o usage.o

main.o: main.c
	$(CC) $(ASDFLAGS) main.c

maths.o: maths.c maths.h
	$(CC) $(ASDFLAGS) maths.c

usage.o: usage.c usage.h
	$(CC) $(ASDFLAGS) usage.c

install:
	sudo cp maths.h /usr/include && sudo cp usage.h /usr/include

uninstall:
	sudo rm /usr/include/maths.h && sudo rm /usr/include/usage.h

clean:
	rm -f $(OBJS) $(BIN)