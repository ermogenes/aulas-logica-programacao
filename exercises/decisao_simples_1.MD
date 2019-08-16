Para cada exercício abaixo, crie um projeto no CodeBlocks com o nome indicado entre colchetes contendo um programa que execute a tarefa indicada.

---

`[Negativo]` Leia um número inteiro e exiba a mensagem "Você digitou um número negativo." caso o número seja menor que zero.

`[Sinal]` Leia um número inteiro e exiba "Negativo", "Zero" ou "Positivo".

`[Divisao]` Receba um numerador e um denominador. Exiba o resultado da divisão ou "Não é possível dividir por zero.", conforme o caso.

`[Media4Notas]` Receba 4 notas, com somente uma casa decimal. Valide se todas estão entre 0.0 e 10.0. Se alguma delas não estiver, exiba "Digite somente notas entre 0 e 10.". Caso todas as notas sejam válidas, calcule a média aritmética das notas. Exiba uma mensagem no seguinte padrão: "Você ficou com média 7,5. Resultado: Aprovado".

Resultados possíveis:

- "Reprovado" para médias menores que 5.0
- "Em recuperação" para médias entre 5.0 e 6.0
- "Aprovado", para médias acima de 6.0

`[IMC]` Calcule o Índice de Massa Corporal ([IMC](https://pt.wikipedia.org/wiki/%C3%8Dndice_de_massa_corporal)) do usuário.

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/4db320ff2cde68cebea226fb921247d7ebbfad33)

Exemplo:

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/087509d243f6d39cd81ee54daad23ca7c8990d8c)

Exiba a situação, conforme tabela.

Resultado | Situação
--- | ---
Abaixo de 17 | Muito abaixo do peso
Entre 17 e 18,49 | Abaixo do peso
Entre 18,5 e 24,99 | Peso normal
Entre 25 e 29,99 | Acima do peso
Entre 30 e 34,99 | Obesidade I
Entre 35 e 39,99 | Obesidade II (severa)
Acima de 40 | Obesidade III (mórbida)

`[Maior2Numeros]` Receba dois números. Exiba o maior.

`[Senha]` Solicite ao usuário que digite a sua senha (número inteiro). Exiba "Acesso permitido" caso a senha digitada seja `1234`, senão exiba "Acesso negado".

`[DoadorSangue]` Solicite a idade do usuário. Avalie se ele pode ser doador de sangue (i.e. possui idade entre 18 e 67 anos). Informe o resultado da avaliação.

`[ParImpar]` Receba um número. Exiba "par" ou "ímpar", conforme o caso.

_Dica: um número é ímpar caso possua resto ao ser dividido por 2._

`[PesoIdeal]` Solicite que o usuário digite sua altura e o seu sexo (1 para masculino, 2 para feminino). Calcule e exiba seu peso ideal.

- Para homens, altura x 72.7 - 58.0
- Para mulheres, altura x 62.1 - 44.7

`[AnaliseCredito]` Um cliente quer solicitar um empréstimo. Receba o valor solicitado, a quantidade de parcelas desejada e a renda mensal comprovada. Só autorize empréstimos cuja parcela não ultrapasse 30% da renda (desconsidere os juros).

`[Heron]` Receba três números decimais maiores que zero. Valide se estes números correspondem aos lados de um triângulo (a). Exiba o tipo do triângulo (b). Exiba a sua área (c).

a. Condição de existência de um triângulo:

Para que se possa construir um triângulo é necessário que a medida de qualquer um dos lados seja menor que a soma das medidas dos outros dois e maior que o valor absoluto da diferença entre essas medidas.

Ou seja, todas as condições abaixo devem ser atendidas:

- `a < (b + c)`
- `a > fabs(b - c)`
- `b < (a + c)`
- `b > fabs(a - c)`
- `c < (a + b)`
- `c > fabs(a - b)`

b. Tipo do triângulo:

- Equilátero: três lado com medidas iguais;
- Escaleno: três lados com medidas diferentes;
- Isósceles: demais triângulos.

c. Área do triângulo pelo Teorema de Heron:

![](https://wikimedia.org/api/rest_v1/media/math/render/svg/e66e19b74d5ba900c820c2d99de7f62c0513d916)
![](https://wikimedia.org/api/rest_v1/media/math/render/svg/da3d1cfce6b872d360b302f80de119cb9ef5c210)

Ref.: https://pt.wikipedia.org/wiki/Tri%C3%A2ngulo
