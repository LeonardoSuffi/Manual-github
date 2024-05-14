# 1. Manual Github do Professor Rold
## Instalação do Git
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
   • Para Debian/Ubuntu: sudo apt-get install git
   • Para Fedora: sudo dnf install git
   • Para Arch Linux: sudo pacman -S git
4. Confirme a instalação com git --version.

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
1. Para criar um novo branch, use o comando:
```
git branch nome-do-branch
```
Isso cria um novo branch baseado no estado atual do branch em que você está (geralmente o master ou main).

2. Para começar a trabalhar no novo branch, você deve mudar para ele usando:
```
git checkout nome-do-branch
```
A partir de agora, todos os commits que você fizer serão feitos nesse branch.

### Listar branches:
•   Para ver todos os branches existentes no seu repositório (o asterisco mostra o branch atual):
```
git branch
```

### Deletar um branch:
•   Para deletar um branch local que você não precisa mais:
```
git branch -d nome-do-branch
```
•   Se o branch não foi completamente mesclado e você ainda quer deletá-lo, use:
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
•   Para alternar entre branches:
```
git checkout nome-do-branch
```
Isso muda seu diretório de trabalho para o branch especificado.
