# Constantes literais

São valores explicitamente escritos em um código. Todo literal possui um tipo de dado associado, seja implicitamente indicado, ou inferido pelo compilador.

## Inteiros

Representa um número inteiro. É escrito em decimal (base 10).

Número em base 10 | Literal
--- | ---
12 | `12` 

Também é possível escrever literais utilizando outras bases numéricas.

Base | Literal | Observação
--- | --- | ---
10 (decimal) | `12` |
8 (octal) | `014` | Iniciar em `0`.
16 (hexadecimal) | `0xC` | Iniciar em `0x` ou `0X`; dígitos `A` a `F` podem ser maiúsculos ou minúsculos.

Todos os literais acima representam o número inteiro 12.

Existem vários tipos de dados que permitem armazenar números inteiros. O compilador decidirá o tipo a ser utilizado.

Pode-se utilizar os operadores unários `-` e `+` para indicar o sinal, como em `-3` (três negativo).

## Caracteres

Representa um caracter simples, como `A`, `5`, ` ` (_espaço em branco_), ou `?`. É escrito entre aspas simples (`'`) e armazenado como um número inteiro, conforme a [Tabela ASCII](https://pt.wikipedia.org/wiki/ASCII).

Literal | Valor ASCII | Símbolo | Observação
--- | --- | --- | ---
`'A'` | 65 | A | letra A maiúscula
`'a'` | 97 | a | letra A minúscula
`'5'` | 53 | 5 | dígito 5
`' '` | 32 | ` ` | espaço em branco
`'?'` | 63 | ? | sinal de interrogação
`'\n'` | 10 | (_não imprimível_) | quebra de linha (`\n`)

### Sequências de escape

Podemos indicar alguns caracteres não imprimíveis utilizando as sequências de escape, iniciadas em `\`. Exemplos:

Escape | Significado
--- | ---
`\n` | Quebra de linha
`\t` | Tabulação 
`\\` | Barra invertida (\\)
`\'` | Aspas simples
`\"` | Aspas duplas

Referência completa [aqui](https://www.gnu.org/software/gnu-c-manual/gnu-c-manual.html#Character-Constants).

## Números reais

São armazenados utilizando [pontos flutuantes](https://www.mentebinaria.com.br/forums/topic/507-cuidado-com-a-aritm%C3%A9tica-de-ponto-flutuante/). Permite armazenar números com parte interia e parte fracionária, como por exemplo, o número 1/2 (um meio, 0,5).

Utilizam o sinal `.` para separar a parte inteira da fracional.

Literal | Valor
--- | ---
`15.7` | 15,7 (quinze inteiros e 7 décimos)
`0.5` | 0,5 (um meio)
`.5` | 0,5 (um meio)
`4.` | 4,0 (quatro)
`0.0` | 0 (zero)
`0.` | 0 (zero)
`.0` | 0 (zero)

Para números negativos, utilizar o operador unário `-`. Por exemplo, `-5.3` é avaliado como o número negativo -5,3.

### Notação científica

Utiliza-se o símbolo de exponenciação `e` (ou `E`) para indicar um número em [notação científica](https://pt.wikipedia.org/wiki/Nota%C3%A7%C3%A3o_cient%C3%ADfica).

Literal | Notação científica | Valor | Literal equivalente
--- | --- | --- | ---
`5e4` | 5 x 10^4 | 50.000,0 (cinquenta mil) | `50000`
`2e-3` | 2 x 10^-3 | 0,002 (dois milésimos) | `.002`

## Strings

Uma string representa um texto. É uma sequência de literais de caracter, terminada pelo caracter `\0`. Exemplo:

A string `"Etec"` é armazenada em memória desta maneira:

Caracteres | `'E'` | `'t'` | `'e'` | `'c'` | `'\0'`
--- | --- | --- | --- | --- | ---
**ASCII** | 69 | 116 | 101 | 99 | 0

Uma string pode ser escrita de diversas maneiras:

- Uma string simples:
`"Etec Adolpho Berezin"`

- Uma sequência de strings será concatenada pelo compilador (note os caracteres ` `):
`"Etec" " Adolpho " "Berezin"`

- Um texto com várias linhas:
`"Linha 1\nLinha2\n\nLinha4"`

- Para incluir aspas no texto, use sequência de escape:
`"Textos entre \'aspas simples\' e entre \"aspas duplas\"."`

- Uma string longa, escrita em várias linhas:
```c
"Minha terra tem palmeiras, \
Onde canta o Sabiá; \
As aves, que aqui gorjeiam, \
Não gorjeiam como lá."
```

- Strings em várias linhas também são concatenadas:
```c
"\"Ora (direis) ouvir estrelas! Certo"
"\nPerdeste o senso!\" E eu vos direi, no entanto,"
"\nQue, para ouvi-las, muita vez desperto"
"\nE abro as janelas, pálido de espanto..."
```
