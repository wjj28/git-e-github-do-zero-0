# Quiz · Módulo 09 · Ferramentas avançadas

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Estás a meio de uma alteração e precisas de mudar de branch para uma urgência. O trabalho não está pronto para um commit. O que usas?

- A) `git reset --hard`
- B) `git stash`
- C) `git revert`
- D) `git tag`

<details>
<summary>Ver resposta</summary>

**B.** O `stash` guarda as alterações de lado e limpa a pasta. Quando voltares, recuperas com `git stash pop`.

</details>

### 2. Qual é a diferença entre `git stash pop` e `git stash apply`?

- A) Nenhuma
- B) O `pop` apaga as alterações sem as recuperar
- C) O `pop` recupera e remove da lista, o `apply` recupera e mantém na lista
- D) O `apply` só funciona noutra branch

<details>
<summary>Ver resposta</summary>

**C.** Para apagar sem recuperar usa-se `git stash drop`.

</details>

### 3. Criaste a tag `v1.0.0` e fizeste `git push`. A tag está no GitHub?

- A) Sim, as tags vão sempre com os commits
- B) Não. As tags enviam-se à parte, com `git push origin v1.0.0` ou `--tags`
- C) Só se a tag tiver mensagem
- D) Só se estiveres na `main`

<details>
<summary>Ver resposta</summary>

**B.** O `git push` normal só envia commits de branches.

</details>

### 4. A versão atual é `1.4.2`. Corrigiste um erro, sem funcionalidades novas. Qual é a versão seguinte?

- A) `2.0.0`
- B) `1.5.0`
- C) `1.4.3`
- D) `1.4.2-fix`

<details>
<summary>Ver resposta</summary>

**C.** Correções sobem o último número. Funcionalidades novas e compatíveis dariam `1.5.0`. Alterações que partem a compatibilidade dariam `2.0.0`.

</details>

### 5. O que acontece aos commits da tua branch depois de `git rebase main`?

- A) Ficam iguais, com os mesmos hashes
- B) São apagados
- C) São juntos num só commit
- D) São recriados em cima da `main`, com o mesmo conteúdo e hashes novos

<details>
<summary>Ver resposta</summary>

**D.** É por isso que se diz que o rebase reescreve a história: os commits antigos são substituídos por cópias.

</details>

### 6. Qual é a regra de ouro do rebase?

- A) Nunca fazer rebase de commits que já partilhaste e que outras pessoas podem estar a usar
- B) Fazer sempre rebase antes de um commit
- C) Nunca usar rebase
- D) Fazer rebase só na `main`

<details>
<summary>Ver resposta</summary>

**A.** Nas tuas branches locais, ou em branches onde trabalhas sozinho, o rebase é seguro.

</details>

### 7. Uma correção urgente está num commit da branch `desenvolvimento`, no meio de outro trabalho que ainda não está pronto. Como a levas para a `main`?

- A) `git merge desenvolvimento`
- B) `git cherry-pick <hash>`, a partir da `main`
- C) `git rebase desenvolvimento`
- D) `git stash`

<details>
<summary>Ver resposta</summary>

**B.** O `cherry-pick` copia só o commit indicado. O merge e o rebase trariam todo o trabalho por acabar.

</details>

### 8. Fizeste `git reset --hard HEAD~1` e arrependeste-te. O commit ainda se recupera?

- A) Não, o `--hard` é definitivo
- B) Só se tiveres feito `git stash` antes
- C) Sim: encontras o hash com `git reflog` e crias uma branch nesse commit
- D) Só com um programa de recuperação de ficheiros

<details>
<summary>Ver resposta</summary>

**C.** O que esteve num commit quase sempre se recupera. O que o `--hard` destrói de vez são as alterações que nunca chegaram a um commit.

</details>

### 9. Numa lista de `git rebase -i`, o que faz trocar `pick` por `squash` numa linha?

- A) Apaga esse commit
- B) Muda só a mensagem desse commit
- C) Passa o commit para outra branch
- D) Junta esse commit ao commit da linha de cima

<details>
<summary>Ver resposta</summary>

**D.** Para apagar usa-se `drop`, e para mudar só a mensagem usa-se `reword`.

</details>

---

Agora treina com as mãos: faz a **Etapa 5** do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md).

[← Voltar ao módulo 09](README.md) · Seguinte: [10 Projeto final →](../10-projeto-final/README.md)
