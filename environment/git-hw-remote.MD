# git e GitHub

## Instalando o git

* Baixe e instale o [Git para Windows](https://git-scm.com/download/win).
* Para testar se a instalação está correta, abra o Prompt de Comando e execute `git --version`. Será exibida a versão do git instalada.

```
C:\Users\ermogenes\> git --version
git version 2.16.2.windows.1

C:\Users\ermogenes\> 
```

## Criando uma conta no GitHub

* Crie um perfil em https://github.com/. Guarde bem o e-mail, o nome de usuário e a senha.
* Efetue o login.

## Configurando o seu usuário no git local

Execute os comando abaixo com seu nome e e-mail (utilizado no GitHub):

```
git config --global user.name "Seu Nome"
git config --global user.email seuemail@example.com
```

![](git-config.png)

Para testar se deu certo, digite:

```
git config user.name
```

_Obs.: Pode ser necessário executar esse passo sempre que utilizar um computador da Etec._

## Criando um novo repositório no GitHub

* Estando logado, acesse a opção `New Repository`:

![](git-new-repository.png)

* Configure o nome do repositório (ex.: `hello-world-github-c`), sua descrição e ative a criação do arquivo `README`.

![](git-new-repository-options.png)

* Ao final, será exibida a página inicial do seu repositório.

![](git-new-repository-inicial.png)

## Editando arquivos diretamente no GitHub

