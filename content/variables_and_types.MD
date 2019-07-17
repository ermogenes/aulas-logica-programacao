# Variáveis

São espaços na memória principal utilizados para guardar valores a serem processados.

Possuem um identificador (nome), um tipo e um endereço de memória (de um tamanho de acordo com o tipo), e podem armazenar dados (de acordo com seu tamanho).

## Declaração de variáveis

Exemplos:

* Uma variável chamada `a` do tipo `float`, sem valor inicial definido:
```c
float a;
```

* Duas variáveis chamadas `b` e `c` do tipo `long int`, sem valor inicial definido:
```c
long int b, c;
```

* Uma variável chamada `d` do tipo `char`, com valor inicial `i`:
```c
char d = 'i';
```

* Duas variáveis chamadas `e` e `f` do tipo `int`, com valores iniciais `5` e `-7`, respectivamente:
```c
int e = 5, f = -7;
```

## Atribuição

Variáveis podem ter seus valores lidos e/ou gravados.

Uma atribuição permite a gravação de um valor em uma variável, e tem o seguinte formato:

```c
variável = expressão
```

Nessa situação `=` é o operador de atribuição, que vai avaliar a expressão à direita e gravar na posição de memória da variável identificada à esquerda.

Por exemplo, `a = 5` grava o valor `5` na variável `a`, `b = 1 + 7` avalia a expressão `1 + 7` (que resulta em `8`) e grava na variável `b`, e `c = a + 3` avalia a expressão `a + 3` (o valor atual de `a` acrescido de `3`) e grava o resultado em `c`.

Uma situação que pode parecer estranha, é que a mesma variável pode aparecer mais de uma vez na mesma expressão.

```c
int a = 2;

a = a * 3 + a;
// (2 * 3)
//   (6   + 2)
//       (8)

a = a + 1;
// (8)+ 1
//   (9)   
```

Neste caso, `a` valerá `8` ao final da primeira atribuição, e `9` ao final do trecho.

O exemplo abaixo efetua a soma entre duas parcelas:

```c
// Declarando 3 variáveis sem valor definido
int parcela_1, parcela_2, soma;

// Inicializando as parcelas, através de atribuições
parcela_1 = 5;
parcela_2 = 3;

// Atribuindo a soma, através da avaliação de uma expressão
soma = parcela_1 + parcela_2;
```

# Tipos de dados primitivos

São os tipos mais básico de uma linguagem, da qual outros tipos podem ser derivados. São armazenados diretamente na posição de memória indicada pela variável que a contém, ocupando posições contíguas quando necessário.

## Inteiros

Números inteiros, com ou sem sinal.

Tipo | Sinônimos | Tamanho | Limites
--- | --- | --- | ---
`signed char` | | 8 bits | -128 a 127
`unsigned char` | | 8 bits | 0 a 255
`char` | | 8 bits | Dependendo do sistema, é um `signed char` ou um `unsigned char`
`short int` | `short`, `signed short int`, `signed short` | 16 bits | -32,768 a 32,767
`unsigned short int` | `unsigned short` | 16 bits | 0 a 65,535
`int` | `signed int`, `signed` | 32 bits | -2,147,483,648 a 2,147,483,647
`unsigned int` | `unsigned` | 32 bits | 0 a 4,294,967,295
`long int` | `long`, `signed long int`, `signed long` | 32 bits* | -2,147,483,648 a 2,147,483,647
`unsigned long int` | `unsigned long` | 32 bits* | 0 a 4,294,967,295
`long long int` | `long long`, `signed long long int`, `signed long long` | 64 bits | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807
`unsigned long long int` | `unsigned long long` | 64 bits | 0 a 18,446,744,073,709,551,615

\* Pode variar dependendo do sistema utilizado (os valores acima são [utilizados no Windows](https://docs.microsoft.com/en-us/cpp/cpp/integer-limits?view=vs-2019)).

Exemplos de declaração e atribuição:

```c
char letra_inicial_nome = 'E';
unsigned char idade = 17;
int populacao_br = 210192648;
```

## Reais

Números fracionais. 

Seus tamanhos são altamente dependentes do sistema utilizado. Estes parâmetros ficam em `float.h`. Os valores abaixo são [utilizados no Windows](https://docs.microsoft.com/en-us/cpp/cpp/floating-limits?view=vs-2019).

Tipo | Tamanho | Limites
--- | --- | ---
`float` | 32 bits | 1.175494351e-38 a 3.402823466e+38
`double` | 64 bits | 2.2250738585072014e-308 a 1.7976931348623158e+308
`long double ` | 64 bits | 2.2250738585072014e-308 a 1.7976931348623158e+308

São armazenados em [ponto flutuante](https://floating-point-gui.de/), que possuem precisão finita, o que indica que nem todos os números podem ser representados com exatidão. Sendo assim, considere todos os números como uma aproximação, especialmente quando comparando igualdade entre dois valores.

Exemplos de declaração e atribuição:

```c
double valor  = 1.5;     // literais em ponto flutuante são sempre do tipo 'double'
float credito = 125.30F; // use 'f' ou 'F' para indicar explicitamente que é um 'float'
long double y = .5e-10L; // use 'l' ou 'L' para indicar explicitamente que é um 'long double'
```

## Complexos

A versão C99 introduziu [números complexos](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#Complex-Number-Types).

# Regras para identificadores

A criação de identificadores segue as seguintes regras:

- Pode incluir letras, dígitos e o símbolo `_`;
- O primeiro caracter não pode ser um dígito;
- Diferencia maiúsculas e minúsculas;
- Não pode coincidir com as [palavras reservadas da linguagem](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#Keywords):
```
auto break case char const continue default do double else enum extern
float for goto if int long register return short signed sizeof static
struct switch typedef union unsigned void volatile while
```

Exemplos válidos:
```
variavel_2
x
a3
idade
Idade
```

Exemplos inválidos:
- `3abcd4`, por iniciar com dígito
- `ed@23`, por conter `@`
- `#35`, por conter `#` e por iniciar com dígito
- `asda%`, por conter `%`
- `ação`, por conter os caracteres especias `ç` e `ã`
- `valor pedágio`, por conter espaço em branco e `à`
- `if`, por ser uma palavra reservada
- `numero-anterior`, por conter `-`
