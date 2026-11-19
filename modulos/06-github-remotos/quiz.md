# Quiz · Módulo 06 · GitHub e repositórios remotos

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. O que é `origin`?

- A) O nome da branch principal
- B) O primeiro commit do repositório
- C) O nome dado, por convenção, ao remoto principal
- D) Um comando do Git

<details>
<summary>Ver resposta</summary>

**C.** É só um nome. O `git clone` cria-o automaticamente e podes ver para onde aponta com `git remote -v`.

</details>

### 2. Para que serve o `-u` em `git push -u origin main`?

- A) Liga a branch local à branch do remoto, para depois bastar `git push`
- B) Força o envio
- C) Envia todas as branches
- D) Atualiza o Git

<details>
<summary>Ver resposta</summary>

**A.** Só é preciso na primeira vez que publicas cada branch.

</details>

### 3. Ao publicar um repositório local que já tem commits, porque deves criar o repositório do GitHub vazio (sem README nem licença)?

- A) Porque o GitHub não permite README em repositórios novos
- B) Porque o remoto ficaria com um commit que o teu repositório local não tem, e o primeiro `push` seria rejeitado
- C) Porque o README ocupa muito espaço
- D) Porque um README torna o repositório público

<details>
<summary>Ver resposta</summary>

**B.** Dois históricos que começaram separados não encaixam. Um remoto vazio aceita o teu histórico tal como está.

</details>

### 4. Qual é a diferença entre `git fetch` e `git pull`?

- A) Nenhuma
- B) O `fetch` envia, o `pull` recebe
- C) O `pull` só descarrega, o `fetch` descarrega e integra
- D) O `fetch` só descarrega as novidades, o `pull` descarrega e integra na tua branch

<details>
<summary>Ver resposta</summary>

**D.** `pull` = `fetch` + `merge`. O `fetch` atualiza `origin/main`, mas não mexe na tua `main` nem nos teus ficheiros.

</details>

### 5. O `git push` foi rejeitado porque o remoto tem commits que tu não tens. O que fazes?

- A) `git push --force`
- B) `git pull`, resolves conflitos se houver, e `git push` outra vez
- C) Apagas o repositório e clonas de novo
- D) `git init`

<details>
<summary>Ver resposta</summary>

**B.** O `--force` apagava do remoto os commits dos teus colegas.

</details>

### 6. O GitHub aceita a palavra-passe da conta num `git push` por HTTPS?

- A) Sim, sempre
- B) Só em repositórios privados
- C) Não. É preciso um token, o Git Credential Manager, o GitHub CLI ou SSH
- D) Só com autenticação de dois fatores desligada

<details>
<summary>Ver resposta</summary>

**C.** A palavra-passe serve para entrar no site. As operações Git exigem um dos outros métodos.

</details>

### 7. Geraste um par de chaves SSH. Qual delas colas no GitHub?

- A) A privada (`id_ed25519`)
- B) A pública (`id_ed25519.pub`)
- C) As duas
- D) Nenhuma, o GitHub gera as suas

<details>
<summary>Ver resposta</summary>

**B.** A chave privada nunca sai do teu computador. Se a partilhares, qualquer pessoa pode fazer-se passar por ti.

</details>

### 8. Depois de um `git clone`, o que tens de fazer antes de começar a trabalhar?

- A) `git init`
- B) `git remote add origin <url>`
- C) Os dois comandos anteriores
- D) Só entrar na pasta com `cd`

<details>
<summary>Ver resposta</summary>

**D.** O `clone` já traz o histórico completo e já configura o `origin`.

</details>

### 9. O que representa `origin/main` no teu computador?

- A) A posição da `main` do remoto, tal como estava da última vez que comunicaste com ele
- B) A `main` do GitHub, sempre atualizada ao segundo
- C) Uma cópia de segurança da tua `main`
- D) Uma branch onde podes fazer commits

<details>
<summary>Ver resposta</summary>

**A.** Só se atualiza com `fetch`, `pull` ou `push`. Se um colega enviar commits agora, o teu `origin/main` não muda até fazeres `git fetch`.

</details>

---

Agora treina com as mãos: faz a **Etapa 4** do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md).

[← Voltar ao módulo 06](README.md) · Seguinte: [07 Colaboração →](../07-colaboracao/README.md)
