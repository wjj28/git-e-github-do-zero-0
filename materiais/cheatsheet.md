# Cheatsheet de Git

Os comandos mais usados, por situação. O texto entre `< >` é para substituir.

## Configuração

| Comando | O que faz |
|---------|-----------|
| `git config --global user.name "Nome"` | Define o nome do autor |
| `git config --global user.email "email"` | Define o email do autor |
| `git config --global init.defaultBranch main` | Branch inicial passa a ser `main` |
| `git config --global --list` | Mostra a configuração |

## Começar

| Comando | O que faz |
|---------|-----------|
| `git init` | Cria um repositório na pasta atual |
| `git clone <url>` | Copia um repositório remoto |

## Dia a dia

| Comando | O que faz |
|---------|-----------|
| `git status` | Mostra o estado do repositório |
| `git add <ficheiro>` | Prepara um ficheiro para o commit |
| `git add .` | Prepara tudo o que mudou |
| `git commit -m "mensagem"` | Grava um commit |
| `git commit -am "mensagem"` | `add` + `commit` de ficheiros já acompanhados |
| `git diff` | Alterações ainda não preparadas |
| `git diff --staged` | Alterações preparadas |

## Histórico

| Comando | O que faz |
|---------|-----------|
| `git log` | Histórico completo |
| `git log --oneline` | Um commit por linha |
| `git log --oneline --graph --all` | Com o desenho de todas as branches |
| `git show <hash>` | Detalhes de um commit |

## Desfazer

| Comando | O que faz |
|---------|-----------|
| `git restore <ficheiro>` | Deita fora alterações não gravadas ⚠️ |
| `git restore --staged <ficheiro>` | Retira da área de preparação |
| `git commit --amend` | Corrige o último commit (só se for local) |
| `git reset --soft HEAD~1` | Desfaz o último commit, mantém as alterações |
| `git reset --hard HEAD~1` | Desfaz o último commit e apaga as alterações ⚠️ |
| `git revert <hash>` | Cria um commit que anula outro |
| `git rm --cached <ficheiro>` | Deixa de acompanhar um ficheiro sem o apagar |

⚠️ = destrói trabalho que não esteja num commit.

## Branches

| Comando | O que faz |
|---------|-----------|
| `git branch` | Lista as branches |
| `git switch -c <nome>` | Cria uma branch e muda para ela |
| `git switch <nome>` | Muda de branch |
| `git merge <nome>` | Junta a branch indicada à atual |
| `git merge --abort` | Cancela um merge em conflito |
| `git branch -d <nome>` | Apaga uma branch já integrada |

## Remotos

| Comando | O que faz |
|---------|-----------|
| `git remote -v` | Lista os remotos |
| `git remote add origin <url>` | Liga o repositório a um remoto |
| `git push -u origin <branch>` | Envia e liga a branch (primeira vez) |
| `git push` | Envia os commits |
| `git pull` | Traz e integra as novidades |
| `git fetch` | Traz as novidades sem integrar |
| `git push origin --delete <branch>` | Apaga uma branch no remoto |

## Avançado

| Comando | O que faz |
|---------|-----------|
| `git stash` | Guarda as alterações de lado |
| `git stash pop` | Recupera o que foi guardado |
| `git tag -a v1.0.0 -m "mensagem"` | Cria uma tag |
| `git push origin --tags` | Envia as tags |
| `git describe` | Mostra a tag mais próxima e a distância até ela |
| `git rebase <branch>` | Reaplica os commits em cima de outra branch |
| `git rebase -i HEAD~3` | Revê os últimos 3 commits: juntar, reordenar, apagar |
| `git pull --rebase` | Traz as novidades e reaplica os teus commits locais por cima |
| `git switch --detach <hash>` | Visita um commit antigo (HEAD separado) |
| `git cherry-pick <hash>` | Copia um commit para a branch atual |
| `git reflog` | Mostra todos os movimentos do `HEAD` |

## Fluxo completo de uma tarefa

```bash
git switch main
git pull
git switch -c minha-tarefa
# ... editar ...
git status
git add .
git commit -m "Descreve a alteração"
git push -u origin minha-tarefa
# abrir pull request no GitHub, rever, integrar
git switch main
git pull
git branch -d minha-tarefa
```

## Outras cheatsheets

- [GitHub Git Cheat Sheet (português)](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet/)
- [GitHub Git Cheat Sheet (English, PDF)](https://education.github.com/git-cheat-sheet-education.pdf)
- [Atlassian Git Cheat Sheet (English)](https://www.atlassian.com/git/tutorials/atlassian-git-cheatsheet)
