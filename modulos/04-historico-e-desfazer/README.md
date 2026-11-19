# Módulo 04 · Histórico e desfazer

## Objetivos

No fim deste módulo consegues:

- Ver exatamente o que mudou com `git diff`.
- Desfazer alterações em cada uma das três áreas.
- Ignorar ficheiros que não devem entrar no repositório.

Continua a trabalhar no repositório `meu-diario` do módulo anterior.

## Ver o que mudou

```bash
git diff              # alterações ainda não preparadas
git diff --staged     # alterações preparadas para o próximo commit
```

Linhas com `-` (a vermelho) foram removidas, linhas com `+` (a verde) foram adicionadas.

Ganha o hábito de correr `git diff --staged` antes de cada commit. É a tua última revisão.

## Explorar o histórico

```bash
git log --oneline            # um commit por linha
git log --oneline --graph    # com o desenho das branches
git log -3                   # só os últimos 3
git log -- README.md         # só commits que tocaram neste ficheiro
git show a1b2c3d             # detalhes de um commit específico
```

Não precisas do hash completo. Os primeiros 7 caracteres chegam.

`HEAD` é o nome que o Git dá ao commit onde estás neste momento. `HEAD~1` é o commit anterior, `HEAD~2` o anterior a esse.

## Desfazer: qual comando usar

| Situação | Comando |
|----------|---------|
| Alterei um ficheiro e quero deitar fora as alterações | `git restore ficheiro` |
| Fiz `git add` e quero retirar da área de preparação | `git restore --staged ficheiro` |
| Enganei-me na mensagem do último commit | `git commit --amend -m "Nova mensagem"` |
| Esqueci-me de um ficheiro no último commit | `git add ficheiro` e depois `git commit --amend --no-edit` |
| Quero desfazer o último commit mas manter as alterações | `git reset --soft HEAD~1` |
| Quero anular um commit que já partilhei | `git revert <hash>` |

### Deitar fora alterações não gravadas

```bash
git restore README.md
```

> **Atenção:** isto apaga as alterações que ainda não estavam em nenhum commit. Não há forma de as recuperar.

### Retirar da área de preparação

```bash
git restore --staged README.md
```

O ficheiro continua alterado na pasta de trabalho. Só deixa de estar marcado para o próximo commit.

### Corrigir o último commit

```bash
git commit --amend -m "Mensagem corrigida"
```

O `--amend` substitui o último commit por um novo. Usa-o só em commits que **ainda não enviaste** para o GitHub.

### `git reset`: voltar atrás no histórico

```bash
git reset --soft HEAD~1    # desfaz o commit, mantém as alterações preparadas
git reset --mixed HEAD~1   # desfaz o commit, mantém as alterações na pasta (é o modo por omissão)
git reset --hard HEAD~1    # desfaz o commit E apaga as alterações
```

> **Atenção:** `--hard` destrói trabalho. Antes de o usares, confirma com `git status` e `git log` que é mesmo isso que queres.

### `git revert`: desfazer sem apagar história

```bash
git revert a1b2c3d
```

O `revert` cria um **novo commit** que faz o inverso do commit indicado. O histórico fica intacto.

**Regra de ouro:** se o commit já está no GitHub e outras pessoas podem tê-lo, usa `revert`. O `reset` e o `--amend` reescrevem a história e só devem ser usados em commits locais.

## Ignorar ficheiros: `.gitignore`

Há ficheiros que nunca devem entrar no repositório:

- palavras-passe, tokens e chaves de API (ficheiros `.env`),
- ficheiros gerados automaticamente (`__pycache__/`, `node_modules/`),
- ficheiros do sistema ou do editor (`.DS_Store`, `Thumbs.db`),
- dados pesados ou pessoais.

Cria um ficheiro chamado `.gitignore` na raiz do repositório:

```gitignore
# Segredos
.env

# Python
__pycache__/
*.pyc
venv/

# Sistema
.DS_Store
Thumbs.db

# Relatórios gerados
saida/*.xlsx
```

Cada linha é um padrão. `*` significa "qualquer coisa" e uma barra no fim indica uma pasta.

O `.gitignore` é um ficheiro normal: adiciona-o e faz commit.

> **Nunca faças commit de palavras-passe ou tokens.** Em automação isto é crítico: um bot tem sempre credenciais. Se um segredo chegar ao GitHub, considera-o comprometido e troca-o, mesmo que apagues o commit a seguir.

Se um ficheiro já foi gravado antes de entrar no `.gitignore`, o Git continua a acompanhá-lo. Para deixar de o acompanhar sem o apagar do disco:

```bash
git rm --cached ficheiro
```

## Exercícios

1. Altera o `README.md`, vê a diferença com `git diff` e deita a alteração fora com `git restore`.
2. Altera dois ficheiros, faz `git add .` e depois retira um deles da área de preparação.
3. Faz um commit com um erro na mensagem e corrige-o com `--amend`.
4. Faz um commit, desfaz com `git reset --soft HEAD~1` e observa o `git status`. Repete com `--mixed`. Qual é a diferença?
5. Faz um commit que acrescenta uma linha e anula-o com `git revert`. Quantos commits novos aparecem no `git log`?
6. Cria `segredo.env` e um `.gitignore` que o ignore. Confirma com `git status` que o Git já não o vê.

## Checklist

- [ ] Uso `git diff --staged` antes de fazer commit.
- [ ] Sei desfazer alterações na pasta de trabalho e na área de preparação.
- [ ] Sei a diferença entre `reset` e `revert`.
- [ ] Tenho um `.gitignore` no meu repositório.

## Referências

**Português**

- [Pro Git: Desfazendo coisas](https://git-scm.com/book/pt-br/v2/Fundamentos-do-Git-Desfazendo-Coisas)
- [Pro Git: Vendo o histórico de commits](https://git-scm.com/book/pt-br/v2/Fundamentos-do-Git-Visualizando-o-Hist%C3%B3rico-de-Commits)
- [GitHub Docs: Ignorar ficheiros](https://docs.github.com/pt/get-started/git-basics/ignoring-files)

**English**

- [Pro Git: Undoing Things](https://git-scm.com/book/en/v2/Git-Basics-Undoing-Things)
- [Atlassian: Undoing commits and changes](https://www.atlassian.com/git/tutorials/undoing-changes)
- [github/gitignore: modelos de .gitignore](https://github.com/github/gitignore)

---

[← 03 Primeiro repositório](../03-primeiro-repositorio/README.md) · [Início](../../README.md) · Seguinte: [05 Branches e merge →](../05-branches-e-merge/README.md)
