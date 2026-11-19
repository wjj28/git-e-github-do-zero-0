# Erros comuns e como resolver

Antes de mais: lê a mensagem de erro até ao fim. O Git costuma dizer o que se passa e, muitas vezes, sugere a solução.

## `fatal: not a git repository`

**Causa:** estás numa pasta que não é um repositório.

**Solução:** confirma onde estás com `pwd` e entra na pasta certa com `cd`. Se o projeto ainda não é um repositório, `git init`.

## `Author identity unknown` / `Please tell me who you are`

**Causa:** o Git não tem o teu nome e email configurados.

**Solução:**

```bash
git config --global user.name "O Teu Nome"
git config --global user.email "o-teu-email@exemplo.com"
```

## `nothing to commit, working tree clean`

**Causa:** não há alterações para gravar. Não é um erro.

**Verifica:** guardaste o ficheiro no editor? Estás na pasta certa?

## `nothing added to commit but untracked files present`

**Causa:** há ficheiros novos, mas não fizeste `git add`.

**Solução:** `git add <ficheiro>` e repete o commit.

## Fiquei preso num ecrã estranho depois de `git commit`

**Causa:** fizeste `git commit` sem `-m` e abriu-se o editor Vim.

**Solução:** para sair sem gravar, carrega em `Esc`, escreve `:q!` e `Enter`. Para gravar a mensagem, `Esc`, `:wq`, `Enter`.

Para não voltar a acontecer:

```bash
git config --global core.editor "code --wait"
```

## Fiquei preso no `git log`

**Solução:** carrega em `q`.

## `error: failed to push some refs` / `rejected (fetch first)`

**Causa:** o remoto tem commits que tu não tens.

**Solução:**

```bash
git pull
# resolve conflitos, se houver
git push
```

Não uses `git push --force` para "resolver" isto.

## `fatal: refusing to merge unrelated histories`

**Causa:** criaste o repositório no GitHub com README ou licença, e o teu repositório local tem um histórico diferente.

**Solução:**

```bash
git pull origin main --allow-unrelated-histories
```

Para evitar: ao publicar um repositório local, cria o repositório no GitHub **vazio**.

## `fatal: remote origin already exists`

**Causa:** já existe um remoto chamado `origin`.

**Solução:** vê qual é com `git remote -v`. Para mudar o endereço:

```bash
git remote set-url origin <novo-url>
```

## `Authentication failed` / `Permission denied (publickey)`

**Causa:** problema de autenticação.

**Solução:**

- **HTTPS:** o GitHub não aceita a palavra-passe da conta. Usa o login pelo browser (Git Credential Manager) ou um *personal access token*.
- **SSH:** confirma que a chave pública está no GitHub e testa com `ssh -T git@github.com`.
- Confirma também que tens permissão de escrita no repositório. Se não for teu, precisas de um fork.

Vê o [módulo 06](../modulos/06-github-remotos/README.md#autenticação).

## `CONFLICT (content): Merge conflict in ...`

**Causa:** duas branches alteraram as mesmas linhas.

**Solução:** abre o ficheiro, escolhe o conteúdo final, apaga os marcadores `<<<<<<<`, `=======`, `>>>>>>>`, depois `git add` e `git commit`. Para desistir: `git merge --abort`.

Vê o [módulo 05](../modulos/05-branches-e-merge/README.md#conflitos).

## `error: Your local changes would be overwritten`

**Causa:** tens alterações por gravar que colidem com a operação (mudar de branch, pull, merge).

**Solução:** faz commit das alterações, ou guarda-as com `git stash` e recupera-as depois com `git stash pop`.

## Fiz commit na branch errada

Se ainda não fizeste push:

```bash
git switch -c branch-certa     # cria a branch certa com o commit incluído
git switch main
git reset --hard HEAD~1        # remove o commit da main
```

## Fiz commit de um ficheiro que não devia

Se ainda não fizeste push:

```bash
git rm --cached <ficheiro>
echo "<ficheiro>" >> .gitignore
git add .gitignore
git commit --amend --no-edit
```

Se o ficheiro tinha uma palavra-passe ou token e **já fizeste push**: troca imediatamente a credencial. Apagar o commit não chega, porque o segredo pode já ter sido copiado.

## `warning: LF will be replaced by CRLF`

**Causa:** diferença de fins de linha entre Windows e outros sistemas. É um aviso, não um erro.

**Solução:** no Windows, `git config --global core.autocrlf true`.

## `detached HEAD`

**Causa:** fizeste `git checkout` ou `git switch --detach` para um commit específico, em vez de uma branch.

**Solução:** para voltar, `git switch main`. Se fizeste commits nesse estado e queres mantê-los, cria uma branch antes de sair: `git switch -c nova-branch`.

## Apaguei commits sem querer

**Solução:** `git reflog` mostra por onde o `HEAD` passou. Encontra o hash do commit e cria uma branch nele:

```bash
git switch -c recuperado <hash>
```

## Mais ajuda

- [Dangit, Git!? (português)](https://dangitgit.com/pt_BR)
- [Dangit, Git!? (English)](https://dangitgit.com/en)
- `git help <comando>` abre a documentação oficial de qualquer comando.
