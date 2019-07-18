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

- Interpolação de um argumento `int` com o especificador `%d`:
```c
printf("João tem %d anos de idade.", 42);

/* saída:
João tem 42 anos de idade.
*/
```

- Interpolação de dois argumento, `int` e um `double`:
```c
printf("João tem %d anos de idade e ganhou R$%f na loteria.", 42, 100000.);

/* saída:
João tem 42 anos de idade e ganhou R$100000,000000 na loteria.
*/
```

- Usando opções de formatação nos especificadores:

```c
printf("João tem %d anos de idade e ganhou R$%.2f na loteria.", 42, 100000.);

/* saída:
João tem 42 anos de idade e ganhou R$100000,00 na loteria.
*/
```

#### Especificadores de formato para `printf`

Uma lista de especificadores comuns ([lista completa](http://www.cplusplus.com/reference/cstdio/printf/)).

- Números

Especificador | Saída | Exemplo
--- | --- | ---
`%d` | número inteiro com sinal | `printf("%d", -5);` exibe `-5`
`%u` | número inteiro sem sinal | `printf("%u", 2);` exibe `2`
`%f` | número fracionário | `printf("%f", .1);` exibe `0.100000`
`%e` | número fracionário em notação científica | `printf("%e", .000005);` exibe `5.000000e-006`
`%g` | opção mais curta entre `%f` e `%e` | `printf("%g", 500000000.);` exibe `5e+008`

- Definindo precisão em números fracionários

Especificador | Saída | Exemplo
--- | --- | ---
`%.3f` | três casas decimais | `printf("%.3f", 2.1);` exibe `2.100`
`%5.1f` | cinco espaços, com uma casa decimal (espaços em branco à esquerda)| `printf("%5.1f", 2.1);` exibe `  2.1`
`%05.1f` | cinco espaços, com uma casa decimal (zeros à esquerda)| `printf("%5.1f", 2.1);` exibe `002.1`

- Texto

Especificador | Saída | Exemplo
--- | --- | ---
`%c` | Um caracter | `printf("%c", 65);` exibe `A`
`%s` | Uma string de caracteres | `printf("Meu nome é %s.", "Ermogenes");` exibe `Meu nome é Ermogenes.`

- Outros sistemas numéricos

Especificador | Saída | Exemplo
--- | --- | ---
`%o` | octal (sem sinal) | `printf("%o", 92);` exibe `134`
`%x` | hexadecimal (sem sinal) | `printf("%x", 92);` exibe `5c`

- Especiais

Especificador | Saída | Exemplo
--- | --- | ---
`%%` | Exibe % | `printf("100%% Linguagem C");` exibe `100% Linguagem C`
`%p` | Endereço de memória (ponteiro) | `char v1,v2; printf("v1 está em %p, e v2 está em %p", &v1, &v2);` exibe `v1 está em 0060FEFF, e v2 está em 0060FEFE` (pode variar a cada execução)
 

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

Lê uma entrada formatada em um endereço de memória. O armazenamento é feito no formato dado pelo especificador.

É a principal maneira de se entrar com valores em C.

Sintaxe:
```c
scanf( formato , endereco_de_memoria )
```

Os exemplos da tabela abaixo consideram a existência destas variáveis:

```c
int numero;
unsigned int numero_positivo;
char letra;
float valor;
char texto [100];
```

Especificador | Entrada | Exemplo
--- | --- | ---
`%d` | dígitos, precedidos ou não por sinal | `scanf("%d", &numero);`
`%u` | dígitos | `scanf("%u", &numero_positivo);`
`%f` | dígitos, precedidos ou não por sinal, opcionalmente com ponto decimal | `scanf("%f", &valor);`
`%c` | Um caracter | `scanf("%c", &letra);`
`%s` | Uma string de caracteres, terminada por espaço | `scanf("%s", texto);` (_perceba que não usamos `&`_)

Perceba que as entradas `%f` respeitam a configuração de local, usando `.` ou `,` como separador de decimal, conforme configuração.

Opções importantes:

Especificador | Entrada | Exemplo
--- | --- | ---
`%10s` | Uma string de até 10 caracteres  | `scanf("%10s", texto);`
`%[^\n]` | Uma string de caracteres, terminada por quebra de linha | `scanf("%[^\n]", texto);`

Todos os caracteres não lidos continuam no buffer, para a próxima leitura. _Preste atenção nisso, caso ache que o comportamento está estranho!_ Um espaço em branco antes do especificador ignora espaços e quebras de linha preexistentes no buffer.

Um exemplo completo:
```c
char nome_completo [50];
int idade;
float salario;

printf("Entre com os seus dados:\n\n");

printf("Nome: ");
scanf(" %[^\n]", nome_completo);

printf("Idade: ");
scanf(" %d", &idade);

printf("Salario: ");
scanf(" %f", &salario);

printf("\nValores digitados:\n");

printf("\nNome = %s", nome_completo);
printf("\nIdade = %d anos", idade);
printf("\nSalario = R$ %.2f", salario);
```

Saída:

```c
Entre com os seus dados:

Nome: Jair Messias Bolsonaro
Idade: 64
Salario: 30934.7

Valores digitados:

Nome = Jair Messias Bolsonaro
Idade = 64 anos
Salario = R$ 30934.70
```

([Lista completa](http://www.cplusplus.com/reference/cstdio/scanf/))
