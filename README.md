# Estruturas de Dados Avançadas
Repositório base para os trabalhos da disciplina de Estruturas de Dados Avançadas (CK0126)/Estruturas de Dados (CKP8077).
Cada pasta contém a especificação de um trabalho e casos de teste.
Você pode clonar esse repositório utilizando 
```
git clone https://github.com/victoitor/Estruturas-de-Dados-Avancadas.git
```

## Grupos

- Cada equipe da graduação pode ser formada por até 3 membros
- Cada equipe da pós-graduação pode ser formada por até 2 membros

## Envio
O envio de todos os trabalhos deve conter:
- O código-fonte
- Um arquivo [`Makefile`](https://www.gnu.org/software/make/manual/make.html) que possua as regras `build` para compilar e `run` para rodar o programa
  - O `run` deve ser capaz de ler um arquivo `.txt` fornecido pela variável `INPUT` que será a entrada do programa.
  - Estes comandos devem rodar no Linux.
- Um arquivo `README.md` com a descrição do seu trabalho, que deve indicar
  - A linguagem de programação usada (incluindo a versão)
  - Descrição de cada função e estrutura (como `struct` em `C` ou `class` em `Java`) que são usadas no código
  - Em quais arquivos cada função e estrutura estão

### Exemplo de `Makefile`
```makefile
INPUT = entrada.txt

build: main.cpp
  g++ -o programa main.cpp

run:
  ./programa $(INPUT)
```

Aqui temos dois comandos: `build` e `run`.

- O comando `make build` compila o conteúdo do arquivo `main.cpp` usando o compilador `g++` e cria o programa executável `programa` como saída.
- O comando `make run` coloca `programa` para rodar passando como entrada o arquivo fornecido pela variável `INPUT`.

Se você quiser utilizar outro arquivo de entrada, como `entrada2.txt`, basta redefinir a variável como a seguir.
```
make run INPUT=entrada2.txt
```

## Entrada e saída

- A entrada **precisa** ler o arquivo fornecido na variável `INPUT` do `Makefile` ao rodar seu programa com ```make run```, como no exemplo acima.
- A saída **precisa** ser impressa no terminal.

## Testes

Parte da nota dos trabalhos vêm do comportamento do seu programa com algumas entradas de teste.
Cada teste consiste em uma entrada específica e uma saída esperada, seu programa será executado com a entrada e a saída vai ser comparada com a saída esperada.
O caso de teste só será bem-sucedido se a saída for **exatamente igual** à saída esperada, incluíndo espaços e quebras de linha.

### Sugestão para realização de testes

Crie casos de teste formados por pares de entrada e saída esperada.
Coloque cada entrada em um arquivo (como ```entrada1.txt```, ```entrada2.txt```, etc.) e cada saída em um outro arquivo (como ```saida_esperada1.txt```, ```saida_esperada2.txt```, e etc.).
Execute o seu programa passando a entrada específica e escreva o output em um arquivo para a saída utilizando ```>```, por exemplo ```make run INPUT=entrada1.txt > saida1.txt```.
Isso fará com que a saída do programa com a entrada ```entrada1.txt``` seja salva no arquivo ```saida1.txt```.
Em seguida, compare a saída com a saída esperada.
Você pode utilizar o ```diff``` para isso (ou ```fc``` no ```cmd``` do Windows).
Por exemplo, ```diff saida1.txt saida_esperada1.txt > diferencas1.txt```.
Agora, se o arquivo ```diferencas1.txt``` estiver vazio, a saída é igual à saída esperada (o ```fc``` deve dizer ```no differences encountered```).

Vamos disponibilizar algumas entradas e saídas esperadas para cada trabalho.
Teste em cada uma delas e sinta-se livre para elaborar outros casos de teste, mas lembre-se: a saída deve ser **exatamente igual** à saída esperada para que o teste seja aprovado.
