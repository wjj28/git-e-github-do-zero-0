# Módulo 09 · Ferramentas avançadas

## Objetivos

No fim deste módulo consegues:

- Guardar trabalho a meio com `stash`.
- Marcar versões com tags.
- Usar `rebase` e `cherry-pick` e saber quando os evitar.
- Recuperar commits "perdidos" com `reflog`.

Não precisas destas ferramentas todos os dias. Precisas de saber que existem para as reconheceres quando fizerem falta.

## `git stash`: guardar trabalho a meio

Estás a meio de uma alteração e precisas de mudar de branch para tratar de uma urgência. O trabalho não está pronto para um commit. O `stash` guarda-o de lado e limpa a pasta de trabalho.

```bash
git stash                 # guarda as alterações e limpa a pasta
git stash -u              # igual, incluindo ficheiros novos (untracked)
git stash list            # lista o que está guardado
git stash pop             # recupera o último e remove-o da lista
git stash apply           # recupera o último mas mantém-no na lista
git stash drop            # apaga o último sem recuperar
```

Dá-lhe um nome para não te perderes:

```bash
git stash push -m "formulário de contacto a meio"
```

O stash é local e temporário. Para trabalho que vai ficar parado mais de um dia, prefere um commit numa branch.

## Tags: marcar versões

Uma **tag** é um nome fixo para um commit. Usa-se para marcar versões: `v1.0.0`, `v1.1.0`.

```bash
git tag -a v1.0.0 -m "Primeira versão estável"
git tag                      # lista as tags
git show v1.0.0              # detalhes
git push origin v1.0.0       # envia uma tag
git push origin --tags       # envia todas
```

As tags não vão no `git push` normal. Têm de ser enviadas explicitamente.

No GitHub, uma tag pode ser transformada numa **Release**, com notas e ficheiros para descarregar.

Para saber a que distância estás da última versão:

```bash
git describe
```

A resposta tem a forma `v1.0.0-3-ga1b2c3d`: a tag mais próxima, o número de commits feitos desde então e o hash abreviado do commit atual (depois do `g`). Se estiveres exatamente em cima da tag, mostra só `v1.0.0`.

### Versionamento semântico

O formato habitual é `MAIOR.MENOR.CORREÇÃO`:

| Parte | Sobe quando |
|-------|-------------|
| MAIOR (`2.0.0`) | Há alterações que partem a compatibilidade |
| MENOR (`1.1.0`) | Há funcionalidades novas, compatíveis |
| CORREÇÃO (`1.0.1`) | Há correções de erros |

## `git rebase`: reescrever a base

O `rebase` é uma alternativa ao `merge` para atualizar a tua branch com o que há de novo na `main`. Em vez de criar um commit de merge, **reaplica os teus commits em cima** da `main` atual. O histórico fica numa linha reta.

```bash
git switch minha-branch
git rebase main
```

Antes:

```text
main:          A - B - C
                    \
minha-branch:        X - Y
```

Depois do rebase:

```text
main:          A - B - C
                        \
minha-branch:            X' - Y'
```

`X'` e `Y'` são commits **novos** com o mesmo conteúdo. Os hashes mudam.

Se houver conflitos, o rebase para em cada commit:

```bash
# resolve o conflito no ficheiro, depois:
git add ficheiro
git rebase --continue

# ou desiste e volta ao início:
git rebase --abort
```

> **Regra de ouro do rebase:** nunca faças rebase de commits que já partilhaste e que outras pessoas possam estar a usar. O rebase reescreve a história. Usa-o só nas tuas branches locais ou em branches onde trabalhas sozinho.

### Merge ou rebase?

| | Merge | Rebase |
|---|-------|--------|
| Histórico | Mostra o que aconteceu de facto, com bifurcações | Linear e limpo |
| Segurança | Não reescreve nada | Reescreve commits |
| Para quem começa | Recomendado | Só depois de dominar o merge |

Cada equipa tem a sua preferência. Na dúvida, usa `merge`.

### Atualizar com rebase em vez de merge

Quando o `git push` é rejeitado porque o remoto tem commits novos, o `git pull` resolve com um commit de merge. Se preferires manter o histórico em linha reta:

```bash
git pull --rebase
git push
```

O `git pull --rebase` descarrega as novidades e reaplica os teus commits **locais** em cima delas. Como esses commits ainda não foram partilhados, não quebra a regra de ouro.

### Rebase interativo: arrumar commits antes de partilhar

O rebase interativo deixa-te rever os teus últimos commits antes de os enviares: juntar, reordenar, mudar mensagens ou apagar.

