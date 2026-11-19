# Jogos e prática interativa

Jogos e exercícios guiados, todos gratuitos, escolhidos para acompanhar os módulos do curso. Não substituem os exercícios de cada módulo: servem para repetir os mesmos comandos noutro contexto, até saírem sem pensar.

## Qual jogar em cada módulo

| Módulo | Jogo | Onde corre | Língua | Tempo |
|--------|------|------------|--------|-------|
| 02 Terminal básico | [Terminus](#terminus) | Browser | Inglês | 30 a 45 min |
| 03 Primeiro repositório | [Gitvana](#gitvana), ato 1 | Browser | Inglês | 30 min |
| 04 Histórico e desfazer | [Learn Git Branching](learn-git-branching.md), etapa 1 | Browser | Português | 15 min |
| 05 Branches e merge | [Learn Git Branching](learn-git-branching.md), etapas 2 e 3 · [Gitvana](#gitvana), ato 2 | Browser | Português · Inglês | 1 h |
| 06 GitHub e remotos | [Learn Git Branching](learn-git-branching.md), etapa 4 · [The Command Line Murders](#the-command-line-murders) | Browser · O teu terminal | Português · Inglês | 1h30 |
| 07 Colaboração | [GitHub Skills](#github-skills) | A tua conta GitHub | Inglês | 1 a 2 h |
| 08 Boas práticas | [Markdown Tutorial](#markdown-tutorial) | Browser | Português | 15 min |
| 09 Ferramentas avançadas | [Learn Git Branching](learn-git-branching.md), etapa 5 · [Gitvana](#gitvana), atos 3 e 4 · [Git Exercises](#git-exercises) | Browser · O teu terminal | Português · Inglês | 2 a 3 h |
| Depois do curso | [Oh My Git!](#oh-my-git) | Instala-se no computador | Inglês | Livre |

Os módulos 00 e 01 não têm jogo: são conceitos e instalação.

Quase todos estão em inglês. Não é um obstáculo: os comandos são os mesmos e o vocabulário está no [glossário](../materiais/glossario.md). Ler inglês técnico é, aliás, uma das competências que vais precisar.

## Os jogos

### Learn Git Branching

<https://learngitbranching.js.org/?locale=pt_BR>

O jogo principal do curso. Desenha a árvore de commits e mostra-a a mudar a cada comando. Tem roteiro próprio, com etapas e metas: [Desafio Learn Git Branching](learn-git-branching.md).

- **Encaixa em:** módulos 04, 05, 06 e 09.
- **Limite:** quase não tem ficheiros nem mensagens de commit. Treina a forma do histórico, não o trabalho do dia a dia.

### Gitvana

<https://gitvana.pixari.dev>

Um jogo de puzzles com 35 níveis em 6 atos. Ao contrário do Learn Git Branching, corre Git verdadeiro dentro do browser, com ficheiros, `git add` e mensagens de commit. Não pede conta e guarda o progresso no browser.

| Ato | Matéria | Quando jogar |
|-----|---------|--------------|
| 1 · Awakening | `init`, `add`, `commit`, `status`, `log`, `diff` | Depois do módulo 03 (o `diff` é do módulo 04) |
| 2 · The Middle Path | branches, merge, `cherry-pick`, `revert`, `stash` | Depois do módulo 05. Os níveis de `cherry-pick` e `stash` pedem o módulo 09 |
| 3 · Rewriting Reality | `rebase`, `--amend`, juntar commits, limpar segredos do histórico | Depois do módulo 09 |
| 4 · The Safety Net | `reflog`, `blame`, `bisect`, recuperação de desastres | Depois do módulo 09 |
| 5 e 6 | Técnicas avançadas e prova final | Opcional |

- **Encaixa em:** módulos 03, 04, 05 e 09. Complementa o Learn Git Branching, porque treina precisamente o que lhe falta.
- **Fora do curso:** `git blame` (quem alterou cada linha) e `git bisect` (encontrar o commit que introduziu um erro). O jogo explica-os.
- **Limite:** é um projeto recente, feito por uma só pessoa. Se algum nível se comportar de forma estranha, avança e regista o problema.

Exercícios:

1. Completa o ato 1 sem consultar o módulo. Quando ficares preso, aponta o comando que te faltou.
2. No fim de cada ato, escreve em `apontamentos/gitvana.md`, no teu repositório de estudos, os três comandos que mais usaste e para que servem. Faz um commit por ato.

### Terminus

<https://web.mit.edu/mprat/Public/web/Terminus/Web/main.html>

Uma aventura de texto criada no MIT. Andas por um mundo de fantasia onde cada sítio é uma pasta e cada objeto é um ficheiro: entras numa sala com `cd`, olhas à volta com `ls`.

- **Encaixa em:** módulo 02. É a melhor forma de ganhar o reflexo de `ls`, `cd` e `pwd`.
- **Diferença:** para ler um ficheiro, o jogo usa `less` em vez do `cat` do curso. O `less` mostra o conteúdo num ecrã de leitura, do qual sais com `q`.
- **Limite:** não guarda o progresso de forma fiável. Joga de uma vez.

Exercícios:

1. Joga até saíres da primeira zona. Que comandos usaste que não estão no módulo 02?
2. Desenha num papel o mapa dos sítios por onde passaste, como uma árvore de pastas.
3. Explica a diferença entre `cat` e `less`. Quando é que cada um dá mais jeito?

### The Command Line Murders

<https://github.com/veltman/clmystery>

Um mistério policial que se resolve no terminal. Recebes uma pasta cheia de ficheiros com pistas, moradas e depoimentos, e tens de encontrar o culpado usando só comandos.

- **Encaixa em:** módulo 06, porque começa com um `git clone`. É também uma revisão do módulo 02.
- **Vai além do curso:** precisas de comandos de pesquisa em texto, como `grep` e `head`. O jogo traz uma cheatsheet e ficheiros de pistas.
- **Limite:** não se joga no browser. Corre no teu terminal (no Windows, o Git Bash).

Exercícios:

1. Clona o repositório e lê as instruções:

   ```bash
   cd ~/curso-git
   git clone https://github.com/veltman/clmystery.git
   cd clmystery
   cat instructions
   ```

2. Corre `git log --oneline` e `git remote -v`. O que ficas a saber sobre o repositório sem teres feito `git init`?
3. Resolve o mistério. Guarda os comandos que usaste num ficheiro `notas.txt`.
4. Corre `git status`. O que diz o Git sobre o teu `notas.txt`?

### GitHub Skills

<https://skills.github.com>

Os cursos práticos oficiais do GitHub. Não são jogos, mas funcionam como tal: copias um repositório para a tua conta e um robô vai-te dando tarefas e verificando o que fazes, em issues e pull requests verdadeiros.

| Curso | Matéria | Módulo | Tempo |
|-------|---------|--------|-------|
| [Introduction to GitHub](https://github.com/skills/introduction-to-github) | Branch, commit, pull request e merge, tudo pelo site | 07 | Menos de 1 h |
| [Review pull requests](https://github.com/skills/review-pull-requests) | Rever, sugerir alterações e integrar | 07 | Menos de 30 min |
| [Resolve merge conflicts](https://github.com/skills/resolve-merge-conflicts) | Resolver um conflito no editor do site | 07 (matéria do 05) | Menos de 30 min |
| [Communicate using Markdown](https://github.com/skills/communicate-using-markdown) | Títulos, imagens, código e listas de tarefas | 08 | Menos de 1 h |
| [Create a release based workflow](https://github.com/skills/release-based-workflow) | Versões, releases e correções urgentes | 09 | Menos de 1 h |

- **Encaixa em:** módulos 07, 08 e 09. É a única prática desta lista feita no GitHub verdadeiro.
- **Limite:** precisas de conta no GitHub (módulo 01). Os repositórios ficam no teu perfil. No fim, podes apagá-los ou torná-los privados.

Exercícios:

1. Faz o *Introduction to GitHub*. Em que passo é que o robô abriu a issue seguinte? O que o desencadeou?
2. Faz o *Review pull requests* e deixa pelo menos uma sugestão de alteração (*suggestion*).
3. Faz o *Resolve merge conflicts*. Compara com o conflito que resolveste no terminal no módulo 05: que passos são iguais?

### Markdown Tutorial

<https://www.markdowntutorial.com/pt-br>

Sete lições curtas, em português, com exercícios que se corrigem sozinhos enquanto escreves.

- **Encaixa em:** módulo 08, na secção "Markdown em 5 minutos".
- **Alternativa em inglês:** o [tutorial do CommonMark](https://commonmark.org/help/tutorial/), no mesmo formato.

Exercícios:

1. Completa as sete lições.
2. Sem consultar, escreve no README do teu `meu-diario` um título, uma lista, uma ligação, uma imagem e um bloco de código.

### Git Exercises

<https://gitexercises.fracz.com>

Uma série de exercícios feitos no teu terminal, com Git verdadeiro. Clonas um repositório, resolves cada exercício com commits e envias para seres avaliado. As instruções para começar estão na página inicial.

- **Encaixa em:** módulo 09. Os exercícios cobrem `--amend`, conflitos, `stash`, `rebase`, `cherry-pick` e rebase interativo.
- **Limite:** é mais árido do que os outros. Vale para quem já fez a etapa 5 do Learn Git Branching e quer repetir com ficheiros a sério.

Exercícios:

1. Resolve os primeiros cinco exercícios.
2. Escolhe o exercício que te deu mais trabalho e explica a solução, por palavras tuas, no teu repositório de estudos.

### Oh My Git!

<https://ohmygit.org>

Um jogo de código aberto em que cada comando Git é uma carta. Mostra o repositório por dentro em tempo real e tem um terminal integrado com Git verdadeiro. Descarrega-se para Windows, macOS e Linux.

- **Encaixa em:** revisão geral depois do curso. Cobre do primeiro commit aos remotos.
- **Limite:** exige instalação e está em inglês. Existe uma [tradução para português do Brasil](https://github.com/d3cryptofc/oh-my-git-ptbr), feita pela comunidade e ainda incompleta.

## O que ficou de fora

| Recurso | Porquê |
|---------|--------|
| [Githug](https://github.com/Gazler/githug) | Exige instalar Ruby numa versão antiga. É uma barreira grande para quem está a começar |
| [Visualizing Git](https://git-school.github.io/visualizing-git/) | Não é um jogo: é uma área livre, sem objetivos. Continua nas [referências](../REFERENCIAS.md) como ferramenta para experimentar |
| Command Line Heroes: BASH | Jogo de velocidade para quem já sabe muitos comandos. Não ensina |

---

[Início](../README.md) · [Referências](../REFERENCIAS.md)
