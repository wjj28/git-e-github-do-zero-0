# Módulo 01 · Preparar o ambiente

## Objetivos

No fim deste módulo tens:

- Uma conta no GitHub.
- O Git instalado e configurado com o teu nome e email.
- O VS Code instalado como editor.

## 1. Criar a conta no GitHub

1. Vai a <https://github.com/signup>.
2. Indica o email, uma palavra-passe e um nome de utilizador.
3. Confirma o email com o código que recebes.

**Sobre o nome de utilizador:** vai aparecer no endereço do teu perfil (`github.com/o-teu-nome`) e em todos os teus projetos. Escolhe algo profissional e simples, de preferência próximo do teu nome real. Evita datas, alcunhas e números aleatórios.

**Segurança:** ativa a autenticação de dois fatores em *Settings → Password and authentication*. O GitHub exige-a a quem contribui com código.

## 2. Instalar o Git

### Windows

1. Descarrega o instalador em <https://git-scm.com/downloads>.
2. Executa-o. As opções por omissão servem, com duas atenções:
   - No editor por omissão, escolhe **Visual Studio Code** (se já o tiveres instalado).
   - No nome da branch inicial, escolhe **"Override the default branch name"** e escreve `main`.
3. No fim ficas com o **Git Bash**, o terminal que vamos usar no curso.

Em alternativa, pelo terminal do Windows:

```powershell
winget install --id Git.Git -e --source winget
```

### macOS

Abre o Terminal e escreve:

```bash
git --version
```

Se o Git não estiver instalado, o macOS propõe instalar as ferramentas de linha de comandos. Aceita. Quem usa o [Homebrew](https://brew.sh) pode fazer `brew install git`.

### Linux (Debian / Ubuntu)

```bash
sudo apt update
sudo apt install git
```

### Confirmar a instalação

Abre o terminal (no Windows, o **Git Bash**) e escreve:

```bash
git --version
```

Deves ver algo como `git version 2.52.0`. O número exato não importa.

## 3. Configurar o Git

O Git assina cada commit com um nome e um email. Configura-os uma vez:

```bash
git config --global user.name "O Teu Nome"
git config --global user.email "o-teu-email@exemplo.com"
```

Usa **o mesmo email da conta GitHub**, para que os commits fiquem associados ao teu perfil.

> **Privacidade:** o email dos commits é público. Se não o quiseres expor, vai a *Settings → Emails* no GitHub, ativa *Keep my email addresses private* e usa no Git o endereço `...@users.noreply.github.com` que lá aparece.

Mais duas configurações recomendadas:

```bash
# A primeira branch de cada repositório novo chama-se "main"
git config --global init.defaultBranch main

# O VS Code passa a ser o editor que o Git abre quando precisa
git config --global core.editor "code --wait"
```

Fins de linha (evita avisos e diferenças falsas entre sistemas):

```bash
# Windows
git config --global core.autocrlf true

# macOS e Linux
git config --global core.autocrlf input
```

Confirma tudo com:

```bash
git config --global --list
```

A opção `--global` aplica a configuração a todos os repositórios do teu utilizador. Sem ela, a configuração vale só para o repositório onde estás.

## 4. Instalar o VS Code

1. Descarrega em <https://code.visualstudio.com>.
2. No instalador do Windows, marca **"Add to PATH"** e **"Open with Code"**.
3. Confirma no terminal:

```bash
code --version
```

O VS Code já traz integração com o Git (o ícone *Source Control* na barra lateral). Durante o curso usamos sobretudo o terminal, para perceberes o que os botões fazem por baixo.

## Exercícios

1. Corre `git config --global user.name` (sem valor à frente). O que aparece?
2. Corre `git help config`. Onde é que a ajuda abriu?
3. Preenche o teu perfil do GitHub: fotografia, nome e uma frase de biografia.

## Checklist

- [ ] Tenho conta no GitHub com autenticação de dois fatores.
- [ ] `git --version` mostra um número de versão.
- [ ] `git config --global --list` mostra o meu nome e email.
- [ ] `code --version` funciona.

## Referências

**Português**

- [Pro Git: Instalando o Git](https://git-scm.com/book/pt-br/v2/Primeiros-Passos-Instalando-o-Git)
- [Pro Git: Configuração inicial do Git](https://git-scm.com/book/pt-br/v2/Primeiros-Passos-Configura%C3%A7%C3%A3o-inicial-do-Git)
- [GitHub Docs: Configurar o Git](https://docs.github.com/pt/get-started/git-basics/set-up-git)

**English**

- [Pro Git: First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup)
- [GitHub Docs: Set up Git](https://docs.github.com/en/get-started/git-basics/set-up-git)
- [VS Code: Using Git source control](https://code.visualstudio.com/docs/sourcecontrol/overview)

---

[← 00 Introdução](../00-introducao/README.md) · [Início](../../README.md) · Seguinte: [02 Terminal básico →](../02-terminal-basico/README.md)
