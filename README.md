# Primeiros passos com Git e Gitflow

## Git

O Git é um sistema de controle de versão distribuído amplamente usado na área de desenvolvimento de software. Ele permite que você rastreie e gerencie alterações em arquivos, crie ramificações para desenvolver recursos independentes e mescle essas mudanças de forma eficiente. É uma ferramenta fundamental para o desenvolvimento colaborativo, ajudando a manter o código organizado e permitindo o trabalho em equipe de maneira eficaz.

## Gitflow

Gitflow é um modelo de fluxo de trabalho que busca simplificar e organizar o versionamento de ramificações de um projeto de desenvolvimento no Git.

**Main:** é a ramificação principal que contém o código-fonte em produção. Não é permitido realizar alterações (commit) diretamente nessa ramificação. A Master ainda é utilizada para enviar os commits dos releases para a produção;

**Develop:** criada a partir da ramificação Main, ela reúne os códigos de todos os ramos e se comunica com a Main. Ela contém o código-fonte mais atual e todas as novas features estáveis que serão mescladas posteriormente;

**Feature:** criada a partir da ramificação Develop, é uma branch temporária que carrega uma nova funcionalidade para o projeto, ela sempre acabará sendo mesclada à própria Develop através de merge. E segue um padrão de nomenclatura “feature/new-feature”.

**Release:** é uma ramificação temporária que fará com que os novos recursos armazenados na Develop sejam mesclados na branch Master, recebendo uma tag que indica a nova versão do projeto.

**Hotfix:** é uma ramificação utilizada para mesclar correções na ramificação principal decorrente de bugs identificados no processo de desenvolvimento. Após a correção do bug, o código irá tanto para a branch main como para a Develop. Essa branch também recebe uma tag indicando a nova versão na Main.


## Criando um Repositorio



## Clonando um Repositório

O comando git clone é usado para criar uma cópia local de um repositório Git existente.

Encontrar o Repositório: Primeiro, você precisa identificar o URL do repositório Git que deseja clonar.

Executar o Comando Clone: O comando git clone é usado para criar uma cópia local do repositório remoto. A sintaxe básica é a seguinte:

> git clone <URL_do_repositório>

Por exemplo, para clonar um repositório chamado "meu-projeto" do GitHub, você usaria:

> git clone https://github.com/seu-usuario/meu-projeto.git

**Criação da Cópia Local**: O Git irá baixar todos os arquivos e histórico de commits do repositório remoto e criar uma cópia completa na sua máquina local. Agora, você tem todos os arquivos do projeto em seu ambiente.

**Contribuição no Desenvolvimento**: Com o repositório clonado, você pode fazer modificações nos arquivos, criar novos arquivos e adicionar funcionalidades. Quando você faz essas alterações, o Git monitora as diferenças entre a cópia local e o estado anterior. Use os comandos git add, git commit e git push para adicionar, confirmar e enviar suas alterações de volta para o repositório remoto.

**Testes Locais**: Além de contribuir para o desenvolvimento, você também pode usar a cópia local do repositório para realizar testes em um ambiente controlado. Isso é útil para verificar como suas mudanças afetam o projeto antes de compartil

## Branchs

![branch-feature](./img/image.png)


## Commits



## Comandos Básicos

### Git init
Inicializa um repositório Git dentro de um diretório do sistema.

> git init

### Git clone
Cria uma cópia de um repositório remoto em um diretório da máquina.

> git clone *(https://github.com/(userGitHub)/(repositoryName).git)*

### Git status
Verifica o status do git atualmente. Esse comando mostra se o projeto local está sincronizado com o master, quais arquivos estão sendo monitorados pelo Git e em qual branch você está. 

> git status

### Git add
Adiciona arquivos ao pacote de alterações para serem feitas. É possível adicionar um arquivo ou múltiplos arquivos por vez.

> git add <-arquivo1->

**Observação:** Adiciona somente o arquivo 1 para o pacote.

> git add . 

**Observação:** Adiciona todos os arquivos modificados ao pacote.

### Git commit
Etapa crucial para registrar uma nova versão do projeto, composta por um conjunto de alterações. Ele pega as modificações que foram adicionadas usando o comando git add, agrupa essas mudanças em um conjunto e as identifica com um código único chamado Hashcode. Além disso, em cada commit, é necessário incluir uma mensagem descritiva que esclareça quais foram as alterações feitas nessa atualização. Isso torna mais fácil entender o propósito e o conteúdo de cada commit no histórico do projeto.

> git commit -m "Adicionando cards"

### Git branch
Cria novas branches de desenvolvimento, bem como visualiza quais são os ramos existentes. 

> git branch

> git branch feature/cards

> git checkout: navegar entre as branchs do projeto. 

> git checkout feature/cards

### Git remote add "origin https://github.com/seu-usuario/meu-projeto.git
É usado para adicionar um repositório remoto ao seu repositório local no Git. Você fornece um nome para o repositório remoto (geralmente "origin" por convenção) e a URL do repositório remoto. Isso permite que você envie e receba alterações entre seu repositório local e o repositório remoto.

> git remote add origin (url do repositorio github)

### Git fetch:
É usado para baixar as atualizações de um repositório remoto para o seu repositório local no Git.

> git fetch nome-do-repositorio

### Git push:
Enviar as alterações do seu repositório local para um repositório remoto no Git. Isso atualiza o repositório remoto com as mudanças que você fez localmente, permitindo que outros colaboradores acessem essas alterações e as incorporem ao projeto. Geralmente, você especifica a branch local que deseja enviar e a branch correspondente no repositório remoto.

> git push origin nome-da-sua-branch-local

### Git pull:
Usado para atualizar o seu repositório local com as alterações do repositório remoto no Git. Ele combina automaticamente as alterações da branch remota para a branch local em que você está trabalhando, trazendo as últimas atualizações do projeto para o seu ambiente de desenvolvimento. Geralmente, é usado após um "git fetch" para trazer essas mudanças para o seu repositório local.

> git pull origin main

### Git merge:
É usado para combinar as alterações de uma branch para outra no Git. Geralmente, você usa "git merge" para integrar as alterações de uma branch secundária (por exemplo, uma funcionalidade ou correção de bug) na branch principal (geralmente a "master" ou "main"). Isso cria um novo commit que representa a fusão das alterações, unindo as duas linhas de desenvolvimento.

> git checkout main
> git merge feature/nova-funcionalidade

**Observação:** Mesclar uma branch secundária em uma branch principal
