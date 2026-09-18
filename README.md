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
- Um arquivo ```Makefile``` que possua as funcionalidades ```build``` para compilar e ```run``` para rodar o programa
  - Lembre-se que o programa deve receber um arquivo de texto ```.txt``` como entrada
  - O comando ```run``` deve ser capaz de receber um argumento que é o caminho para um arquivo ```.txt``` para ser utilizado como entrada do programa
- Um arquivo ```README.md``` com a descrição do seu trabalho, que deve indicar
  - A linguagem de programação usada (incluindo a versão)
  - Descrição de cada função e estrutura (como ```struct``` em ```C``` ou ```class``` em ```Java```) que são usadas no código
  - Em quais arquivos cada função e estrutura estão

### Exemplo de ```Makefile```
```makefile
INPUT = entrada.txt

build: main.cpp
  g++ -o programa main.cpp

run: programa.exe
  ./programa $(INPUT)
  ```

Aqui temos dois comandos: ```build``` e ```run```.

O comando ```make build``` irá executar a linha 4.
Ele irá compilar o conteúdo do arquivo ```main.cpp``` que contém o código fonte no arquivo executável ```programa.exe```.
Ele precisa que o arquivo ```main.cpp``` exista no mesmo diretório que o arquivo ```makefile```, por isso está sendo especificado depois dos dois pontos na linha 3.
Se o arquivo ```main.cpp``` estivesse dentro de uma subpasta ```src/```, por exemplo, a linha 3 mudaria para ```build: src/main.cpp``` e a linha 4 mudaria para ```g++ -o programa src/main.cpp``` (embora o ideal fosse criar variáveis pra cuidar disso).

O comando ```make run```irá executar a linha 7.
Ele precisa que o arquivo ```programa``` exista dentro do diretório (então precisa ser executado *depois* do ```build```).
Se você salvou o executável ```programa``` na subpasta ```out/```, você também precisa colocar o prefixo ```out/``` antes de ```programa``` nas linhas 6 e 7, assim como no parágrafo anterior.

O ```INPUT``` é uma variável definida dentro do arquivo ```makefile```.
Por padrão, definimos ele como ```entrada.txt```.
Se executarmos apenas o comando ```make run```, ele executará a linha 7 substituindo ```$(INPUT)``` pela string salva nele e, com isso, executará ```programa``` passando o arquivo ```entrada.txt``` como argumento (se ele existir no diretório).
Se você quiser utilizar um arquivo com outro nome, como ```entrada2.txt```, basta executar o comando ```make run INPUT=entrada2.txt``` para atribuir outra string à variável ```INPUT``` antes do comando ser executado.

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
