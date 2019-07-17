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

### `printf`

Exibe uma string formatada. Permite a composição de uma string a partir de uma string base contendo especificadores que serão substituídos por um igual número de argumentos.

É a principal maneira de se exibir valores em C.

Sintaxe:
```c
printf( string_base , argumentos... )
```

Exemplos:

- Somente caracteres:
```c
printf("The GNU C Library");

/* saída:
The GNU C Library
*/
```

- Usando sequências de escape:
```c
printf("GNU é uma sigla para\n\'GNU is not Unix\'.");

/* saída:
GNU é uma sigla para
'GNU is not Unix'.
*/
```

- Interpolação de argumentos em especificadores: (_em breve_)
```c
```

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

### `scanf`

_em breve_
