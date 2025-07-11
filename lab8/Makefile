ifeq ($(OS),Windows_NT)
    RM = cmd /C del /Q
else
    RM = rm -f
endif

all: core.exe

core.exe: main.o bin/persistencia.o bin/menu.o bin/pedido.o bin/util.o
	gcc -o $@ $^
main.o: src/main.c
	gcc -Iinclude -c $< -o $@
bin/persistencia.o: src/persistencia.c
	gcc -Iinclude -c $< -o $@
bin/menu.o: src/menu.c
	gcc -Iinclude -c $< -o $@
bin/pedido.o: src/pedido.c
	gcc -Iinclude -c $< -o $@
bin/util.o: src/util.c
	gcc -Iinclude -c $< -o $@

run: core.exe
	.\core.exe
clean:
ifeq ($(OS),Windows_NT)
	-$(RM) core.exe
	-$(RM) main.o
	-$(RM) bin\persistencia.o
	-$(RM) bin\menu.o
	-$(RM) bin\pedido.o
	-$(RM) bin\util.o
else
	-$(RM) core.exe
	-$(RM) main.o
	-$(RM) bin/persistencia.o
	-$(RM) bin/menu.o
	-$(RM) bin/pedido.o
	-$(RM) bin/util.o
endif
