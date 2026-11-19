# Quiz · Módulo 03 · Primeiro repositório

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. O que faz o `git init`?

- A) Cria um repositório no GitHub
- B) Transforma a pasta atual num repositório, criando a pasta oculta `.git`
- C) Faz o primeiro commit
- D) Instala o Git

<details>
<summary>Ver resposta</summary>

**B.** O `git init` é local. Não cria nada no GitHub nem grava nenhum commit.

</details>

### 2. Quais são as três áreas do Git, pela ordem em que uma alteração as percorre?

- A) Repositório → área de preparação → pasta de trabalho
- B) Pasta de trabalho → repositório → área de preparação
- C) Pasta de trabalho → área de preparação → repositório
- D) Área de preparação → pasta de trabalho → repositório

<details>
<summary>Ver resposta</summary>

**C.** Editas na pasta de trabalho, escolhes com `git add` (área de preparação) e gravas com `git commit` (repositório).

</details>

### 3. Criaste `tarefas.txt` e ainda não fizeste `git add`. Como aparece no `git status`?

- A) *modified*
- B) *untracked*
- C) *staged*
- D) Não aparece

<details>
<summary>Ver resposta</summary>

**B.** *Untracked* significa que o ficheiro existe na pasta, mas o Git ainda não o acompanha. *Modified* é para ficheiros que o Git já conhece.

</details>

### 4. Alteraste cinco ficheiros, mas só dois fazem parte da correção que queres gravar. O que fazes?

- A) `git add .` e depois `git commit`
- B) `git commit -m "..."` diretamente
- C) Apagas os outros três ficheiros
- D) `git add` só dos dois ficheiros e depois `git commit`

<details>
<summary>Ver resposta</summary>

**D.** É para isto que existe a área de preparação: escolher o que entra em cada commit.

</details>

### 5. Fizeste `git add README.md` e depois alteraste outra vez o `README.md`. O que entra no commit seguinte?

- A) A versão do ficheiro no momento do `git add`
- B) A versão mais recente do ficheiro
- C) Nada, o Git dá erro
- D) As duas versões, em dois commits

<details>
<summary>Ver resposta</summary>

**A.** O `git add` prepara o conteúdo tal como está nesse instante. Para incluir a alteração nova, tens de fazer `git add` outra vez. O `git status` mostra o ficheiro nas duas listas.

</details>

### 6. Qual é a melhor mensagem de commit?

- A) `alterações`
- B) `fix`
- C) `Corrige data errada no dia 2`
- D) `commit final`

<details>
<summary>Ver resposta</summary>

**C.** Diz o que mudou sem ser preciso abrir os ficheiros.

</details>

### 7. Que comando mostra o histórico com um commit por linha?

- A) `git status`
- B) `git log --oneline`
- C) `git history`
- D) `git show`

<details>
<summary>Ver resposta</summary>

**B.** O `git log` sem opções mostra o mesmo histórico com autor, data e mensagem completa.

</details>

### 8. O que acontece se apagares a pasta `.git`?

- A) Nada, o Git volta a criá-la
- B) Perdes os ficheiros do projeto
- C) Perdes todo o histórico, e a pasta deixa de ser um repositório
- D) O repositório é apagado do GitHub

<details>
<summary>Ver resposta</summary>

**C.** Os ficheiros de trabalho ficam, mas os commits desaparecem. Se existir uma cópia no GitHub, essa não é afetada.

</details>

---

[← Voltar ao módulo 03](README.md) · Seguinte: [04 Histórico e desfazer →](../04-historico-e-desfazer/README.md)
