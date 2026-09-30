INPUT = entrada.txt

# O comando `make build` compila o conteúdo do arquivo `main.cpp` usando o compilador `g++` e cria o programa executável `programa` como saída.
.PHONY build
build: main.cpp
	  g++ -o programa main.cpp

# O comando `make run` coloca `programa` para rodar passando como entrada o arquivo fornecido pela variável `INPUT`.
.PHONY run
run:
	  ./programa $(INPUT)
