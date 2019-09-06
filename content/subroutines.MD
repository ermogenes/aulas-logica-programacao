# Subrotinas

É desejável que se separe trechos de programas em subrotinas. Estas separações permitem uma melhor organização do programa e o reaproveitamento de código. É a base de todas as bibliotecas.

Na linguagem C, as subrotinas são implementadas através de funções.

## Funções

Todo programa tem ao menos uma função: _main_, executada no início da execução do programa.

Ex.:

```c
int main (void)
{
    // Aqui vão as instruções do programa
    return 0;
}
```

Neste exemplo, o programa contém somente a definição de uma função (`main`), com um único comando composto (bloco `{}`). Este comando é executado ao iniciar o programa (por causa do seu nome). Esta função não recebe argumentos (`void`), mas promete retornar um valor inteiro (`int` precedendo o nome da função), o que se confirma na instrução `return` com o valor `0`.

### Elementos de uma função

#### Declaração

Assim como as variáveis, devemos declarar uma função antes do seu primeiro uso. _A função `main` é uma exceção a esta regra, já que sempre deve estar presente, e sempre é a primeira a ser executada._

Para declarar uma função, precisamos de um identificador, um tipo de retorno, e uma lista de argumentos:

```
tipoRetorno identificadorFuncao (listaArgumentos);
```

Ex.:

Queremos uma função que calcule o dobro de um número inteiro informado.

Identificador: `dobro`
Argumentos: `int numero`, indicando o número a ser multiplicado por 2
Tipo de retorno: `int`, já que o dobro de um inteiro é outro inteiro

Assim, a declaração desejada é:

```c
int dobro(int numero);
```

Ex. 2:

Queremos uma subrotina que exiba uma mensagem fixa de erro, para ser executada sempre que necessário.

Identificador: `exibeErro`
Argumentos: nenhum, pois a mensagem é fixa
Tipo de retorno: nenhum, pois não há cálculo a ser executado

Assim, a declaração desejada é:

```c
void exibeErro(void);
```

`void` é uma palavra reservada da linguagem que, nesse caso, significa que não há retorno e não há argumentos (respectivamente).

Este tipo de subrotina sem retorno é chamado de _procedimento_.

#### Definição

Após a definição, devemos criar a lógica da nossa subrotina. Fazemos isso através da sua definição, da mesma maneira que em _main_: através de um comando composto.

```
tipoRetorno identificadorFuncao (listaArgumentos)
{
    // comandos que implementam a lógica da função
}
```

Se a função tiver um tipo de retorno diferente de `void`, deve possuir uma chamada ao comando `return`, com uma expressão do tipo indicado.

Ex.:

```c
int dobro(int numero)
{
    return numero * 2;
}
```

Nesse caso, o resultado da expressão `numero * 2` é um número inteiro, retornado pelo comando `return`.

Ex. 2:

```c
void exibeErro(void)
{
    printf("\nErro! Por favor verifique os dados e tente novamente.");
    getchar();
}
```
Nesse caso, não temos o comando `return`.

#### Argumentos

Uma função pode receber nenhum, um ou mais argumentos. Argumentos são os valores necessários para que a função seja executada, e estão disponíveis durante a execução dos comandos contidos na definição da função.

Ex.:

```c
int soma(int parcela1, int parcela2)
{
    int resultado = parcela1 + parcela2;
    return resultado;
}
```

Também são chamados de _parâmetros_.

#### Chamada

Informa que uma subrotina deve ser executada. Se houver argumentos, os valores serão copiados para variáveis locais à definição da função, na ordem indicada. Se houver um retorno, ele pode ser atribuído utilizando a chamada como uma expressão.

Ex.:

```
int x = 1, z = 0;

z = soma(x, 5);

printf("%d somado com 5 é %d", z); // exibe '1 somado com 5 é 6'
```

Ex. 2:

```c
if (z != 6)
{
    exibeErro();
}
```

### Exemplo completo

```c
#include <stdio.h>
#include <stdlib.h>

int produto(int a, int b);
void exibeErro(void);

int main(void)
{
    int n1, n2, r;
    printf("Digite n1..:"); scanf("%d", &n1);
    printf("Digite n2..:"); scanf("%d", &n2);

    r = produto(n1, n2);

    if (r == 0)
    {
        printf("\nVocê digitou 0 em algum dos números.");
        exibeErro();
    }
    else if (r < 0)
    {
        printf("\nUm dos números digitados é negativo.");
        exibeErro();
    }
    else
    {
        printf("\nn1 * n2 = %d", r);
    }

    return 0;
}

int produto(int a, int b)
{
    return a * b;
}

void exibeErro(void)
{
    printf("\nErro! Por favor verifique os dados e tente novamente.");
    getchar();
}
```