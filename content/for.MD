# Laços _for_

São laços de repetição condicionais usualmente utilizados em situações que que o _loop_ é controlado por um contador.

Permite facilmente executar um código um número específico de vezes, ou percorrer um [arranjo de valores](array.MD).

```c
for ( comandoInicializacao; condicao; comandoPasso )
    comandoAExecutar
```

1. `comandoInicializacao` será executa no início do laço, geralmente utilizado para iniciar um contador.
1. `condicao` deverá ser verdadeiro para que a iteração ocorra. Caso falso, para de executar o laço.
1. `comandoAExecutar` será executado a cada iteração. Pode ser um comando composto, utilizando `{` e `}`.
1. `comandoPasso` será executado ao final da iteração, geralmente alterando o valor testado em `condicao`. Ao final, volta ao passo 2.

Exemplos:

Exibir uma frase 5 vezes.

```c
int i;
for (i = 1; i <= 5; i++)
    printf("\nEtec Adolpho Berezin");
```

Saída:

```
Etec Adolpho Berezin
Etec Adolpho Berezin
Etec Adolpho Berezin
Etec Adolpho Berezin
Etec Adolpho Berezin
```

Exibir a soma dos números de 1 a 100.

```c
int n, soma = 0;
for (n = 1; n <= 100; n++)
{
    soma += n;
}
printf("%d", soma); // Exibe 5050
```

## Laços aninhados

Podemos aninhar quantos laços forem necessários.

Exemplos:

Exibir um "quadrado" de `n_linhas` linhas e `n_colunas` colunas.

```c
int n_linhas = 6, n_colunas = 10;
int linha = 0;
for(linha = 0; linha < n_linhas; linha++)
{
    printf("\n");

    int coluna = 0;
    for(coluna = 0; coluna < n_colunas; coluna++)
        printf("*");
}
```

Saída:

```
**********
**********
**********
**********
**********
**********
```

## Componentes opcionais

Todos os componentes do _for_ são opcionais.

* Sem `comandoInicializacao`, a variável contadora deve ter sido inicializada anteriomente.

Ex.:

```c
int i = 1;
for (; i <= 5; i++)
    printf(" %d", i);
```

* Sem `condicao` é o mesmo que a condição sempre avaliar como verdadeiro, resultando em um _loop_ infinito.

Ex.:

```c
int i;
for (i = 1; ; i++)
    printf(" %d", i); // será exibido 'infinitas' vezes
```

* Sem `comandoPasso`, o valor da variável contadora deve ser atualizado dentro do laço, exatamente como em um laço _while_.

Ex.:

```c
int i;
for (i = 1; i <= 5;)
{
    printf(" %d", i);
    i++;
}
```

* Sem `comandoAExecutar`, o laço será executado normalmente pelo número de vezes necessário, mas nada será feito a cada iteração.

Ex.:

```c
int i;
for (i = 1; i <= 5; i++);
```

### Comandos `break` e `continue`

Tem o mesmo funcionamento que em outros laços.
