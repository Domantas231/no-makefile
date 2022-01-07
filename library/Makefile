CC:=gcc
BIN:=main
LIB:=libreader.so
LIBNAME:=reader
SRC:=$(wildcard *.c)
OBJS:=$(SRC:.c=.o)

PREFIX:=/usr

.PHONY: all install uninstall clean

all: $(BIN)

$(BIN): main.o $(LIB)
	$(CC) -L$(PWD) -Wall $< -o $(BIN) -l$(LIBNAME)

main.o: main.c
	$(CC) -c $^

$(LIB): file_reader.o
	$(CC) -shared -o $(LIB) $^

file_reader.o: file_reader.c
	$(CC) -c -Wall -fPIC $^

install:
	install -d $(PREFIX)/lib
	install -d $(PREFIX)/include
	install -m 644 $(LIB) $(PREFIX)/lib/$(LIB)
	install -m 644 file_reader.h $(PREFIX)/include/file_reader.h

uninstall:
	$(RM) $(LIB) $(PREFIX)/lib/$(LIB)
	$(RM) $(LIB) $(PREFIX)/include/file_reader.h

clean:
	$(RM) $(OBJS) $(LIB) $(BIN)