# Desafio · Learn Git Branching

O [Learn Git Branching](https://learngitbranching.js.org/?locale=pt_BR) é um jogo gratuito que corre no browser. Escreves comandos Git num terminal simulado e vês a árvore de commits a mudar à tua frente. Não instala nada e não toca nos teus repositórios, por isso podes errar à vontade.

O desafio é completar os **36 níveis** do jogo, por etapas, à medida que avanças no curso.

## Como funciona o jogo

Cada nível mostra uma árvore de commits de partida e uma árvore objetivo. Ganhas quando a tua árvore fica igual à do objetivo. No fim, o jogo diz-te quantos comandos usaste e quantos usa a solução dele.

Comandos do jogo (escrevem-se no terminal do jogo, não são comandos Git):

| Comando | O que faz |
|---------|-----------|
| `levels` | Abre a lista de níveis |
| `level intro1` | Vai diretamente para um nível, pelo identificador |
| `objective` | Volta a mostrar a explicação do nível |
| `show goal` | Mostra a árvore objetivo |
| `hint` | Dá uma pista |
| `undo` | Desfaz o último comando |
| `reset` | Recomeça o nível |
| `sandbox` | Sai do nível para uma área livre, sem objetivo |
| `show solution` | Mostra a solução (ver as regras abaixo) |

### Diferenças em relação ao Git real

- **Não há ficheiros** na maior parte dos níveis. Um `git commit` cria logo um commit, sem `git add` e sem mensagem. O jogo treina a forma da árvore, não o conteúdo.
- Os commits chamam-se `C0`, `C1`, `C2`... em vez de terem um hash. Usas esses nomes onde no Git real usarias o hash.
- As explicações usam `git checkout`, mas o `git switch` que aprendeste no curso também funciona.
- Nos níveis de remotos, a branch `origin/main` aparece abreviada como `o/main`.
- O rebase interativo abre uma janela onde arrastas os commits, em vez de um editor de texto.
- O progresso fica guardado no browser. Se mudares de browser ou limpares os dados de navegação, recomeças do zero.

## Regras do desafio

1. **Não uses `show solution`.** Usa `hint`, `show goal`, o módulo correspondente e a [cheatsheet](../materiais/cheatsheet.md). Se ficares mesmo preso, pede ajuda a um colega antes de veres a solução.
2. Faz as etapas **pela ordem indicada aqui**, que acompanha os módulos do curso. A ordem do jogo é ligeiramente diferente.
3. Em cada nível, lê a explicação até ao fim. É lá que está a matéria nova.
4. Depois de resolver, tenta outra vez (`reset`) até igualares o número de comandos da solução do jogo.

## Etapas

Os identificadores servem para o comando `level`. O nome de cada nível aparece no jogo, na língua que escolheres.

### Etapa 1 · Preparar e desfazer

Faz depois do [módulo 04](../modulos/04-historico-e-desfazer/README.md). Estes dois níveis estão a meio do jogo: entra neles com `level move3` e `level move4`.

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `move3` | A área de preparação: `git add` e `git commit`, um ficheiro de cada vez |
| ☐ | `move4` | `git restore --staged` e `git restore` |

### Etapa 2 · Commits, branches e merge

Faz depois do [módulo 05](../modulos/05-branches-e-merge/README.md).

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `intro1` | `git commit` |
| ☐ | `intro2` | Criar uma branch e mudar para ela |
| ☐ | `intro3` | `git merge` |

### Etapa 3 · Andar pela árvore

Faz depois da etapa 2. Usa a matéria do [módulo 04](../modulos/04-historico-e-desfazer/README.md) sobre `HEAD`, `HEAD^`, `HEAD~2`, `reset` e `revert`.

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `rampup1` | Separar o `HEAD` da branch (*detached HEAD*) |
| ☐ | `rampup2` | Referências relativas com `^` |
| ☐ | `rampup3` | Referências relativas com `~`, e mover uma branch com `git branch -f` |
| ☐ | `rampup4` | `git reset` para commits locais, `git revert` para commits partilhados |

O `git branch -f <branch> <commit>` não aparece no curso. Obriga uma branch a apontar para outro commit, e o nível explica-o.

### Etapa 4 · Remotos

Faz depois do [módulo 06](../modulos/06-github-remotos/README.md). Estes níveis estão no separador de remotos da lista de níveis.

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `remote1` | `git clone` |
| ☐ | `remote2` | Branches de acompanhamento remoto (`o/main`) |
| ☐ | `remote3` | `git fetch` |
| ☐ | `remote4` | `git pull` |
| ☐ | `remote5` | Simular commits de colegas no remoto |
| ☐ | `remote6` | `git push` |

O `git fakeTeamwork` do nível `remote5` só existe no jogo. Serve para fazer de conta que um colega enviou commits.

### Etapa 5 · Reescrever e mover commits

Faz depois do [módulo 09](../modulos/09-ferramentas-avancadas/README.md).

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `intro4` | `git rebase` |
| ☐ | `move1` | `git cherry-pick` |
| ☐ | `move2` | Rebase interativo (`git rebase -i`) |
| ☐ | `mixed1` | Ficar só com um commit de vários |
| ☐ | `mixed2` | Corrigir um commit antigo com rebase interativo e `--amend` |
| ☐ | `mixed3` | O mesmo problema, resolvido com `cherry-pick` |
| ☐ | `mixed4` | `git tag` |
| ☐ | `mixed5` | `git describe` |
| ☐ | `remote7` | Push rejeitado por históricos divergentes: `fetch` e `rebase`, ou `pull --rebase` |
| ☐ | `remote8` | `main` protegida: mover o trabalho para uma branch e enviá-la |

### Etapa 6 · Bónus

Para quem quer ir além do curso. Estes níveis usam opções que raramente fazem falta no dia a dia, mas obrigam a perceber a fundo como as branches e os remotos funcionam.

| Feito | Nível | O que treinas |
|:-----:|-------|---------------|
| ☐ | `advanced1` | Vários rebases seguidos |
| ☐ | `advanced2` | Commits de merge com dois pais (`^2`) |
| ☐ | `advanced3` | Reorganizar várias branches emaranhadas |
| ☐ | `remoteAdvanced1` | Integrar várias branches com rebase e enviar |
| ☐ | `remoteAdvanced2` | O mesmo, com merge |
| ☐ | `remoteAdvanced3` | Ligar uma branch local a uma branch remota |
| ☐ | `remoteAdvanced4` | Argumentos do `git push` |
| ☐ | `remoteAdvanced5` | `git push origin <origem>:<destino>` |
| ☐ | `remoteAdvanced6` | Argumentos do `git fetch` |
| ☐ | `remoteAdvanced7` | Origem vazia: `git push origin :branch` |
| ☐ | `remoteAdvanced8` | Argumentos do `git pull` |

## Metas

| Meta | Etapas | Níveis |
|------|--------|:------:|
| 🥉 Bronze | 1 a 4 | 15 |
| 🥈 Prata | 1 a 5 | 25 |
| 🥇 Ouro | 1 a 6 | 36 |

A meta do curso é a **Prata**. O Ouro é opcional.

## Regista o teu progresso

Um desafio de Git regista-se com Git. No teu repositório de estudos:

1. Cria o ficheiro `apontamentos/learn-git-branching.md` e copia para lá as tabelas das etapas.
2. Sempre que fechares uma etapa, troca os `☐` por `☑`, acrescenta uma ou duas frases sobre o que aprendeste e faz um commit, por exemplo `Conclui etapa 2 do Learn Git Branching`.
3. No fim, o `git log --oneline -- apontamentos/learn-git-branching.md` mostra o teu percurso.

## Perguntas para pensar

Responde depois de fechar a etapa indicada.

<details>
<summary>Etapa 2 · No jogo, criar uma branch desenha só uma etiqueta nova no mesmo commit. O que é que isso te diz sobre o que é uma branch?</summary>

Uma branch é só um apontador para um commit. Criar uma branch não copia ficheiros nem commits, e é por isso que é instantâneo.

</details>

<details>
<summary>Etapa 3 · Fizeste commits com o HEAD separado e depois mudaste para a <code>main</code>. O que acontece a esses commits?</summary>

Ficam sem nenhuma branch a apontar para eles. Deixam de aparecer no `git log` e acabam por ser apagados pelo Git. Para os guardar, cria uma branch antes de sair: `git switch -c nome`.

</details>

<details>
<summary>Etapa 4 · Depois de um <code>git fetch</code>, o <code>o/main</code> avançou mas a tua <code>main</code> ficou no mesmo sítio. Porquê?</summary>

O `fetch` só descarrega os commits e atualiza as branches de acompanhamento remoto. Integrar na tua branch é outro passo (`git merge o/main`), que o `git pull` faz por ti.

</details>

<details>
<summary>Etapa 5 · Depois de um rebase, os commits copiados têm um nome novo (<code>C3'</code> em vez de <code>C3</code>). Que regra do curso é que isto explica?</summary>

A regra de ouro do rebase. Os commits recriados são commits diferentes, com outro hash. Se os antigos já tinham sido partilhados, o teu histórico e o dos teus colegas deixam de coincidir.

</details>

---

[Início](../README.md) · [Referências](../REFERENCIAS.md)
