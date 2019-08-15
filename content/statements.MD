# Comandos (_statements_)

São textos escrito em seu programa que permitem a execução de uma tarefa ou o controle do fluxo do programa.

Cada categoria de comandos possui a sua sintaxe própria.

## Comando nulo (_null statement_)

O menor comando em C é a expressão nula. É utilizada em alguma situações específicas para indicar que nada deve ser feito.

```c
;
```

## Comandos de expressões

Comandos que exigem a avaliação de uma expressão.

Exemplos:

- `41 + 1;` é um comando que instrui o programa a calcular a expressão. Nada é feito com o resultado (42). Na realidade, a maioria dos compiladores simplesmente ignora tais comandos.
- `x = 5 * 3;` é uma expressão que inclui um efeito colateral: uma atribuição. Nesse caso, o compilador sempre incluirá o comando.
- `printf("Hello world!");` é uma expressão que inclui uma chamada de função, que potencialmente possui efeitos colaterais. Este tipo de expressão nunca é ignorada pelo compilador.

## Comandos de decisão

Os comandos `if` e `switch` permitem a execução condicional algum comando. Leia mais [aqui](content/if.MD) e [aqui](content/switch.MD). Outro comando relacionado é `break`.

## Laços de repetição

Os comandos `while`, `do` e `for` permitem repetir a execução de algum comando em _loop_. Leia mais [aqui](content/while-do.MD) e [aqui](content/for.MD). Outros comandos relacionados com laços são `break` e `continue`.

## Comandos compostos (_compound statements_)

Os símbolos `{` e `}` permitem agrupar zero ou mais comandos em um grupo. Um grupo de comandos entre chaves é chamado de bloco.

Exemplos:

1. Blocos vazios:

```c
{}
```
e 

```c
{

}
```

Ambos são blocos definidos sem nenhum comando. Nada acontece.

2. Blocos _normais_:

```c
{ 
    int x, y;
    x = 1;
    y = 2;
    x = x + y;
}
```

3. Blocos aninhados:

```c
{ 
    int x, y;

    {
        x = 1;
        y = 2;
    }

    x = x + y;
}
```

Blocos podem ser aninhados livremente. Um bloco define o escopo e o tempo de vida de uma variável.

Exemplo:

```c
{
    int x = 1;
    {
        int y = 2;
        printf("%d", x);
        printf("%d", y);
    }
    printf("%d", x);
    printf("%d", y);
}
```

Acima, `x` existe durante todo o trecho, porém `y` só existe dentro do bloco interno. Por isso, o último comando resultará em erro de compilação.

## Outros

Também são comandos válidos:

- rótulos e desvio `goto`, não recomendados em programação estruturada;
- `return`, que será estudado em conjunto com funções;
- `typedef`, que será estudado em conjunto com a criação de tipos complexos.
