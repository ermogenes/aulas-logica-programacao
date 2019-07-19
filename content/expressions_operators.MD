# Expressões e operadores

## Expressões

Uma expressão é uma sequência que consiste de pelo menos um operando e zero ou mais operadores. O resultado de uma expressão é um único valor.

Exemplos de expressões:

```c
12
5 + 3
(x + 4) * -1
sqrt(2)
```

Parênteses alteram a ordem de avaliação, assim como na matemática. Por exemplo, a expressão

![](https://github.com/ermogenes/aulas-logica-programacao/raw/master/content/eq1.png)
 
pode ser escrita em C como:

```c
  (1 + (2 * 1 * (1 - .5 + (2 + 2 * (2 + 3)) / (7 - 3)))) / 2 - 1 
```

Que será executada nesta ordem, resultando em ```3.```:

```c
                                                             - 1 
. (                                                    ) / 2    .
..(1 +                                                )     .   .
...    (2 * 1 *                                      )..    .   .
...    .         1 - .5 +                            ...    .   .
...    .        .         (2 +            ) / (7 - 3)...    .   .
...    .        .         .    2 *        .   |-----|...    .   .
...    .        .         .   .    (2 + 3).      4   ...    .   .
...    .        .         .   .    |-----|.          ...    .   .
...    .        .         .   .       5  ..          ...    .   .
...    .        .         .   |----------|.          ...    .   .
...    .        .         .        10     .          ...    .   .
...    .        .         |---------------|          ...    .   .
...    .        .                  12                ...    .   .
...    .        .         |--------------------------|..    .   .
...    .        .                       3.           ...    .   .
...    .        |------------------------------------|..    .   .
...    .                          3.5                 ..    .   .
...    |----------------------------------------------|.    .   .
...                          7.                        .    .   .
..|----------------------------------------------------|    .   .
..                       8.                                 .   .
.|----------------------------------------------------------|   .
.                              4.                               .
|---------------------------------------------------------------|
                               3.                                
```

Testando:

```c
double resultado_expressao = (1 + (2 * 1 * (1 - .5 + (2 + 2 * (2 + 3)) / (7 - 3)))) / 2 - 1;
printf("%.2f", resultado_expressao); // saída: 3.00
```

## Operadores

Um operador pode possui de um a três operandos, sendo chamado, respectivamente, de operador unário, binário ou ternário. Uma operação resulta em um único resultado.

### Operadores aritméticos

A linguagem C possui operadores binários para as operações aritméticas básicas.

Operador | Operação | Exemplo | Resultado
--- | --- | --- | ---
`+` | Soma | `1 + 2.5` | `3.5`
`-` | Subtração | `1 - 5` | `-4`
`*` | Multiplicação | `2 * 3` | `6`
`/` | Divisão | `5. / 2.` | `2.5`
`%` | Resto da divisão | `5 % 2` | `1`

Realizar uma divisão por zero resultará em erro.

O resultado de uma divisão entre números inteiros resultará em uma divisão inteira. Por exemplo, `5 / 2` é avaliado como `2`, já que `5` e `2` são inteiros.

Os operadores unários `+` e `-` fazem o papel do sinal aritmético. Por exemplo, `-(2+1)` é o oposto de `2+1`, resultando em `-3`.

### Operadores relacionais (ou de comparação)

Operadores utilizados para comparação entre valores numéricos. Retornam `1` no caso verdadeiro (comumente chamado de `true`) e `0` no caso falso (`false`). São amplamente utilizados em conjunto com o comando `if`, para criar desvios condicionais.

Operador | Operação | Exemplo | Resultado
--- | --- | --- | ---
`==` | Igualdade | `2 == 2` | Verdadeiro
`!=` | Desigualdade | `2 != 3` | Verdadeiro
`<` | Menor que | `3 < 2` | Falso
`>` | Maior que | `3 > 2` | Verdadeiro
`<=` | Menor que ou igual a | `2 <= 2` | Verdadeiro
`>=` | Maior que ou igual a | `3 >= 2` | Verdadeiro

### Operadores lógicos

São utilizados em conjunto com os operadores de comparação para criar [expressões booleanas](https://pt.wikipedia.org/wiki/Boolean) complexas.

Em C, qualquer valor diferente de `0` é avaliado como verdadeiro. Somente um valor `0` será avaliado como falso.

Abaixo, os operadores e suas tabelas-verdade.

- Operador de negação `!` (unário): inverte o valor lógico do operando

`p` | `!p`
--- | ---
Falso | Verdadeiro
Verdadeiro | Falso

- Operador 'E' `&&`: o resultado é verdadeiro somente quando ambos os operandos são verdadeiros

`p` | `q` | `p && q`
--- | --- | ---
Falso | Falso | Falso
Falso | Verdadeiro | Falso
Verdadeiro | Falso | Falso
Verdadeiro | Verdadeiro | Verdadeiro

Na operação `p && q`, caso `p` avalie como falso, `q` é irrelevante e [não será processado](https://pt.wikipedia.org/wiki/Avalia%C3%A7%C3%A3o_de_curto-circuito).

- Operador 'OU' `||`: o resultado é falso somente quando ambos os operandos são falsos

`p` | `q` | `p \|\| q`
--- | --- | ---
Falso | Falso | Falso
Falso | Verdadeiro | Verdadeiro
Verdadeiro | Falso | Verdadeiro
Verdadeiro | Verdadeiro | Verdadeiro

Na operação `p || q`, caso `p` avalie como verdadeiro, `q` é irrelevante e [não será processado](https://pt.wikipedia.org/wiki/Avalia%C3%A7%C3%A3o_de_curto-circuito).

### Incremento e decremento

Acrescentam (`++`) ou reduzem (`--`) `1` do valor de uma variável.

Exemplo: 

```c
int x = 1;
x++; // x vale 2
x--; // x volta a valer 1
```

Nos casos acima, não faria diferença utilizá-los no sufixo (como em `x++`) ou no prefixo (como em `++x`). Porém, em alguns casos, isso pode fazer toda a diferença.

Exemplo:

```c
int x, y, z;

x = 5;
y = 2;

z = y + x--;           // decrementa x depois de somar com y
printf("\nz = %d", z); // exibe 7
printf("\nx = %d", x); // exibe 4

z = y + --x;           // decrementa x antes de somar com y
printf("\nz = %d", z); // exibe 5
printf("\nx = %d", x); // exibe 3
```

### Outros operadores

Existem outros operadores em C, para efetuar [operações bit-a-bit](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#Bitwise-Logical-Operators), [deslocamento](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#Bit-Shifting), recuperar o [tamanho de uma variável ou de um tipo](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#The-sizeof-Operator), entre outros.


### Atribuição

Além do operador simples de atribuição `=`, podemos simplificar algumas construções de operações binárias utilizando operadores compostos.

Por exemplo, `x = x + 5` é a mesma coisa que `x += 5`.

Podemos utilizar este método com os operadores aritméticos (`+`, `-`, `*`, `/` e `%`), com os operadores bit-a-bit, e com os operadores de deslocamento.

### Operador condicional ternário

O operador ternário `? :` será estudado juntamente com as decisões condicionais.

### Ponteiros

Operadores unários que permitem operar com os endereços de memória.

Operador | Operação
--- | ---
`&` | Endereço de memória
`*` | Valor contido no endereço

```c
int v1 = 42;
int v2;
int *ponteiro_para_v1;

ponteiro_para_v1 = &v1; // ponteiro_para_v1 receberá o endereço de v1

/* v2 receberá o valor contido no endereço armazenado em ponteiro_para_v1, que no caso coincide com v1 */
v2 = *ponteiro_para_v1; // equivalente a v2 = v1;

*ponteiro_para_v1 = 5; // altera o valor de v1

printf("v1 = %d, v2 = %d", v1, v2); 

/* saída: 
v1 = 5, v2 = 42
*/
```

## Type cast

Permite que se avalie uma expressão convertendo um valor para um tipo específico.

Exemplo:

```c
float r;

int a = 9;
int b = 2;

r = a / b;

printf("%.2f", r);

/* saída;
4.00
*/
```

_Por que o resultado exibido não é `4.5`, já que `r` é `float`?_

Vamos tentar usar _type casting_ para forçar a avaliação como float:

```c
...

r = (float) (a / b);

printf("%.2f", r);

/* saída;
4.00
*/
```

Nesse caso, continua tudo igual, já que `a / b` é avaliado como `4` e só depois convertido para `4.`.

Temos que usar _type casting_ antes da divisão, em um dos operandos:

```c
...

r = a / (float)b;

printf("%.2f", r);

/* saída;
4.50
*/
```
