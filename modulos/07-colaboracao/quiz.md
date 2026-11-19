# Quiz · Módulo 07 · Colaboração

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. No GitHub Flow, onde se faz o trabalho novo?

- A) Diretamente na `main`
- B) Numa branch criada a partir da `main`, uma por tarefa
- C) Num repositório novo
- D) Numa tag

<details>
<summary>Ver resposta</summary>

**B.** A `main` mantém-se estável. O trabalho entra nela por pull request, depois de revisto.

</details>

### 2. O que é um pull request?

- A) Um pedido para integrar uma branch noutra, com espaço para discussão e revisão
- B) O mesmo que `git pull`
- C) Um pedido de acesso a um repositório privado
- D) Uma cópia de um repositório na tua conta

<details>
<summary>Ver resposta</summary>

**A.** Apesar do nome parecido, não tem relação com o comando `git pull`. A opção D descreve um fork.

</details>

### 3. A revisão do teu PR pediu alterações. Como atualizas o PR?

- A) Fechas o PR e abres outro
- B) Envias as alterações por email
- C) Fazes mais commits na mesma branch e `git push`
- D) Fazes commit diretamente na `main`

<details>
<summary>Ver resposta</summary>

**C.** O PR acompanha a branch. Cada `push` novo aparece lá automaticamente.

</details>

### 4. O que acontece quando um PR com `Closes #12` na descrição é integrado?

- A) O PR número 12 é fechado
- B) A issue número 12 é fechada automaticamente
- C) São apagados 12 commits
- D) Nada, é só um comentário

<details>
<summary>Ver resposta</summary>

**B.** Também funcionam `Fixes #12` e `Resolves #12`.

</details>

### 5. Queres contribuir para um projeto público onde não tens permissão de escrita. Qual é o caminho?

- A) Clonar o original e fazer `git push`
- B) Pedir a palavra-passe ao dono
- C) Fazer `git push --force`
- D) Fork, clonar o teu fork, branch, commits, push para o fork e pull request para o original

<details>
<summary>Ver resposta</summary>

**D.** O `push` para o original seria recusado. O fork é a tua cópia, onde tens permissão de escrita.

</details>

### 6. Num fork, o que são `origin` e `upstream`?

- A) `origin` é o repositório original, `upstream` é o teu fork
- B) São dois nomes para o mesmo remoto
- C) `origin` é o teu fork, `upstream` é o repositório original
- D) `upstream` é a branch principal

<details>
<summary>Ver resposta</summary>

**C.** Clonaste o teu fork, por isso é ele o `origin`. O `upstream` adiciona-se à mão com `git remote add upstream <url>`.

</details>

### 7. Qual destes comentários de revisão é o mais útil?

- A) "Isto está mal."
- B) "Não percebes nada disto."
- C) "Se a lista vier vazia, esta linha dá erro. O que achas de verificar antes?"
- D) "👍"

<details>
<summary>Ver resposta</summary>

**C.** Aponta o problema concreto, explica a razão e propõe um caminho. Comenta o código, não a pessoa.

</details>

### 8. O que deve ter uma boa issue de erro?

- A) Só o título "Não funciona"
- B) O que esperavas, o que aconteceu e os passos para reproduzir
- C) O código inteiro do projeto
- D) Uma captura de ecrã sem texto

<details>
<summary>Ver resposta</summary>

**B.** Quem vai resolver precisa de conseguir reproduzir o erro no seu computador.

</details>

### 9. O teu PR foi integrado no GitHub. O que fazes no teu computador?

- A) Nada
- B) `git switch main`, `git pull` e `git branch -d` da branch
- C) Apagas a pasta e clonas outra vez
- D) `git push --force`

<details>
<summary>Ver resposta</summary>

**B.** Atualizas a tua `main` com o que foi integrado e apagas a branch local, que já cumpriu a sua função.

</details>

---

[← Voltar ao módulo 07](README.md) · Seguinte: [08 Boas práticas →](../08-boas-praticas/README.md)
