compile: compile.ml
	ocamlfind ocamlc -o compile -thread -package oUnit -package sexplib -package str -linkpkg -g compile.ml

%.run: %.o main.c
	gcc -g -m32 -Wl,-no_pie -o $@ main.c $<

%.o: %.s
	nasm -f macho -o $@ $<

%.s: %.int compile
	./compile $< > $@

