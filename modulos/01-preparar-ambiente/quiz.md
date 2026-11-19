# Quiz · Módulo 01 · Preparar o ambiente

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Que comando confirma que o Git está instalado?

- A) `git install`
- B) `git --version`
- C) `git start`
- D) `git check`

<details>
<summary>Ver resposta</summary>

**B.** Mostra algo como `git version 2.52.0`. Se aparecer "command not found", o Git não está instalado ou o terminal precisa de ser reaberto.

</details>

### 2. Para que servem `user.name` e `user.email`?

- A) Para entrar na conta do GitHub
- B) Para o Git assinar cada commit com o autor
- C) Para criar a conta no GitHub
- D) Para escolher o nome do repositório

<details>
<summary>Ver resposta</summary>

**B.** São a assinatura dos commits. Não são credenciais: a autenticação no GitHub trata-se à parte, no módulo 06.

</details>

### 3. O que faz a opção `--global` no `git config`?

- A) Aplica a configuração a todos os utilizadores do computador
- B) Publica a configuração no GitHub
- C) Aplica a configuração a todos os repositórios do teu utilizador
- D) Aplica a configuração só ao repositório atual

<details>
<summary>Ver resposta</summary>

**C.** Sem `--global`, a configuração vale apenas para o repositório onde estás.

</details>

### 4. Porque deves usar no Git o mesmo email da conta GitHub?

- A) Porque o Git não funciona com outro email
- B) Para os commits ficarem associados ao teu perfil
- C) Para receberes notificações
- D) Porque o GitHub apaga commits com outro email

<details>
<summary>Ver resposta</summary>

**B.** O GitHub liga os commits ao perfil através do email. Com outro email, os commits aparecem sem a tua fotografia e não contam no teu gráfico de contribuições.

</details>

### 5. Não queres expor o teu email pessoal nos commits. O que fazes?

- A) Deixas o `user.email` vazio
- B) Inventas um email qualquer
- C) Ativas *Keep my email addresses private* no GitHub e usas o endereço `...@users.noreply.github.com`
- D) Não há solução, o email é sempre público

<details>
<summary>Ver resposta</summary>

**C.** O endereço `noreply` mantém os commits associados ao teu perfil sem revelar o email verdadeiro.

</details>

### 6. O que faz `git config --global init.defaultBranch main`?

- A) Muda o nome da branch em todos os repositórios existentes
- B) Faz com que a primeira branch de cada repositório novo se chame `main`
- C) Cria uma branch chamada `main` no repositório atual
- D) Apaga a branch `master`

<details>
<summary>Ver resposta</summary>

**B.** Só afeta repositórios criados a partir desse momento com `git init`.

</details>

### 7. Corres `git config --global user.name`, sem valor à frente. O que acontece?

- A) Apaga o nome configurado
- B) Dá erro
- C) Pede-te para escrever um nome
- D) Mostra o nome que está configurado

<details>
<summary>Ver resposta</summary>

**D.** Sem valor, o `git config` lê em vez de escrever. É uma forma rápida de confirmar uma configuração.

</details>

---

[← Voltar ao módulo 01](README.md) · Seguinte: [02 Terminal básico →](../02-terminal-basico/README.md)
