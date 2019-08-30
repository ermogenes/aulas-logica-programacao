# Decisão múltipla

Testa uma expressão, comparando sequencialmente com diversas outras. Permite que se disponha múltiplos caminhos de execução, de acordo com o valor da primeira expressão.

Exemplo:

```
Menu de opções
--------------

N. Novo arquivo
A. Abrir arquivo
H. Ajuda
X. Sair

Digite a sua opção: _
```

Nesse caso, gostaríamos de avaliar o resultado da digitação entre 4 valores disjuntos (`'N'`, `'A'`, `'H'` e `'X'`).

## Comando `switch`

Implementa a decisão múltipla em C.

```c
switch (expressaoTeste)
{
    case expressaoCaso1:
        comandosCaso1Verdadeiro
        ...
        break;
    case expressaoCaso2:
        comandosCaso2Verdadeiro
        ...
        ...
        break;
    ...
    default:
        comandosTodosCasosFalsos
}
```

* `switch`: comando de decisão múltipla
* `expressaoTeste`: expressão inteira (`int`, `char`, etc.) a ser avaliada pelos testes
* `case`: um teste de igualdade em relação a `expressaoTeste`
* `expressaoCaso1` e `expressaoCaso2`: valores inteiros a serem testados contra `expressaoTeste`
* `comandosCaso1Verdadeiro` e `comandosCaso2Verdadeiro`: listas de comandos a serem executados caso seus testes avaliem como verdadeiro
* `break`: indica não deve mais executar comandos do bloco `switch`
* `default` (opcional): caso padrão, se nenhum dos casos anteriores for verdadeiro
* `comandosTodosCasosFalsos` (opcional): comandos a serem executados no caso padrão

Exemplo:

```c
   char opcaoUsuario = 0;

   printf("Menu de opções\n");
   printf("--------------\n\n");
   printf("N. Novo arquivo\n");
   printf("A. Abrir arquivo\n");
   printf("H. Ajuda\n");
   printf("X. Sair\n\n");

   printf("Digite a sua opção: ");
   scanf("%c", &opcaoUsuario);

   printf("\nOPÇÃO SELECIONADA: %c\n\n", opcaoUsuario);

   switch (opcaoUsuario)
   {
    case 'N':
        printf("Um arquivo novo será criado.\n");
        break;
    case 'A':
        printf("Um arquivo existente poderá ser aberto.\n");
        break;
    case 'H':
        printf("Uma tela de ajuda será exibida.\n");
        break;
    case 'X':
        printf("Obrigado por utilizar nosso software!\n");
        exit(EXIT_SUCCESS);
        break;
    default:
        printf("Opção inválida!\n");
        exit(EXIT_FAILURE);
        break;
   }
```

## Cuidados ao usar `switch`

* Os testes param de ser executados assim que o primeiro teste é avaliado como verdadeiro.
* Todos os comandos após o teste avaliado como verdadeiro serão executados até o final do bloco (`}`), ou até encontrar um `break`.

Exemplo de construção `switch` válida, mas (provavelmente) incorreta:

```c
int valor = 0;
switch (valor)
{
    case -3:
        printf("Menos três.\n");
        printf("Número negativo.\n");
    case 0:
        printf("Zero.\n");
    case 2:
        printf("Dois.\n");
        printf("Número par.\n");
        break;
    case 3:
        printf("Três.\n");
        printf("Número ímpar positivo.\n");
    default:
        printf("Nenhum dos anteriores.\n");
}
printf("Obrigado!");
```

Resultado:

```
Zero.
Dois.
Número par.
Obrigado!
```

Explicação:

* O programa testa `valor == -3`, que avalia como falso.
  * O programa segue para o próximo `case`.
* O programa testa `valor == 0`, que avalia como verdadeiro.
  * O programa executa todos os comandos (exceto outros `case`) até que termine o bloco `switch` ou encontre um `break`:
    * Exibe `"Zero.\n"`
    * Pula `case 2:`
    * Exibe `"Dois.\n"`
    * Exibe `"Número par.\n"`
    * Executa `break`, que encerra o bloco `switch`

Sendo assim, poderíamos corrigir este exemplo adicionando `break` após cada bloco de comandos:

```c
int valor = 0;

switch (valor)
{
    case -3:
        printf("Menos três.\n");
        printf("Número negativo.\n");
        break;
    case 0:
        printf("Zero.\n");
        break;
    case 2:
        printf("Dois.\n");
        printf("Número par.\n");
        break;
    case 3:
        printf("Três.\n");
        printf("Número ímpar positivo.\n");
        break;
    default:
        printf("Nenhum dos anteriores.\n");
}
printf("Obrigado!");
```

A saída fica:

```
Zero.
Obrigado!
```
