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
