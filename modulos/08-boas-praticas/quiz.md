# Quiz · Módulo 08 · Boas práticas

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Qual é o melhor título de commit?

- A) `Corrigi cenas.`
- B) `update`
- C) `Corrige cálculo do total com valores vazios`
- D) `Alterei o ficheiro relatorio.py na linha 42 para verificar se o valor está vazio antes de somar`

<details>
<summary>Ver resposta</summary>

**C.** É curto, começa por um verbo e diz o que mudou. A opção D tem a informação certa, mas é longa demais para um título: o detalhe vai para o corpo.

</details>

### 2. O que deve explicar o corpo de uma mensagem de commit?

- A) O que cada linha alterada faz
- B) O porquê da alteração e o contexto
- C) O nome do autor
- D) A data

<details>
<summary>Ver resposta</summary>

**B.** O que mudou linha a linha vê-se no diff. Autor e data são registados pelo Git. O motivo só existe se o escreveres.

</details>

### 3. Em Conventional Commits, que prefixo usas para uma correção de erro?

- A) `feat`
- B) `docs`
- C) `chore`
- D) `fix`

<details>
<summary>Ver resposta</summary>

**D.** `feat` é para funcionalidades novas, `docs` para documentação e `chore` para manutenção.

</details>

### 4. O título do teu commit seria "Adiciona exportação para Excel e corrige erro no login". O que isto indica?

- A) Que provavelmente deviam ser dois commits
- B) Que o commit está bem feito
- C) Que falta um ponto final
- D) Que o título é curto demais

<details>
<summary>Ver resposta</summary>

**A.** Um commit, uma ideia. Se um dia for preciso reverter a exportação, o `revert` levava também a correção do login.

</details>

### 5. Que Markdown produz uma ligação?

- A) `(texto)[https://exemplo.com]`
- B) `[texto](https://exemplo.com)`
- C) `<texto: https://exemplo.com>`
- D) `![texto](https://exemplo.com)`

<details>
<summary>Ver resposta</summary>

**B.** Parênteses retos para o texto, curvos para o endereço. A opção D, com `!` no início, insere uma imagem.

</details>

### 6. Publicaste código no GitHub sem ficheiro de licença. Outra pessoa pode usá-lo legalmente no seu projeto?

- A) Sim, tudo o que é público é livre
- B) Sim, desde que indique o teu nome
- C) Não. Sem licença, ninguém tem autorização para o usar
- D) Só se o repositório tiver mais de 100 estrelas

<details>
<summary>Ver resposta</summary>

**C.** Público não significa livre. Sem licença aplicam-se os direitos de autor por omissão.

</details>

### 7. O teu script precisa de uma palavra-passe de email. Como organizas o repositório?

- A) Escreves a palavra-passe no código
- B) Fazes commit do `.env` num repositório privado
- C) Pões a palavra-passe no README
- D) O `.env` real fica no `.gitignore`, e fazes commit de um `.env.exemplo` com valores fictícios

<details>
<summary>Ver resposta</summary>

**D.** Quem clonar o projeto fica a saber que variáveis tem de preencher, sem ver os teus valores. Um repositório privado não chega: pode tornar-se público, ser clonado ou partilhado.

</details>

### 8. Para que serve o `README.md`?

- A) É a página de entrada do repositório: explica o que é o projeto e como usá-lo
- B) Guarda o histórico de commits
- C) Diz ao Git que ficheiros ignorar
- D) Define a licença

<details>
<summary>Ver resposta</summary>

**A.** O GitHub mostra-o automaticamente na página do repositório.

</details>

---

[← Voltar ao módulo 08](README.md) · Seguinte: [09 Ferramentas avançadas →](../09-ferramentas-avancadas/README.md)
