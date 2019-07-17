# Entrada e saída

Permitem o _input_ (entrada)  e o _output_ (saída) de dados utilizando a entrada padrão (geralmente teclado) e a saída padrão (geralmente tela do monitor) do sistema.

As funções abaixo fazem parte da Standard Library do C e estão definidas na biblioteca `stdio.h`.

## Saída simples

### `putchar`

Exibe um caractere.

```c
putchar('X'); // saída: X

putchar(65);  // saída: A

char c = '!';
putchar(c);   // saída: !

// Ao final terá exibido: XA!
```

### `puts`

Exibe uma string seguida de uma quebra de linha.

```c
puts("Olá, usuário.");
puts("Seja bem-vindo!");

/* saída:
Olá, usuário.
Seja bem-vindo!

*/
```

## Saída formatada

### printf

_em breve_

## Entrada simples

### `getchar`

Lê o próximo caracter do buffer de teclado como um `unsigned char` e o retorna como um `int`.

```c
getchar();  // aguarda a entrada de um caracter, sem gravar o valor em nenhuma variável

int tecla;         // getchar retorna um int
tecla = getchar(); // guarda o caracter informado na variável
putchar(tecla);    // exibe o caracter informado
```

## Entrada formatada

### scanf

_em breve_
