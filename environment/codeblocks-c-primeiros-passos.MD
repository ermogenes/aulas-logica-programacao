# Criando o primeiro projeto em C no Code::Blocks

* Abrir o Code::Blocks:

![](codeblocks-instalado.png)

* Inicie um projeto novo, clicando em `File > New > Project...` e selecione o _template_ `Console Application` e a linguagem C:

![](codeblocks-novo-projeto-template.png)
![](codeblocks-novo-projeto-linguagem.png)

* Defina um nome para o projeto e o local de salvamento. Para este tutorial, usamos o nome `HelloWorld` e o local `C:\Users\ermogenes\Desktop\ProjetosCB\HelloWorld` (escolha a pasta de sua preferência).

![](codeblocks-novo-projeto-local.png)

* Escolha o compilador GNU GCC Compiler e mantenha a criação dos diretórios de Debug e Release com as opções padrão.

![](codeblocks-novo-projeto-compilacao.png)

* O projeto será criado com um programa de exemplo:

![](codeblocks-novo-projeto-criado.png)

* Estes são os arquivos criados até agora:
  - `HelloWorld.cbp`: configurações do projeto
  - `main.c`: arquivo de código-fonte principal do programa
  
![](codeblocks-novo-projeto-arquivos-iniciais.png)

* Criado o projeto, vamos compilá-lo executando o processo de Build:

![](codeblocks-hw-build.png)

* Serão criados diretórios com os arquivos-objeto (`obj`) e com os binários executáveis (`bin`), nas suas versões Debug.

![](codeblocks-hw-build-arquivos.png)

![](codeblocks-hw-build-objeto.png)

![](codeblocks-hw-build-executavel.png)

* Execute o programa:

![](codeblocks-hw-run.png)

* Pressione `ENTER` duas vezes para retornar à IDE.

# Melhorando o programa

* Modifique a mensagem exibida:

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Olá, mundo!\n");
    printf("Meu nome é Ermogenes.\n\n");
    printf("Este é o meu primeiro programa em C.\n");
    return 0;
}
```

* Compile e execute, utilizando o comando `Build and Run`:

![](codeblocks-hw-build-and-run.png)

* Perceba que os acentos e caracteres especiais utilizados pelo compilador não correspondem ao padrão do sistema operacional.

![](codeblocks-hw-erro-encoding.png)

* Faça as alterações abaixo para configurar corretamente o local:

![](codeblocks-hw-erro-encoding-ajuste.png)

...
```c
#include <locale.h>
```
...
```c
setlocale(LC_ALL,"portuguese");
```
...

* Ao compilar e executar novamente temos a versão correta.

![](codeblocks-hw-erro-encoding-ajustado.png)

* Salve seu projeto.

![](codeblocks-hw-salvar.png)

* Terminado. Pode fechar o Code:Blocks. Quando precisar abrir novamente, use a opção `File > Open...` e escolha o arquivo do projeto `.cbp`:

![](codeblocks-hw-abrir.png)
