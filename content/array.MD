# Arranjos (_arrays_)

São estruturas de dados que permitem armazenas um ou mais elementos do mesmo tipo em posições de memória consecutivas, facilitando o trabalho com múltiplos valores.

Um array possui a seguinte forma:

```c
tipo identificador[numeroItens]
```

Exemplo:

```c
int notas[4];
```

## Armazenando e lendo valores

Os valores em um array são acessados utilizando um índice, iniciando em zero.

Exemplo:
```c
double notas[4];
double media;

notas[0] = 3.5;
notas[1] = 8.5;
notas[2] = 10.;
notas[3] = 7.;
```

Nesse caso, o array fica assim:

|notas[]| | | | |
| - | - | - | - | - |
| índices | 0 | 1 | 2 | 3 |
| valores | `3.5` | `8.5` | `10.` | `7.` |

Também podemos ler os valores armazenados da mesma forma.

```c
media = (notas[0] + notas[1] + notas[2] + notas[3]) / 4.;
```

## Declaração e inicialização

Exemplos de inicialização.

Comando | Descrição
-- | --
`int a[10];` | declaração de um array com 10 posições, com valores indefinidos
`int b[3] = {17, 45, 33};` | declaração de um array com 3 posições, com valores iniciais
`int c[100] = { [17] 3, [79] = 5};` | Inicializando somente alguns elementos (elementos de índices 17 e 79), o sinal `=` é opcional
`int d[5000] = { [0 ... 4999] = 0 };` | Atribuindo valores a todos os elementos
`int e[50] = { [0 ... 24] = 0, [25 ... 49] = 1 };` | Atribuindo valores a uma faixa de índices
`int f[] = { 0, 1, 2 };` | tamanho implícito (3 itens)
`int g[] = { 0, 0, 0, [95] 1, 0 };` | tamanho implícito (97 itens)
`int tamanho = 100; int h[tamanho];` | 100 itens de valor indefinido

## Arrays multidimensionais

Os arrays que criamos até agora possuem somente uma dimensão. São comumente chamados de **vetores**.

Podemos criar arrays com mais de uma dimensão, chamados de **matrizes**. Para tal, definimos o número de 'linhas' e o número de 'colunas'.

Exemplo:

Definir a matriz `A` do seguinte formato:

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/b3cd77e085d029ca078a3d2ebfed96b38d92d5a2)

```c
int A[3][3] = { { 1, 2, 3 }, { 4, 5, 6}, { 7, 8, 9} };

/* Resultado na memória:
A[0][0] A[0][1] A[0][2] A[1][0] A[1][1] A[1][2] A[2][0] A[2][1] A[2][2]
   1       2       3       4       5       6       7       8       9
*/
```

## Strings

São armazenadas em C como vetores de `char` ou `unsigned char`. Ocupam uma posição para cada caracter, e uma adicional com o caracter nulo `\0`.

Exemplo:

```c
char nome[101]; // permite armazenar 100 caracteres 'úteis'
char escola[5] = { 'E', 't', 'e', 'c', '\0' };
char cep[] = { '1', '1', '7', '3', '0', '-', '0', '0', '0', '\0' }; // tamanho implícito (10 caracteres)
```

A inicialização pode ser simplificada utilizando aspas duplas, que adicionam o caracter nulo.

```c
char cidade[] = "Mongaguá"; // tamanho implícito (9 caracteres)
```

Para todos os demais efeitos, é uma array normal.

Exemplo:

```c
char uf[] = "SP"; uf[1] = 'C'; // uf vale "SC"
```

## Entrada de dados string

Devemos utilizam os especificadores `%s` para `scanf` e `printf`. Na entrada, devemos especificar o número de caracteres a serem lidos.

```c
char nome[51];
char sobrenome[51];

printf("Entre com os seus dados:\n\n");

printf("Nome: ");
scanf("%50s", nome);

printf("Sobrenome: ");
scanf("%50s", sobrenome);

printf("\nValores digitados:\n");
printf("\nNome = %s, Sobrenome = %s", nome, sobrenome);
```