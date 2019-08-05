Para cada exercício abaixo, crie um projeto no CodeBlocks com o nome indicado entre colchetes contendo um programa que execute a tarefa indicada.

---

`[Soma2Numeros]` Leia 2 números inteiros e exiba o resultado da soma:

```
Cálculo da soma entre dois números.

Digite o primeiro número: 30
Digite o segundo número: 40

Soma: 70
```

`[Medidas]` Receba uma medida em metros e exiba seus equivalentes em quilômetros e centímetros.

```
Entre com a medida (em metros): 150

--- Equivalência ---
15000 cm
150 m
0,15 Km
```

`[GrausCF]` Converta uma temperatura em °C para °F.

°F = °C × 1,8 + 32

Ref.: https://pt.wikipedia.org/wiki/Celsius

```
°C = 0
0°C equivalem a 32°F
```

`[GrausFC]` Converta uma temperatura em °F para °C.

°C = (°F − 32) / 1,8

Ref.: https://pt.wikipedia.org/wiki/Celsius

```
°C = 0
0°C equivalem a 32°F
```

`[MediaAritmetica]` Calcule a média aritmética entre 3 números reais digitados pelo usuário.

```
Média Aritmética de 3 números

Digite o primeiro número: 7.
Digite o segundo número: 9.
Digite o terceiro número: 5.

Média: 7.0
```

`[SisNums]` Receba um número inteiro, digitado em notação decimal. Exiba sua representação em octal e em hexadecimal.

```
Digite um número inteiro em base 10: 12

Decimal: 12
Octal: 014
Hexadecimal: 0xC
```

`[VelocMedia]` Calcule a velocidade, a partir da distância (Δd, em metros) e do tempo (Δt, em segundos).

v = Δd / Δt

```
Distância percorrida (m): 100
Tempo gasto (s): 15

Velocidade média: 6 m/s
```

`[IMC]` Calcule o índice de massa corporal de uma pessoa, dados altura (em m) e peso (em kg).

IMC = peso / altura²

```
Altura (m)..: 2.
Peso (kg)...: 80

IMC: 20,0 kg/m²
```

`[Projetil]` Um projétil é lançado em um ângulo `θ°` (teta graus) a uma velocidade inicial `v0 m/s`. Calcule, em metros, o alcance máximo `xmax` e a altura máxima atingida `hmax`.

Para isso, precisamos:

1. Da constante `π` (pi) = 3,14159 radianos
1. Da constante `g` = 9,80665 m/s²
1. Converter o ângulo de graus para radianos, como no exemplo: 180° × π/180 = 3rad
1. Aplicar a Equação de Torricelli para o alcance, e
1. Aplicar a equação de Torricelli para a altura.

![](https://github.com/ermogenes/aulas-logica-programacao/raw/master/exercises/lancamento_obliquo.png)

Exemplo:


```c
-- Projétil --

Entre com a velocidade, em m/s..: 30
Entre com o ângulo, em graus....: 30

Alcance........: 79,48 m
Altura máxima..: 11,47 m
```

Ref.: https://alunosonline.uol.com.br/fisica/lancamento-obliquo.html
