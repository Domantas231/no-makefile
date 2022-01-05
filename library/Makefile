CC:=gcc
LDFLAGS:=-Wall -o 
ASDFLAGS:=-Wall -c fPIC
BIN:=main
LIB:=reader
OBJS:=$(wildcard *.o)
LIBS:=$(wildcard *.so)

$(BIN): main.o $(LIB)
	$(CC) -L$(PWD) -Wall main.o -o $(BIN) -l$(LIB)

main.o: main.c
	$(CC) -c main.c

$(LIB): file_reader.c file_reader.h
	$(CC) -c -Wall -fPIC file_reader.c
	$(CC) -shared -o lib$(LIB).so file_reader.o

install:
	LD_LIBRARY_PATH=$(PWD)

uninstall:

clean:
	rm -f $(OBJS) $(LIBS) $(BIN)