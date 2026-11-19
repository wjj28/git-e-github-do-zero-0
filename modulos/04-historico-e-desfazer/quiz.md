# Quiz · Módulo 04 · Histórico e desfazer

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Fizeste `git add` de um ficheiro. Que comando mostra o que vai entrar no commit?

- A) `git diff`
- B) `git diff --staged`
- C) `git log`
- D) `git show`

<details>
<summary>Ver resposta</summary>

**B.** O `git diff` sem opções só mostra o que **ainda não** foi preparado. Depois de um `git add` de tudo, fica vazio.

</details>

### 2. O que é `HEAD~2`?

- A) O segundo commit do repositório
- B) O commit seguinte ao atual
- C) O commit que está dois passos atrás do atual
- D) A segunda branch

<details>
<summary>Ver resposta</summary>

**C.** `HEAD` é o commit onde estás, `HEAD~1` (ou `HEAD^`) é o anterior e `HEAD~2` é o anterior a esse.

</details>

### 3. Fizeste `git add .` e incluíste um ficheiro por engano. Como o retiras sem perder as alterações?

- A) `git restore ficheiro`
- B) `git rm ficheiro`
- C) `git reset --hard`
- D) `git restore --staged ficheiro`

<details>
<summary>Ver resposta</summary>

**D.** Com `--staged`, o ficheiro sai da área de preparação e continua alterado na pasta. Sem `--staged`, o `git restore` deitava fora as alterações.

</details>

### 4. Qual destes comandos destrói alterações que não estão em nenhum commit?

- A) `git reset --soft HEAD~1`
- B) `git restore --staged ficheiro`
- C) `git restore ficheiro`
- D) `git revert <hash>`

<details>
<summary>Ver resposta</summary>

**C.** Repõe o ficheiro como estava e as alterações não gravadas não se recuperam. O `git reset --hard` faz o mesmo a todos os ficheiros.

</details>

### 5. Depois de `git reset --soft HEAD~1`, onde ficam as alterações do commit desfeito?

- A) Na área de preparação, prontas para um novo commit
- B) Na pasta de trabalho, por preparar
- C) São apagadas
- D) Num stash

<details>
<summary>Ver resposta</summary>

**A.** Com `--mixed` (o modo por omissão) ficariam na pasta de trabalho, por preparar. Com `--hard` seriam apagadas.

</details>

### 6. Um commit com um erro já está no GitHub e os teus colegas já o descarregaram. Como o anulas?

- A) `git reset --hard HEAD~1`
- B) `git commit --amend`
- C) `git revert <hash>`
- D) Apagando a pasta `.git`

<details>
<summary>Ver resposta</summary>

**C.** O `revert` cria um commit novo que faz o inverso e não toca no histórico. O `reset` e o `--amend` reescrevem a história, o que cria problemas a quem já tem o commit.

</details>

### 7. Acrescentaste `config.env` ao `.gitignore`, mas o ficheiro já tinha sido gravado num commit antigo. O que acontece?

- A) O Git deixa de o acompanhar automaticamente
- B) O Git continua a acompanhá-lo, até fazeres `git rm --cached config.env`
- C) O ficheiro é apagado do disco
- D) O `.gitignore` dá erro

<details>
<summary>Ver resposta</summary>

**B.** O `.gitignore` só afeta ficheiros que o Git ainda não acompanha. E atenção: o segredo continua nos commits antigos, por isso tem de ser trocado.

</details>

### 8. Enviaste por engano um token para o GitHub. Qual é a primeira coisa a fazer?

- A) Apagar o commit e esperar que ninguém tenha visto
- B) Tornar o repositório privado
- C) Acrescentar o ficheiro ao `.gitignore`
- D) Revogar o token e gerar um novo

<details>
<summary>Ver resposta</summary>

**D.** Um segredo que chegou ao GitHub está comprometido. Limpar o repositório vem depois e não substitui a troca do segredo.

</details>

### 9. Quando é seguro usar `git commit --amend`?

- A) Sempre
- B) Só em commits que ainda não enviaste para o remoto
- C) Só na branch `main`
- D) Só em commits com mais de um dia

<details>
<summary>Ver resposta</summary>

**B.** O `--amend` substitui o commit por um novo, com outro hash. Se o antigo já foi partilhado, os históricos deixam de coincidir.

</details>

---

Agora treina com as mãos: faz a **Etapa 1** do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md).

[← Voltar ao módulo 04](README.md) · Seguinte: [05 Branches e merge →](../05-branches-e-merge/README.md)
