# Estruturas (_structs_)

Permitem armazenar um conjunto de variáveis sob um mesmo identificador. São utilizadas para garantir uma maior organização no código.

Por exemplo, ao armazenar dados de um aluno em um sistema escolar, gostaríamos de ter todas suas informações armazenadas em uma única variável.

## Definição de um estrutura

Sintaxe:

```c
struct nomeTipoEstrutura { listaVariaveisComponentes; }
```

- `nomeTipoEstrutura` define um nome para a sua struct
- `listaVariaveisComponentes` é a lista de variáveis contidas na `struct`.

Exemplo:

Queremos uma estrutura para armazenar o RM e a idade de um aluno.

```c
struct dados_aluno {
    int rm;
    int idade;
}
```

Esta estrutura deve ser criada fora da função `main`.

## Declaração de variáveis de estrutura

Declaramos uma variável utilizando o nome do tipo de estrutura.

Exemplo:

```c
struct dados_aluno aluno1;
struct dados_aluno aluno2;
struct dados_aluno msi[40]; // array com 40 variáveis do tipo dados_aluno
```

## Acessando valores

Utilizamos o operador `.` (_member access operator_) para acessar um componente de uma estrutura.

```c
aluno1.rm = 301;
aluno1.idade = 16;

msi[0].rm = 500; // rm do primeiro aluno

printf("O aluno de RM %d possui %d anos.", aluno1.rm, aluno1.idade);
```

## Structs compostas

Podemos aninhar estruturas, criando objetos tão complexos quanto necessário.

Exemplo:

```c
#include <stdio.h>
#include <stdlib.h>
#include <locale.h>

// Armazena notas de 4 bimestres e sua média
struct notas_boletim {
    float nota1;
    float nota2;
    float nota3;
    float nota4;
    float media;
};

// Armazena um aluno, com RM, idade e suas notas
struct dados_aluno {
    int rm;
    int idade;
    struct notas_boletim boletim;
};

int main()
{
    setlocale(LC_ALL, "portuguese");

    struct dados_aluno aluno1;

    aluno1.rm = 301;
    aluno1.idade = 12;
    aluno1.boletim.nota1 = 10;
    aluno1.boletim.nota2 = 8;
    aluno1.boletim.nota3 = 7;
    aluno1.boletim.nota4 = 4;

    aluno1.boletim.media = (aluno1.boletim.nota1 + aluno1.boletim.nota2 + aluno1.boletim.nota3 + aluno1.boletim.nota4) / 4;

    printf("O aluno %d (%d anos), obteve média %.2f.", aluno1.rm, aluno1.idade, aluno1.boletim.media);

    return 0;
}
```

Saída:

```
O aluno 301 (12 anos), obteve média 7,25.
```