# Bibliotecas de funções - C Standard Library

A especificação ISO C deine um conjunto de bibliotecas que toda implementação de C deve incluir. Estas funções disponibilizam facilidades aos desenvolvedores e permitem a portabilidade entre sistemas e a redução da curva de aprendizado e de desenvolvimento.

Para se utilizar uma função de biblioteca é necessário criar a referência para que o linkeditor copie o código-objeto correspondente para o seu executável, durante o processo de compilação.

Para referenciar uma biblioteca, use a diretiva `#include` no início do arquivo:


Exemplos:
```c
#include <stdio.h>
#include <stdlib.h>
#include <math.h>
#include <time.h>
```

Algumas das bibliotecas padrão do C:

Biblioteca | Descrição
--- | ---
`stdio.h` | Entrada e saída
`stdlib.h` | Funções de uso geral
`locale.h` | Configuração de localização
`math.h` | Funções matemáticas
`ctype.h` | Manipulação de caracteres
`string.h` | Manipulação de strings
`time.h` | Manipulação de data e hora

Uma [referência completa da implementação GNU C Library](https://www.gnu.org/software/libc/manual/html_mono/libc.html) pode ser encontrada na página oficial do projeto.

## Entrada e saída - `stdio.h`

Função | Descrição
--- | ---
`getchar` | Lê um caracter da entrada padrão
`putchar` | Escreve um caracter na saída padrão
`puts` | Escreve uma string na saída padrão, incluindo uma quebra de linha
`printf` | Envia saída formatada para a saída padrão
`scanf` | Lê uma entrada formatada da entrada padrão

Define também as funções para lidar com arquivos.

## Funções de uso geral - `stdlib.h`

Função | Descrição | Exemplo
--- | --- | ---
`getenv` | Obtém o valor de uma variável do sistema | `getenv("PATH")`
`system` | Envia um comando para ser executado pelo sistema | `system("dir")`
`abs` | Retorna o valor absoluto de um número inteiro | `abs(-5)` retorna `5`
`rand` | Retorna um número pseuso-aleatório | `rand()` retorna um `int` aleatório (`rand() % 6` limita o número entre `0` e `5`)
`srand` | Especifica a semente do gerador de números pseuso-aleatórios | `srand(time(0))` cria uma semente baseada na hora atual

Define também as funções para alocação dinâmica de memória.

## Configuração de localização - `locale.h`

Função | Descrição | Exemplo
--- | --- | ---
`setlocale` | Define a localização a ser utilizada | `setlocale(LC_ALL,"portuguese")` configura tudo para `pt-br`

## Funções matemáticas - `math.h`

Grupo | Função | Descrição | Exemplo
--- | --- | --- | ---
Trigonométricas | `sin` | Seno | `sin(PI/180 * 45)` retorna `0.707107`
. | `cos` | Cosseno | `cos(PI/3)` retorna `.5`
. | `tan` | Tangente | `tan(0)` retorna `0.`
. | `asin` | Arco seno | `asin(sin(1))` retorna `1.`
. | `acos` | Arco cosseno | `acos(.5)` retorna `1.047198` (π/3)
. | `atan` | Arco tangente | `atan(0)` retorna `0.`
Exponenciais | `exp` | _e_ elevado à potência indicada | `exp(1)` retorna `2.718282` (_e_)
. | `log` | Logartimo natural (base _e_) | `log(2.718282)` retorna `1.`
. | `log10` | Logaritmo comum (base 10) | `log10(1000)` retorna `3.`
Potenciação | `pow` | Potenciação | `pow(2, 3)` retorna `8.`
. | `sqrt` | Raiz quadrada | `sqrt(25)` retorna `5.`
Outras | `fabs` | Valor absoluto de um número fracionário | `fabs(-34.5567)` retorna `34.5567`
. | `fmod` | Resto da divisão, com números fracionários |  `fmod(5.1, 2)` retorna `1.1`
. | `modf` | Separa a parte inteira da parte decimal de um número fracionário | `modf(5.7, &i);` grava `5.` em `i` e retorna `.7`

Aproximação de inteiros

Função | Descrição
--- | ---
`ceil` | Menor valor inteiro maior ou igual ao indicado
`floor` | Maior valor inteiro menor ou igual ao indicado
`trunc` | Inteiro mais próximo de zero
`round` | Arredondamento

Exemplos:

Número | `ceil` | `floor` | `trunc` | `round`
---: | ---: | ---: | ---: | ---:
`1.0` | `1.0` | `1.0` | `1.0` | `1.0`
`-1.0` | `-1.0` | `-1.0` | `-1.0` | `-1.0`
`1.2` | `2.0` | `1.0` | `1.0` | `1.0`
`1.5` | `2.0` | `1.0` | `1.0` | `2.0`
`1.8` | `2.0` | `1.0` | `1.0` | `2.0`
`-1.2` | `-1.0` | `-2.0` | `-1.0` | `-1.0`
`-1.5` | `-1.0` | `-2.0` | `-1.0` | `-2.0`
`-1.8` | `-1.0` | `-2.0` | `-1.0` | `-2.0`

Gráfico das funções ([arquivo Geogebra](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/Arredondamentos.ggb)):

- `y = ceil(x)`

![y = ceil(x)](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/ceil.png)

- `y = floor(x)`

![y = floor(x)](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/floor.png)

- `y = trunc(x)`

![y = trunc(x)](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/trunc.png)

- `y = round(x)`

![y = round(x)](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/round.png)

## Manipulação de caracteres - `ctype.h`

Função | Descrição | Exemplo
--- | --- | ---
`tolower` | Equivalente minúsculo de um caracter | `tolower('A')` retorna `'a'`
`toupper` | Equivalente maiúsculo de um caracter | `toupper('a')` retorna `'A'`
`isalpha` | Avalia se um caracter é alfabético (`A-Z` ou `a-z`) | `isalpha('x')` retorna verdadeiro, `isalpha('9')` retorna falso
`isdigit` | Avalia se um caracter é dígito (`0-9`) | `isdigit('4')` retorna verdadeiro, `isdigit('n')` retorna falso
`isalnum` | Avalia se um caracter é alfanumérico (alfabético ou dígito) | `isalnum('5')` retorna verdadeiro, `isalnum('M')` retorna verdadeiro, `isalnum('$')` retorna falso

## Manipulação de strings - `string.h`

Função | Descrição | Exemplo
--- | --- | ---
`strlen` | Número de caracteres da string | `strlen("abc")` retorna `3`
`strcpy` | Grava um valor string em uma variável | `strcpy(s, "texto")` grava `"texto"` em `s`
`strcmp` | Compara 2 strings e retorna `0.` se forem iguais, `1.` se a primeira for maior e `-1.` se a segunda for maior | `strcmp("bcd", "abc")` retorna `1.`, `strcmp("bcd", "cde")` retorna `-1.`, `strcmp("xyz", "xyz")` retorna `0.`
`strcat` | Adiciona um literal string ao final de uma variável | `char s[20] = "variavel"; strcat(s, "literal");` grava `"variavelliteral"` em `s`

## Manipulação de data e hora - `time.h`

Datas e horas na `time.h` são armazenadas em um tipo chamado `time_t`, que pode variar de acordo com o sistema (no GNU C Library é um `long int`). O valor `0` representa o valor inicial, 0h de 1 de janeiro de 1970 (chamado de _época_). A cada segundo este valor é incrementado em 1. Portanto, o valor indica quantos segundos se passaram da época até o momento indicado.

Exemplo:

```c
time_t tempo = time(NULL); // grava a data/hora atual na variável tempo

printf("Data/hora atual: %s\n", ctime(&tempo));

printf("A partir de 1 de janeiro de 1970 passaram-se:\n\n");
printf("Segundos: %d\n", tempo);
printf("Minutos: %d\n", tempo/60);
printf("Horas: %d\n", tempo/60/60);
printf("Dias: %d\n", tempo/60/60/24);
printf("Semanas : %d\n", tempo/60/60/24/7);

/* Saída:
Data/hora atual: Fri Jul 19 13:31:02 2019

A partir de 1 de janeiro de 1970 passaram-se:

Segundos: 1563553862
Minutos: 26059231
Horas: 434320
Dias: 18096
Semanas : 2585
*/
```

Função | Descrição
--- | ---
`time` | Número de segundos desde a época
`ctime` | Retorna uma string com a data/hora legível
