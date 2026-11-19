# Quiz · Módulo 02 · Terminal básico

Responde de cabeça antes de abrires cada resposta. Se errares mais de duas, relê o [módulo](README.md) antes de avançar.

### 1. Que comando mostra a pasta onde estás?

- A) `ls`
- B) `cd`
- C) `pwd`
- D) `where`

<details>
<summary>Ver resposta</summary>

**C.** `pwd` vem de *print working directory*.

</details>

### 2. Estás em `/home/ana/curso-git/treino`. Onde ficas depois de `cd ../..`?

- A) `/home/ana/curso-git`
- B) `/home/ana`
- C) `/home`
- D) `/`

<details>
<summary>Ver resposta</summary>

**B.** Cada `..` sobe um nível: de `treino` para `curso-git`, e de `curso-git` para `ana`.

</details>

### 3. Que comando mostra também os ficheiros ocultos, como a pasta `.git`?

- A) `ls -l`
- B) `ls -a`
- C) `ls -h`
- D) `ls .`

<details>
<summary>Ver resposta</summary>

**B.** O `-a` (*all*) inclui os nomes que começam por ponto. O `-l` mostra detalhes, mas não os ocultos.

</details>

### 4. Qual é a diferença entre `>` e `>>`?

```bash
echo "Olá" > notas.txt
echo "Mundo" >> notas.txt
```

- A) Nenhuma
- B) `>` substitui o conteúdo do ficheiro, `>>` acrescenta no fim
- C) `>` acrescenta no fim, `>>` substitui o conteúdo
- D) `>>` cria dois ficheiros

<details>
<summary>Ver resposta</summary>

**B.** Depois dos dois comandos, o ficheiro tem duas linhas: `Olá` e `Mundo`. Se o segundo usasse `>`, ficava só `Mundo`.

</details>

### 5. Apagaste um ficheiro com `rm relatorio.txt`. Onde o podes recuperar?

- A) Na reciclagem
- B) Com `Ctrl+Z`
- C) Com o comando `unrm`
- D) Em lado nenhum: o `rm` apaga de vez

<details>
<summary>Ver resposta</summary>

**D.** O `rm` não passa pela reciclagem. É uma das razões para usar Git: o que está num commit pode ser recuperado.

</details>

### 6. No comando `ls -l Documentos`, o que é `-l`?

- A) O comando
- B) Uma opção (flag)
- C) O argumento
- D) O nome de uma pasta

<details>
<summary>Ver resposta</summary>

**B.** `ls` é o comando (o que fazer), `-l` é a opção (como fazer) e `Documentos` é o argumento (sobre o quê).

</details>

### 7. O `git log` encheu o ecrã e o terminal não aceita comandos. Como sais?

- A) Com `q`
- B) Com `Esc`
- C) Fechando o terminal
- D) Com `exit`

<details>
<summary>Ver resposta</summary>

**A.** O `q` sai dos ecrãs de leitura. Para interromper um comando que está a correr, usa-se `Ctrl+C`.

</details>

### 8. Que comando muda o nome de `copia.txt` para `antigo.txt`?

- A) `cp copia.txt antigo.txt`
- B) `rename copia.txt antigo.txt`
- C) `mv copia.txt antigo.txt`
- D) `cd copia.txt antigo.txt`

<details>
<summary>Ver resposta</summary>

**C.** O `mv` serve para mover e para mudar o nome. O `cp` criava uma cópia e deixava o original.

</details>

---

[← Voltar ao módulo 02](README.md) · Seguinte: [03 Primeiro repositório →](../03-primeiro-repositorio/README.md)
