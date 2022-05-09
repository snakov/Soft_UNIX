CC = gcc;
CFLAGS = -I include -g -Wall -O2;
LIBS = -Llib -lmyLib
TARGET = bin/myExe

OBJ = obj/A.o obj/B.o
LIB = lib/libmyLib.a
DOC = doc/myLib.pdf

all: $(TARGET)
lib: $(LIB)
doc: $(DOC)

$(TARGET): $(LIB) src/myExe.c
	$(CC) src/myExe.c  $(CFLAGS) $(LIBS) -o $@

$(LIB): $(OBJ)
	ar -rc $(LIB) $(OBJ)

obj/%.o: src/%.c
	$(CC) $(CFLAGS)  -c $< -o $@

$(DOC): doc/myLib.tex
	cd doc && pdflatex -pdf myLib.tex

clean:
	$(RM) $(OBJ) $(TARGET) 
	cd doc && pdflatex -c myLib.tex
