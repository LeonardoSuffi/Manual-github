# Manual Github do Professor Rold
Este manual foi criado para auxiliar os alunos e profissionais a entender e utilizar o Git eficientemente. Aqui, você encontrará instruções detalhadas sobre a instalação, configuração e uso do Git em diferentes sistemas operacionais, além de práticas recomendadas para gerenciamento de repositórios, branches, commits e muito mais.

# Índice

## 1. [Instalação do Git](#1-instalação-do-git)
   - [Para Windows](#para-windows)
   - [Para macOS](#para-macos)
   - [Para Linux](#para-linux)
   - [Configuração inicial do Git](#configuração-inicial-do-git)
   - [Definindo o editor padrão](#definindo-o-editor-padrão)

## 2. [Repositórios Git: Local e Remoto](#2-repositórios-git-local-e-remoto)
   - [Inicialização de um Novo Repositório](#inicialização-de-um-novo-repositório)
   - [Clonagem de um Repositório Existente](#clonagem-de-um-repositório-existente)
   - [Diferença Entre Repositórios Locais e Remotos](#diferença-entre-repositórios-locais-e-remotos)

## 3. [Trabalhando com Múltiplos Branches](#3-trabalhando-com-múltiplos-branches)
   - [Criação e Gerenciamento de Branches](#criação-e-gerenciamento-de-branches)
   - [Navegação entre Branches](#navegação-entre-branches)

## 4. [Integração com IDEs](#4-integração-com-ides)
   - [VSCode](#vscode)
   - [Eclipse](#eclipse)
   - [Android Studio](#android-studio)

## 5. [Estratégias de Branching](#5-estratégias-de-branching)
   - [Estratégia de Manutenção e Produção Separadas](#estratégia-de-manutenção-e-produção-separadas)
   - [Branches de Feature: Gerenciamento e Melhores Práticas](#branches-de-feature-gerenciamento-e-melhores-práticas)

## 6. [Commits e Gerenciamento de Versão](#6-commits-e-gerenciamento-de-versão)
   - [Realização de Commits Intermediários em Desenvolvimento](#realização-de-commits-intermediários-em-desenvolvimento)
   - [Estratégias para Commits Limpos e Eficazes](#estratégias-para-commits-limpos-e-eficazes)
   - [Tagging para Marcar Lançamentos de Versões](#tagging-para-marcar-lançamentos-de-versões)

## 7. [Fluxo de Trabalho Avançado](#7-fluxo-de-trabalho-avançado)
   - [BACKLOG](#backlog)
   - [CHANGELOG](#changelog)
   - [Versionamento Semântico (SemVer)](#versionamento-semântico-semver)

## 8. [Resolução de Conflitos](#8-resolução-de-conflitos)
   - [Técnicas para Resolução de Conflitos](#técnicas-para-resolução-de-conflitos)
   - [Ferramentas para Resolução de Conflitos](#ferramentas-para-resolução-de-conflitos)

## 9. [Estudos de Caso e Melhores Práticas](#9-estudos-de-caso-e-melhores-práticas)
   - [Exemplos Reais de Utilização do Git](#exemplos-reais-de-utilização-do-git)
   - [Dicas para Manter a Integridade do Repositório](#dicas-para-manter-a-integridade-do-repositório)


## 1. Instalação do Git
### Para Windows:

1. Baixe o instalador do Git em git-scm.com.
2. Execute o arquivo baixado e siga as instruções de instalação. Recomendo deixar as opções padrão, especialmente no que diz respeito ao editor padrão e ao PATH.
3. Após a instalação, você pode verificar se foi bem-sucedida abrindo o Git Bash ou o CMD e digitando git --version.


### Para macOS:

1. Você pode instalar o Git usando o Homebrew (um gerenciador de pacotes para macOS). Se não tiver o Homebrew, instale-o primeiro com o comando: /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)".
2. Após instalar o Homebrew, instale o Git com o comando: brew install git.
3. Verifique a instalação com git --version no Terminal.

### Para Linux:

1. Abra o terminal.
2. Dependendo da distribuição, use o gerenciador de pacotes apropriado:
   - Para Debian/Ubuntu: sudo apt-get install git
   - Para Fedora: sudo dnf install git
   - Para Arch Linux: sudo pacman -S git
3. Confirme a instalação com git --version.

### Configuração inicial do Git
Após a instalação, você precisará configurar algumas informações básicas. Isso é importante porque cada commit no Git usa esta informação:
```
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```


### Definindo o editor padrão:
Você pode escolher o editor de texto para usar com o Git quando precisar digitar mensagens de commit ou interagir de outras formas que requerem entrada de texto. Por exemplo, para configurar o VSCode como seu editor padrão, use:

```
git config --global core.editor "code --wait"
```


Você também pode verificar todas as configurações do Git com o comando:

```
git config --list
```
Este comando mostra todas as configurações do Git, incluindo nome, email e qualquer outra opção que você tenha configurado.

## 2. Repositórios Git: Local e Remoto
### Inicialização de um Novo Repositório
### Criar um repositório local:
1. **Abra o terminal**(ou o Git Bash em sistemas Windows).
2. **Navegue até a pasta** onde você deseja iniciar o repositório usando o comando cd. Por exemplo: cd ~/meuprojeto.
3. **Inicialize o repositório** com o comando:
```
git init
```
Isso criará um novo subdiretório chamado .git que contém todos os arquivos necessários do repositório Git. Também tornará a pasta atual um repositório Git onde você pode começar a adicionar arquivos e fazer commits.

### Clonagem de um Repositório Existente
### Clonar um repositório remoto:

1. **Obtenha o URL do repositório** que você deseja clonar. Isso pode ser encontrado na página do repositório no GitHub (ou qualquer outra plataforma de hospedagem Git). O URL geralmente se parece com isso: https://github.com/usuario/repositorio.git.
2. **Use o comando clone** no terminal:
```
git clone https://github.com/usuario/repositorio.git
```
Isso criará uma cópia local do repositório em seu computador, incluindo todos os arquivos, branches e commits.

### Diferença Entre Repositórios Locais e Remotos

### Repositório Local:

1. É a cópia do repositório que reside no seu sistema local.
2. Você pode fazer alterações, como commits, sem qualquer conexão com a internet.
3. É privado, a menos que você decida sincronizar e compartilhar suas alterações por meio de um repositório remoto.

### Repositório Remoto:

1. É a versão do repositório hospedada em um serviço de servidor, como GitHub, GitLab, ou Bitbucket.
2. Serve como um ponto central, onde colaboradores podem sincronizar mudanças.
3. Facilita a colaboração entre vários desenvolvedores, pois qualquer um com acesso pode clonar o repositório, fazer alterações e propor atualizações.

## 3. Trabalhando com Múltiplos Branches

### Criação e Gerenciamento de Branches
### Criar um novo branch:
- Para criar um novo branch, use o comando:
```
git branch nome-do-branch
```
Isso cria um novo branch baseado no estado atual do branch em que você está (geralmente o master ou main).

- Para começar a trabalhar no novo branch, você deve mudar para ele usando:
```
git checkout nome-do-branch
```
A partir de agora, todos os commits que você fizer serão feitos nesse branch.

### Listar branches:
-   Para ver todos os branches existentes no seu repositório (o asterisco mostra o branch atual):
```
git branch
```

### Deletar um branch:
-   Para deletar um branch local que você não precisa mais:
```
git branch -d nome-do-branch
```
-   Se o branch não foi completamente mesclado e você ainda quer deletá-lo, use:
```
git branch -D nome-do-branch
```

### Uso Prático de Branches para Diferentes Ambientes
Em muitos fluxos de trabalho de desenvolvimento, especialmente em equipes, é comum usar diferentes branches para diferentes propósitos:
1. **Desenvolvimento:** Normalmente chamado **dev** ou **develop**, este branch serve como um ambiente ativo para desenvolvimento onde todas as novas funcionalidades, correções e melhorias são integradas antes de serem estáveis e prontas para produção.
2. **Produção:** Geralmente chamado **master** ou **main**, é o branch que reflete o código atual em produção. É estável e as mudanças só são feitas aqui após testes rigorosos.

### Exemplo de workflow:

1. **Desenvolvimento de novas funcionalidades:** Crie um branch a partir do **develop** para cada nova funcionalidade.
2. **Teste e revisão:** Uma vez concluída, crie um pull request para o **develop**.
3. **Preparação para lançamento:** Após um ciclo de desenvolvimento, as funcionalidades no develop são testadas juntas e depois mescladas no **release branch**, que eventualmente será mesclado em **main**.

### Navegação entre Branches
-   Para alternar entre branches:
```
git checkout nome-do-branch
```
Isso muda seu diretório de trabalho para o branch especificado.

## 4. Integração com IDEs

### VSCode

### Instalação da Extensão Git:
1. **Abrir o VSCode**.
2. **Acessar a aba de extensões** (ícone de blocos na barra lateral esquerda ou Ctrl+Shift+X).
3. **Pesquisar por "Git"** e escolher a extensão oficial chamada "GitLens" ou outra que preferir, como "Git History".
4. **Clicar em instalar**.

***Gerenciamento de branches e commits através do VSCode:***

- Branches:
1. **Acessar o painel do Git** (ícone de três pontos no canto inferior esquerdo ou Ctrl+Shift+G).
2. **Criar, alternar e deletar branches** diretamente pela interface gráfica.
- Commits:
1. **Fazer alterações nos arquivos** e salvá-los.
2. **Abrir o painel do Git**, ver as mudanças, e adicionar arquivos ao stage (área de preparação) clicando no sinal de mais.
3. **Digitar uma mensagem de commit** e confirmar o commit clicando no ícone de check.


### Eclipse

### Configuração do Plugin EGit:
1. **Abrir o Eclipse**.
2. **Ir para Help > Eclipse Marketplace**.
3. **Pesquisar por "EGit"** e instalar o plugin.

***Execução de Operações Git Dentro do Eclipse:***
- **Clonagem de Repositórios: File > Import > Git > Projects from Git**.
- **Criação de Branches, Commits e Merges:** Acessível através do painel Git na perspectiva Team > Git.
- **Gerenciar Repositórios:** Pode ser feito através do Git Repositories view, onde você pode adicionar, commitar, push e pull, assim como criar e mesclar branches.


### Android Studio

### Uso do Controle de Versão Integrado para Gerenciar Projetos Android:
1. **Abrir o Android Studio e seu projeto**.
2. **Ativar o VCS: VCS > Enable Version Control Integration**, escolha Git como o sistema de controle de versão.
3. **Commit de Alterações: VCS > Commit** (ou Ctrl+K), que permite selecionar arquivos, escrever mensagens de commit, e commitar.
4. **Gerenciamento de Branches:** Acesso através de VCS > Git > Branches, permitindo criar, mudar e deletar branches.
5. **Push e Pull de Alterações:** Feitos através de VCS > Git, escolhendo Push (Ctrl+Shift+K) ou Pull.

## 5. Estratégias de Branching

### Estratégia de Manutenção e Produção Separadas
1. Criar um branch de hotfix a partir do main:


```
git checkout main
git pull
git checkout -b hotfix/nome-do-hotfix
```

2. Após concluir o hotfix, mesclar de volta ao main:

```
git checkout main
git merge hotfix/nome-do-hotfix
git push
```
3. Também mesclar o hotfix ao branch de desenvolvimento (ex: develop):

```
git checkout develop
git merge hotfix/nome-do-hotfix
git push
```

4. Deletar o branch de hotfix após a mesclagem:

```
git branch -d hotfix/nome-do-hotfix
```

### Branches de Feature: Gerenciamento e Melhores Práticas

1. Criar um branch de feature a partir do develop:

```
git checkout develop
git pull
git checkout -b feature/nova-feature
```

2. Trabalhar na feature e fazer commits regularmente:

```
git add .
git commit -m "Adiciona nova funcionalidade"
```

3. Manter o branch de feature atualizado com o develop para evitar conflitos futuros:

```
git fetch origin
git rebase origin/develop
```

4. Submeter a feature para revisão através de um pull request:

   - Isso geralmente é feito através da interface do GitHub ou de outra plataforma de hospedagem Git, onde você compara seu branch de feature com o branch develop e cria um pull request.

5. Após o pull request ser aprovado e mesclado, deletar o branch de feature localmente e remotamente:

```
git checkout develop
git pull
git branch -d feature/nova-feature
git push origin --delete feature/nova-feature
```

## 6. Commits e Gerenciamento de Versão

No Git, fazer commits de maneira eficaz e estratégica é fundamental para manter um histórico de versões limpo e útil, facilitando o entendimento das mudanças e a manutenção do projeto. Vamos discutir como realizar commits intermediários eficientes, estratégias para commits limpos, e o uso de tags para marcar lançamentos de versões.

### Realização de Commits Intermediários em Desenvolvimento
**Commits intermediários** são importantes para salvar o progresso do seu trabalho sem necessariamente completar uma funcionalidade inteira. Isso é útil em casos de mudanças de prioridade ou problemas que exigem que você mude de tarefa temporariamente.

- **Comande bem:** Faça commits frequentemente, mas apenas de mudanças que compõem uma unidade lógica de trabalho. Isso pode ser uma correção de bug, uma pequena adição ou uma melhoria em uma funcionalidade existente.

```
git add arquivo-modificado.js
git commit -m "Corrige o bug no cálculo de taxas"
```
   - Use mensagens claras e descritivas: As mensagens de commit devem ser concisas e explicar claramente o porquê das mudanças feitas.

### Estratégias para Commits Limpos e Eficazes
1. **Commit Atomizado:** Cada commit deve representar uma única "unidade atômica" de mudança. Isso facilita o rollback de mudanças específicas sem afetar outras funcionalidades.

2. **Squash de Commits:** Antes de mesclar um branch de feature, você pode "amassar" múltiplos commits em um só, se eles forem parte do mesmo trabalho. Isso ajuda a manter o histórico de commits limpo e fácil de entender.

- Usando Git no terminal:
```
git rebase -i HEAD~3  # "3" é o número de commits que você quer squash
```
   - No editor que aparece, substitua pick por squash para os commits que deseja combinar e então salve e saia.

3. **Revisão e Rebase:** Regularmente rebase seu branch de feature com o branch principal (como **main** ou **develop**) para manter a sincronia e reduzir conflitos.

### Tagging para Marcar Lançamentos de Versões
As **tags** no Git são usadas para marcar pontos específicos no histórico do repositório como importantes — geralmente, lançamentos de versões (v1.0, v2.0, etc.).

- Criar uma tag:
```
git tag -a v1.0 -m "Versão inicial"
git push origin v1.0
```

- Listar tags:
```
git tag
```

- Deletar uma tag:
```
git tag -d v1.0
git push origin --delete v1.0
```

## 7. Fluxo de Trabalho Avançado
Um fluxo de trabalho avançado em Git inclui não apenas a gestão de branches e commits, mas também a gestão eficaz de como as mudanças são rastreadas e documentadas através de BACKLOG, CHANGELOG e versionamento semântico (X.Y.Z). Vamos explorar como esses componentes se integram ao fluxo de trabalho de desenvolvimento.

### BACKLOG
O BACKLOG é fundamentalmente uma lista organizada de tarefas e funcionalidades planejadas para o projeto. Embora a implementação exata possa variar dependendo das ferramentas utilizadas, vou dar um exemplo de como você pode gerenciar um BACKLOG usando o GitHub Issues, que é uma forma comum e integrada ao ambiente de desenvolvimento.

**Exemplo de Criação e Gerenciamento de BACKLOG no GitHub:**

**1. Criar um Issue:**
   - Vá até a aba "Issues" no seu repositório GitHub.
   - Clique em "New issue".
   - Adicione um título e uma descrição detalhada para a tarefa.
   - Você pode categorizar a issue usando labels como **bug**, **feature**, **enhancement**.

**2. Priorização e Organização:**
   - Use Milestones para agrupar issues em metas específicas ou sprints.
   - Priorize issues dentro dos Milestones usando labels como high priority, low priority.

### CHANGELOG
Um CHANGELOG é um arquivo que registra todas as mudanças significativas feitas em cada lançamento de um projeto. Aqui está um exemplo de como você pode manter um **CHANGELOG.md** em seu repositório:

**Exemplo de Conteúdo de CHANGELOG.md:**
```
# Changelog
Todas as mudanças notáveis neste projeto serão documentadas neste arquivo.

## [1.0.1] - 2024-05-14
### Fixed
- Correção de bug que impedia a exportação de arquivos CSV em sistemas Windows.

## [1.0.0] - 2024-05-10
### Added
- Função de login através de redes sociais.
- Sistema de backup automático de dados.

### Changed
- Melhoria no algoritmo de busca, aumentando a velocidade de resposta em 20%.

### Fixed
- Correção de layout no formulário de contato.
```

**Práticas:**

   - Mantenha o changelog atualizado a cada release.
   - Use hyperlinks para referenciar commits e pull requests para detalhar as mudanças.

### Versionamento Semântico (SemVer)
O Versionamento Semântico é uma prática de versionar software de forma a explicitar o tipo de mudanças feitas. Aqui está como você poderia aplicar isso usando tags no Git.

**Comandos para Tagging de Versão no Git:**

- **Criar uma nova tag:**
```
git tag -a v2.0.0 -m "Lançamento da versão 2.0.0 com grandes mudanças na API"
git push origin v2.0.0
```

- **Listar todas as tags:**
```
git tag
```

**Código e Práticas:**
   - Aumente o primeiro número (X) se houver mudanças que quebrem a compatibilidade.
   - Aumente o segundo número (Y) se novas funcionalidades forem adicionadas de forma compatível.
   - Aumente o terceiro número (Z) para correções de bugs.

## 8. Resolução de Conflitos

### Técnicas para Resolução de Conflitos

**1. Entender o Conflito:**
   - Antes de tentar resolver um conflito, é importante entender as alterações feitas em cada branch que está tentando ser mesclada. Isso ajuda a determinar qual mudança deve prevalecer ou como integrar ambas de forma coerente.

**2. Comunicação:**
   - Quando o conflito envolve múltiplos colaboradores, discutir as mudanças com todos os envolvidos é crucial. Isso pode evitar mal-entendidos e ajudar a chegar a uma solução que todos concordam.

**3. Uso Eficiente do Git Merge:**
   - O comando git merge é frequentemente usado para mesclar branches. Quando ocorre um conflito, o Git pausa o processo de merge e marca os arquivos conflitantes no código.
   - Você deve abrir esses arquivos e decidir manualmente como resolver os conflitos, escolhendo entre as mudanças do branch atual ou do branch que está sendo mesclado, ou combinando ambas de alguma forma.

**4. Rebase Como Alternativa:**
   - Usar **git rebase** em vez de **git merge** pode ser uma maneira de evitar alguns tipos de conflitos, pois ele recria a série de commits de um branch sobre a ponta de outro, podendo resultar em um histórico de projeto mais limpo.

### Ferramentas para Resolução de Conflitos

**1. Ferramentas Integradas nas IDEs:**
   - Muitas IDEs, como Visual Studio Code, IntelliJ IDEA e Eclipse, têm ferramentas integradas de resolução de conflitos que apresentam as diferenças lado a lado e permitem que você escolha entre as alterações de forma interativa.
   - Exemplo no Visual Studio Code:
      -Abra os arquivos conflitantes, e o VSCode mostrará as mudanças conflitantes com opções para aceitar "Current Change", "Incoming Change", ou ambos.

**2. Ferramentas Externas:**

   - Existem várias ferramentas dedicadas à resolução de conflitos, como KDiff3, Beyond Compare, e Meld.
   - Essas ferramentas podem ser configuradas para serem usadas com Git definindo a configuração merge.tool:
```
git config --global merge.tool kdiff3
```

**Comando Básico para Iniciar a Resolução de Conflitos**
```
# Após um conflito ter ocorrido durante um merge
git status  # Verifica os arquivos conflitantes
# Manualmente resolva os conflitos nos arquivos indicados
git add arquivo_resolvido  # Marca o arquivo como resolvido
git commit  # Finaliza o processo de merge
```

## 9. Estudos de Caso e Melhores Práticas
### Exemplos Reais de Utilização do Git

**1. Projeto Linux Kernel:**
   - **Descrição:** O Linux Kernel é um dos maiores e mais ativos projetos open source do mundo. Ele utiliza o Git para gerenciar o desenvolvimento de seu enorme código base.
   - **Práticas:** Devido à sua escala, o projeto Linux utiliza uma hierarquia de repositórios. Mudanças são submetidas como patches para revisão via mailing lists antes de serem aceitas no repositório principal. Os mantenedores de sub-sistemas gerenciam seus próprios repositórios e contribuem para o repositório principal.

**2. Microsoft usando Git para Windows:**
   - **Descrição:** A Microsoft utiliza Git para gerenciar o desenvolvimento do Windows, que é um dos maiores repositórios privados no mundo.
   - **Práticas:** Devido ao tamanho do repositório, a Microsoft desenvolveu o GVFS (Git Virtual File System), que permite que o Git gerencie eficientemente grandes repositórios ao carregar apenas uma parte do código necessário para cada desenvolvedor.

**Dicas para Manter a Integridade do Repositório**

**1. Utilize Branches Estrategicamente:**
   - Mantenha branches separados para desenvolvimento, testes e produção. Isso não apenas ajuda a manter a estabilidade do código em produção, mas também permite testes e desenvolvimentos paralelos sem interferência.

**2. Padronize Mensagens de Commit:**
   - Implemente um padrão para mensagens de commit para garantir que eles sejam informativos e consistentes. Isso facilita a compreensão das mudanças históricas para todos os membros da equipe.

**3. Revisão de Código:**
   - Faça revisões de código antes de mesclar qualquer branch ao branch principal. Isso ajuda a manter a qualidade do código e reduz a chance de introduzir erros.

**4. Use Tags e Releases:**
   - Utilize tags para marcar lançamentos ou pontos importantes no histórico do projeto. Isso facilita o rastreamento de versões específicas e ajuda na gestão de releases.

**5. Automatize Testes:**

   - Integre testes automatizados em seu processo de integração contínua. Garantir que todos os commits e branches passem por testes antes de serem mesclados ajuda a manter a integridade do código no repositório.

**6. Backup Regular:**
   - Embora o Git seja uma ferramenta de versionamento robusta, é importante fazer backups regulares do repositório, especialmente para repositórios críticos. Isso protege contra perdas de dados acidentais.

**7. Eduque Sua Equipe:**
   - Assegure-se de que todos os membros da equipe entendam as práticas de Git adotadas no projeto. Treinamentos regulares e recursos de aprendizado podem ajudar a manter todos na mesma página.
