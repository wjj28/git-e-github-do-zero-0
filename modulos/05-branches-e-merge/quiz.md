# Quiz · Módulo 05 · Branches e merge

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Que comando cria a branch `corrige-login` e muda logo para ela?

- A) `git branch corrige-login`
- B) `git switch corrige-login`
- C) `git switch -c corrige-login`
- D) `git merge corrige-login`

<details>
<summary>Ver resposta</summary>

**C.** O `git branch corrige-login` cria a branch, mas deixa-te onde estavas. Em tutoriais antigos vais ver `git checkout -b corrige-login`, que faz o mesmo.

</details>

### 2. Criaste `objetivos.txt` numa branch, fizeste commit e voltaste à `main`. O ficheiro desapareceu da pasta. Porquê?

- A) O Git apagou-o
- B) O ficheiro existe na outra branch, e o Git ajusta a pasta à branch onde estás
- C) Faltou fazer `git push`
- D) É um erro do Git

<details>
<summary>Ver resposta</summary>

**B.** Volta à branch e o ficheiro reaparece. Nada se perdeu.

</details>

### 3. Queres trazer o trabalho de `nova-pagina` para a `main`. Qual é a sequência certa?

- A) `git switch nova-pagina` e depois `git merge main`
- B) `git merge main nova-pagina`
- C) `git switch main` e depois `git branch -d nova-pagina`
- D) `git switch main` e depois `git merge nova-pagina`

<details>
<summary>Ver resposta</summary>

**D.** O merge faz-se a partir da branch que recebe. A opção A faz o contrário: traz a `main` para dentro de `nova-pagina`.

</details>

### 4. Quando é que um merge é *fast-forward*?

- A) Quando a branch que recebe não teve commits novos desde que a outra foi criada
- B) Quando as duas branches têm commits novos
- C) Quando há conflitos
- D) Quando a branch tem um só commit

<details>
<summary>Ver resposta</summary>

**A.** Nesse caso o Git só avança o apontador da branch e não cria commit de merge.

</details>

### 5. Quando acontece um conflito de merge?

- A) Sempre que duas branches alteram o mesmo ficheiro
- B) Quando as duas branches alteram as mesmas linhas do mesmo ficheiro
- C) Quando a branch é muito antiga
- D) Quando duas pessoas fazem commit no mesmo dia

<details>
<summary>Ver resposta</summary>

**B.** Alterações em zonas diferentes do mesmo ficheiro são juntas automaticamente. O conflito só aparece quando o Git tem de escolher entre duas versões da mesma zona.

</details>

### 6. Estás na `main` e fizeste `git merge muda-cor`. O que representa cada parte?

```text
<<<<<<< HEAD
Cor favorita: vermelho
=======
Cor favorita: verde
>>>>>>> muda-cor
```

- A) "vermelho" é a versão de `muda-cor`, "verde" é a versão da `main`
- B) As duas linhas são da `main`
- C) "vermelho" é a versão da `main`, "verde" é a versão de `muda-cor`
- D) "vermelho" é a versão antiga, "verde" é a versão certa

<details>
<summary>Ver resposta</summary>

**C.** A parte de cima (`HEAD`) é a branch onde estás. A de baixo é a branch que estás a juntar. O Git não sabe qual é a "certa": essa decisão é tua.

</details>

### 7. Editaste o ficheiro e apagaste os marcadores. O que falta para concluir o merge?

- A) `git merge --continue --force`
- B) Nada, o merge conclui-se sozinho
- C) `git merge --abort`
- D) `git add` do ficheiro e depois `git commit`

<details>
<summary>Ver resposta</summary>

**D.** O `git add` diz ao Git que o conflito está resolvido, e o `git commit` grava o commit de merge. O `--abort` serve para desistir.

</details>

### 8. Tentas apagar com `git branch -d experiencia` uma branch que nunca foi integrada. O que acontece?

- A) O Git recusa e avisa que a branch não está totalmente integrada
- B) A branch é apagada sem aviso
- C) O Git faz o merge e depois apaga
- D) O repositório fica corrompido

<details>
<summary>Ver resposta</summary>

**A.** É uma proteção contra perda de trabalho. O Git sugere `-D` (maiúsculo) para forçar, se tiveres a certeza.

</details>

### 9. Porque é que `git commit -am "..."` não inclui um ficheiro acabado de criar?

- A) Porque o `-a` só inclui ficheiros que o Git já acompanha
- B) Porque o ficheiro está no `.gitignore`
- C) Porque é preciso `-m` primeiro
- D) Inclui sempre

<details>
<summary>Ver resposta</summary>

**A.** Um ficheiro novo está *untracked* e precisa de um `git add` explícito na primeira vez.

</details>

---

Agora treina com as mãos: faz a **Etapa 2** do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md).

[← Voltar ao módulo 05](README.md) · Seguinte: [06 GitHub e repositórios remotos →](../06-github-remotos/README.md)
