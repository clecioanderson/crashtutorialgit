# crashtutorialgit
##### Table of Contents
* [Níveis de configuração do Git](#níveis-de-configuração-do-git)
    * [A nível de sistema operacional](#a-nível-de-sistema-operacional)
    * [A nível de usuário](#a-nível-de-usuário)
    * [A nível de projeto](#nível-de-projeto)
    * [Configurações a nível de sistema operacional](#configurações-a-nível-de-sistema-operacional)
    * [Configurações a nível de usuário](#configurações-a-nível-de-usuário)
    * [Configurações a nível de repositório](#configurações-a-nível-de-repositório)
* [Listar configurações](#listar-configurações)
* [Autenticação em repositórios remotos](#autenticação-em-repositórios-remotos)
* [Informações de contato](#informações-de-contato)
* [Editor Padrão](#editor-padrão)
* [Ativar o uso de cores para diferenciar texto](#ativar-o-uso-de-cores-para-diferenciar-texto)
* [Consultar ajuda dos comandos](#consultar-ajuda-dos-comandos)
* [Operações do dia-dia](#operações-do-dia-dia)
    * [Criar/Inicializar um novo repositório](#criar/inicializar-um-novo-repositório)
    * [Modificando arquivos](#modificando-arquivos)
	    * [git add](#git-add)
	    * [git commit](#git-commit)

## Níveis de configuração do Git
É importante lembrar que o git permite configurações em 3 níveis diferentes. É possível armazenar configurações **a nível de sistema operacional**, **a nível de usuário** ou **a nível de repositório de trabalho.**

A nível de conhecimento, segue abaixo as localizações dos arquivos em cada caso:

#### A nível de sistema operacional:
Você poderá encontrar na pasta de instalação global do git um arquivo chamado **gitconfig**

`/etc/gitconfig`

#### A nível de usuário:
Você poderá encontrar na pasta do usuário um arquivo chamado **gitconfig**

`~/.gitconfig`
`$HOME/.gitconfig`

#### A nível de projeto:
Você poderá encontrar na pasta do projeto um arquivo chamado **gitconfig**

`my_project/.git/config`

#### Configurações a nível de sistema operacional
A nível de sistema poderá usar o comando:

`git config --system [options] [values]`

#### Configurações a nível de usuário
A nível de usuário poderá usar o comando:

`git config --global [options] [values]`

#### Configurações a nível de repositório
A nível de repositório poderá usar o comando:

`git config [options] [values]`

A nível de repositório poderá usar o comando:

`git config [options] [values]`

## Listar configurações
Para listar todas as configurações padrão e outras já configuradas **a nível de usuário** poderá executar o comando abaixo

`git config --list`

Para listar uma configuração específica **a nível de usuário** poderá executar o comando abaixo. No exemplo abaixo estou consultando a opção **user.name**

`git config user.name`

## Autenticação em repositórios remotos
Ao tentar realizar o primeiro push num novo repositório remoto, não é solicitado usuário e senha para push via HTTP, resultando em erro de autenticação. 

**O que fazer?**

1. Edite o arquivo .git/config do repositório de trabalho
2. Adicione a opção abaixo:

```yaml
[credential]
        helper =
```

3. Salve o arquivo e tente realizar o push novamente

## Informações de contato
Editar o nome/autor dos commits *no nível de usuário*

`git config --global user.name "John Doe"`

Editar o email de contato do auto dos commits *no nível de usuário*

`git config --global user.email "john@mycompany.me"`

## Editor Padrão
Configurar o editor padrão para git a *nível de usuário*. No exemplo abaixo estou ajustando o *TextMate* como meu editor padrão.

`git config --global core.editor "mate -wl1"`

## Ativar o uso de cores para diferenciar texto
Definir o uso de cores no git a *nível de usuário*. Perceba que nesse caso o valor para o parâmetro, ou seja, *true* **não** veio entre **aspas duplas**.

`git config --global color.ui true`

## Consultar ajuda dos comandos
Para consultar a qualquer momento a ajuda dos comandos do git execute a linha de comando **git help [opção]**. Veja um exemplo abaixo que trará a ajuda para o comando **git log**.

`git help log`

## Operações do dia-dia
#### Criar/Inicializar um novo repositório
Sempre que começar um novo trabalho, provavelmente, se deparará com essa necessidade. De modo simples, precisará seguir os passos que a seguir:

- Crie um diretório
- Acesse esse diretório
- Inicialize/adicione ele ao git localmente

Num sistema linux, você poderia realizar esses passos da seguinte forma:

`mkdir newwork`
`cd newwork`
`git init`

Com esses passos agora você possui um repositório local versionado, onde todas as alterações realizadas poderão ser rastreadas ou até mesmo revertidas se necessário. 

Uma vez inicializado o repositório conforme mostrado, você encontrará um diretório oculto .git contendo todas as informações de rastreio das modificações desse novo projeto. **LEMBRE-SE: SE VOCÊ REMOVER ESSE DIRETÓRIO, SEU PROJETO NÃO SERÁ MAIS RASTREÁVEL PELO GIT.**

#### Modificando arquivos
Para rastrear alterações a partir de agora vamos criar um arquivo de teste.

- Criar um arquivo
- Adicioná-lo ao git **{git add}**
- Tornar as alterações permanentes no repositório **{git commit}**

Para simular essas tarefas num sistema linux, você poderá executar os comandos abaixo. Vamos levar em conta o repositório criado anteriormente:

`cd newwork`
`echo "teste" > teste`
`git add .`
`git commit -m "Commit Inicial"`

###### git add

Para saber mais detalhes sobre esse comando, utilize a ajuda do git. **Ex.: git help add**

Esse comando é utilizado para adicionar a última alteração para o git, para torná-la rastreável
###### git commit

Para saber mais detalhes sobre esse comando, utilize a ajuda do git. **Ex.: git help commit**

Esse comando é utilizado para tornar permanente uma alteração adicionada ao rastreio do repositório git. É necessário adicionar um comentário que vai ajudar a identificar o motivo daquela alteração sendo confirmada. **Ex. git commit -m "commit inicial"**.

É importante criar mensagens de commit significativas. Podemos pensar nelas como rótulos que indicam o que inclui aquela alteração ao repositório. Como boa prática, poderá criar uma linha inicial com um resumo da alteração e uma outra com a descrição detalhada, podemos usar a opção **-m** múltiplas vezes para criar uma mensagem de commit multilinha. Para isso execute o comando abaixo:

`git commit -m"bugfix: conserta erro informado no ticket 12345" -m"O ticket 12345 se refere ao problema de autenticação na página de login. Nesse commit foi atualizado o método de autenticação empregado no site para resolver esse bug."`

