# crashtutorialgit

## Opções de configuração do Git

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

#### Comandos a nível de sistema operacional

A nível de sistema poderá usar o comando:

`git config --system [options] [values]`

#### Comandos a nível de usuário

A nível de usuário poderá usar o comando:

`git config --global [options] [values]`

#### Comandos a nível de repositório

A nível de repositório poderá usar o comando:

`git config [options] [values]`

A nível de repositório poderá usar o comando:

`git config [options] [values]`

### Listar configurações

Para listar todas as configurações padrão e outras já configuradas **a nível de usuário** poderá executar o comando abaixo

`git config --list`

Para listar uma configuração específica **a nível de usuário** poderá executar o comando abaixo. No exemplo abaixo estou consultando a opção **user.name**

`git config user.name`

### Autenticação em repositórios remotos

Ao tentar realizar o primeiro push num novo repositório remoto, não é solicitado usuário e senha para push via HTTP, resultando em erro de autenticação. 

**O que fazer?**

1. Edite o arquivo .git/config do repositório de trabalho
2. Adicione a opção abaixo:
```yaml
[credential]
        helper =
```
3. Salve o arquivo e tente realizar o push novamente

### Informações de contato

Editar o nome/autor dos commits *no nível de usuário*

`git config --global user.name "John Doe"`

Editar o email de contato do auto dos commits *no nível de usuário*

`git config --global user.email "john@mycompany.me"`

### Editor Padrão

Configurar o editor padrão para git a *nível de usuário*. No exemplo abaixo estou ajustando o *TextMate* como meu editor padrão.

`git config --global core.editor "mate -wl1"`

### Ativar o uso de cores para diferenciar texto

Definir o uso de cores no git a *nível de usuário*. Perceba que nesse caso o valor **não** veio entre **aspas duplas**.

`git config --global color.ui true`
