# Princiáis comandos Git no termnial:

## Ajuda:
**Geral** 
git help
**Ajuda para comando específico**

git help add
git help commit
git help <qualquer_comando_git>

## Configuração:

### Geral

As configurações do GIT são armazenadas no arquivo .gitconfig localizado dentro do diretório do usuário do Sistema Operacional (Ex.: Windows: C:\Users\Documents and Settings\Leandro ou *nix /home/leandro).

As configurações realizadas através dos comandos abaixo serão incluídas no arquivo citado acima.

**Setar usuário**

git config --global user.name "LeandroSouza"

**Setar email**

git config -- global user.email leandrosouza@gmail.com

**Setar editor**

git config --global core.editor vim

**Setar ferramenta merge**

git config --global core.excludesfile ~/.gitignore

**LIstar configurações**

git config --list

### Ignorar Arquivos

Os nomes de arquivos/diretórios ou extensões de arquivos listados no arquivo .gitignore não serão adicionados em um repositório. Existem dois arquivos .gitignore, são eles:

+ Geral: Normalmente armazenado no diretório do usuário do Sistema Operacional. O arquivo que possui a lista dos arquivos/diretórios a serem ignorados por todos os repositórios deverá ser declarado conforme citado acima. O arquivo não precisa ter o nome de .gitignore.

+ Por repositório: Deve ser armazenado no diretório do repositório e deve conter a lista dos arquivos/diretórios que devem ser ignorados apenas para o repositório específico.

## Repositório Local

#### Criar novo repositório

git init

#### Verificar estado dos arquivos/diretórios

git status

#### Adicionas arquivos/diretório (Staged area)

**Adicionar um arquivo específico**

git add meu_arquivo.txt

**Adicionar um diretório específico**

git add meu_diretorio

**Adicionar todos os arquivos/diretórios**

git add .

**Adicionar um arquivo que esta listado no.gitgnore (geral ou do repositório)**

git add -f ArquivoNogitgnore.txt

#### Comitar arquivo/diretório

**Comitar um arquivo**

git commit meu_arquivo.txt

**Comitar vários arquivos**

git commit meu_arquivo.txt meu_outro_arquivo.txt

**Comitar Informando mensagem** 

git commit meuarquivo.txt -m "minha mensagem de commit"

* É uma boa prática sempre fazer o comit informando uma mensagem.

### Remover arquivo/diretório
**Remover arquivo**

git rm meu_arquivo.txt

**Remover diretório**

git rm -r diretorio

### Visualizar histórico

**Exibir histórico**

git log

**Exibir histórico com diff das duas últimas alterações**

git log -p -2

**Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))**

git log --stat

**Exibir informações resumidas em uma linha (hash completa e comentário)**

git log --pretty=oneline

**Exibir histórico com formatação específica (hash abreviada, autor, data e comentário)**
git log --pretty=format:"%h - %an, %ar : %s"

* %H: Commit hash
* %h: Abreviação do hash;
* %an: Nome do autor;
* %ar: Data;
* %s: Comentário.
Verifique as demais opções de formatação no [Git Book](http://git-scm.com/book/en/v2/Git-Basics-Viewing-the-Commit-History).

**Exibir histório de um arquivo específico**

git log -- <caminho_do_arquivo>

**Exibir histórico de um arquivo específico que contêm uma determinada palavra**

git log --summary -S<palavra> [<caminho_do_arquivo>]

**Exibir histórico modificação de um arquivo**

git log --diff-filter=M -- <caminho_do_arquivo>

* O pode ser substituido por: Adicionado (A), Copiado (C), Apagado (D), Modificado (M), Renomeado (R), entre outros.

**Exibir histório de um determinado autor**

git log --author=usuario

### Desfazendo operações
**Desfazendo alteração local (working directory)**

Este comando deve ser utilizando enquanto o arquivo não foi adicionado na staged area.

git checkout -- meu_arquivo.txt

**Desfazendo alteração local (staging area)**
Este comando deve ser utilizando quando o arquivo já foi adicionado na **staged area**.

git reset HEAD meu_arquivo.txt

Se o resultado abaixo for exibido, o comando reset não alterou o diretório de trabalho.

Unstaged changes after reset:
M	meu_arquivo.txt

A alteração do diretório pode ser realizada através do comando abaixo:

git checkout meu_arquivo.txt

## Repositório Remoto
### Exibir os repositórios remotos

git remote

git remote -v
 
### Vincular repositório local com um repositório remoto

git remote add origin git@github.com:leocomelli/curso-git.git

### Exibir informações dos repositórios remotos

git remote show origin

### Renomear um repositório remoto

git remote rename origin curso-git

### Desvincular um repositório remoto

git remote rm curso-git

### Enviar arquivos/diretórios para o repositório remoto

O primeiro **push** de um repositório deve conter o nome do repositório remoto e o branch.

git push -u origin master

Os demais **pushes** não precisam dessa informação

git push

### Atualizar repositório local de acordo com o repositório remoto

**Atualizar os arquivos no branch atual**

git pull

**Buscar as alterações, mas não aplica-las no branch atual**

git fetch

### Clonar um repositório remoto já existente

git clone git@github.com:leocomelli/curso-git.git

para outros comandos [clique aqui](https://gist.github.com/leocomelli/2545add34e4fec21ec16)








 

	