```bash
git rebase -i HEAD~3
```

Abre-se o editor com os últimos três commits, do mais antigo para o mais recente:

```text
pick a1b2c3d Adiciona formulário de contacto
pick d4e5f6a Corrige gralha no formulário
pick b7c8d9e Adiciona validação do email
```

Troca a palavra `pick` pelo que queres fazer a cada commit, grava e fecha:

| Palavra | O que faz |
|---------|-----------|
| `pick` | Mantém o commit como está |
| `reword` | Mantém o commit, mas deixa-te mudar a mensagem |
| `squash` | Junta o commit ao da linha de cima |
| `drop` | Apaga o commit |

Para mudar a ordem dos commits, muda a ordem das linhas.

Caso típico: fizeste um commit e logo a seguir outro a corrigir uma gralha. Com `squash` na segunda linha, ficam um só commit limpo. Vale a mesma regra de ouro: só em commits que ainda não partilhaste.

## `git cherry-pick`: copiar um commit

Aplica um commit específico de outra branch na branch atual.

```bash
git switch main
git cherry-pick a1b2c3d
```

Caso típico: uma correção urgente foi feita numa branch de desenvolvimento e precisas dela já na `main`, sem trazer o resto.

## `git reflog`: a rede de segurança

O `reflog` regista todos os sítios por onde o `HEAD` passou, incluindo commits que já não aparecem no `git log` depois de um `reset --hard` ou de um rebase mal feito.

```bash
git reflog
```

```text
a1b2c3d HEAD@{0}: reset: moving to HEAD~2
f4e5d6c HEAD@{1}: commit: Adiciona relatório mensal
```

Para recuperar o commit "perdido":

```bash
git switch -c recuperado f4e5d6c
```

Enquanto algo esteve num commit, quase sempre dá para recuperar. O que nunca chegou a um commit é que se perde. Por isso: **faz commits frequentes**.

## Alias: atalhos para comandos

```bash
git config --global alias.st status
git config --global alias.lg "log --oneline --graph --all"
```

Agora `git st` e `git lg` funcionam como atalhos.

## Exercícios

1. Altera um ficheiro, guarda com `git stash`, muda de branch, volta e recupera com `git stash pop`.
2. Cria a tag `v0.1.0` no teu repositório e envia-a para o GitHub. Cria uma Release a partir dela.
3. Cria uma branch, faz dois commits nela e um commit na `main`. Atualiza a branch com `git rebase main` e compara o `git log --oneline --graph --all` com o de um merge.
4. Usa `cherry-pick` para trazer um único commit de uma branch para a `main`.
5. Faz um commit, apaga-o com `git reset --hard HEAD~1` e recupera-o com a ajuda do `reflog`.
6. Cria um alias para o teu comando de log preferido.
7. Faz três commits pequenos numa branch local e junta-os num só com `git rebase -i HEAD~3`.

## Quiz e desafio

- Testa o que aprendeste no [quiz do módulo 09](quiz.md).
- Faz a Etapa 5 do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md). Com ela chegas à meta Prata.
- Joga os atos 3 e 4 do [Gitvana](../../desafios/README.md#gitvana): rebase, `--amend` e `reflog` sobre ficheiros verdadeiros.
- Para repetir no teu terminal, resolve os primeiros exercícios do [Git Exercises](../../desafios/README.md#git-exercises).

## Checklist

- [ ] Sei guardar e recuperar trabalho com `stash`.
- [ ] Sei criar e enviar tags.
- [ ] Sei a regra de ouro do rebase.
- [ ] Sei que o `reflog` existe e para que serve.

## Referências

**Português**

- [Pro Git: Rebase](https://git-scm.com/book/pt-br/v2/Ramifica%C3%A7%C3%A3o-Branching-no-Git-Rebase-Rebasing)
- [Pro Git: Criando tags](https://git-scm.com/book/pt-br/v2/Fundamentos-do-Git-Criando-Tags)
- [Versionamento Semântico 2.0.0](https://semver.org/lang/pt-BR/)
- [Dangit, Git!? (como sair de sarilhos)](https://dangitgit.com/pt_BR)

**English**

- [Pro Git: Rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
- [Pro Git: Stashing and Cleaning](https://git-scm.com/book/en/v2/Git-Tools-Stashing-and-Cleaning)
- [Atlassian: Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
- [Atlassian: git reflog](https://www.atlassian.com/git/tutorials/rewriting-history/git-reflog)

---

[← 08 Boas práticas](../08-boas-praticas/README.md) · [Início](../../README.md) · Seguinte: [10 Projeto final →](../10-projeto-final/README.md)
