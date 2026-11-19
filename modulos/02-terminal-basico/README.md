# Módulo 02 · Terminal básico

## Objetivos

No fim deste módulo consegues:

- Abrir o terminal e saber em que pasta estás.
- Navegar entre pastas.
- Criar, ver, mover e apagar ficheiros e pastas com comandos.

## Porquê o terminal

O Git nasceu como ferramenta de linha de comandos. Existem programas com botões, mas todos executam os mesmos comandos por baixo. Quem percebe os comandos consegue usar qualquer ferramenta, ler qualquer tutorial e resolver problemas quando os botões falham.

Em automação com Python vais viver no terminal: é lá que se correm scripts, se instalam bibliotecas e se põem bots a funcionar.

## Que terminal usar

- **Windows:** usa o **Git Bash**, instalado com o Git. Aceita os mesmos comandos que macOS e Linux, por isso todos os exemplos do curso funcionam.
- **macOS / Linux:** usa a aplicação **Terminal**.

No VS Code, o terminal integrado abre com `` Ctrl+` ``. No Windows, podes escolher o Git Bash na seta ao lado do `+`.

## Anatomia de um comando

```bash
ls -l Documentos
```

| Parte | Nome | Função |
|-------|------|--------|
| `ls` | comando | o que fazer |
| `-l` | opção (flag) | como fazer |
| `Documentos` | argumento | sobre o quê |

Escreves o comando e carregas em **Enter**. Se não aparecer nenhuma mensagem, normalmente correu bem.

## Onde estou?

```bash
pwd
```

Mostra o caminho da pasta atual (*print working directory*). O terminal está sempre "dentro" de uma pasta, e os comandos atuam sobre ela.

## O que há aqui?

```bash
ls        # lista o conteúdo da pasta
ls -l     # lista com detalhes (tamanho, data)
ls -a     # inclui ficheiros ocultos (os que começam por ponto)
```

O `ls -a` vai ser importante: a pasta onde o Git guarda o histórico chama-se `.git` e é oculta.

## Mudar de pasta

```bash
cd Documentos     # entra na pasta Documentos
cd ..             # sobe um nível
cd ~              # vai para a tua pasta pessoal
cd -              # volta à pasta anterior
```

Dois símbolos a conhecer:

- `.` é a pasta atual.
- `..` é a pasta acima.

Se o nome tiver espaços, usa aspas: `cd "Os Meus Projetos"`. Para evitar isto, dá aos teus projetos nomes sem espaços nem acentos, por exemplo `meu-projeto`.

## Criar

```bash
mkdir projetos            # cria uma pasta
touch notas.txt           # cria um ficheiro vazio
echo "Olá" > notas.txt    # escreve no ficheiro (substitui o conteúdo)
echo "Mundo" >> notas.txt # acrescenta uma linha no fim
```

## Ver conteúdo

```bash
cat notas.txt     # mostra o conteúdo do ficheiro
code notas.txt    # abre o ficheiro no VS Code
code .            # abre a pasta atual no VS Code
```

## Copiar, mover e apagar

```bash
cp notas.txt copia.txt       # copia
mv copia.txt antigo.txt      # muda o nome (ou move)
rm antigo.txt                # apaga um ficheiro
rm -r pasta-velha            # apaga uma pasta e tudo o que tem dentro
```

> **Atenção:** `rm` não envia para a reciclagem. O que apagares no terminal desaparece de vez. Confirma sempre com `pwd` e `ls` antes de apagar.

## Atalhos que poupam tempo

| Atalho | O que faz |
|--------|-----------|
| `Tab` | Completa nomes de ficheiros e pastas |
| `↑` / `↓` | Percorre os comandos anteriores |
| `Ctrl+C` | Interrompe o comando em execução |
| `Ctrl+L` ou `clear` | Limpa o ecrã |
| `q` | Sai de ecrãs de leitura (como o do `git log`) |

Usa o `Tab` sempre. Além de poupar teclas, evita erros de escrita.

## Mão na massa

```bash
cd ~
mkdir curso-git
cd curso-git
pwd
mkdir treino
cd treino
touch lista.txt
echo "Aprender Git" > lista.txt
echo "Aprender Python" >> lista.txt
cat lista.txt
ls -l
cd ..
ls
```

A pasta `curso-git` vai ser a tua base de trabalho nos próximos módulos.

## Exercícios

1. Dentro de `curso-git`, cria a estrutura `exercicio/dados` e `exercicio/relatorios` usando só o terminal.
2. Cria `exercicio/dados/clientes.txt` com três nomes, um por linha.
3. Copia `clientes.txt` para a pasta `relatorios` com o nome `clientes-backup.txt`.
4. Muda o nome de `clientes-backup.txt` para `backup.txt`.
5. Apaga a pasta `exercicio` inteira.
6. O que faz `cd ../..`? Experimenta e confirma com `pwd`.

## Quiz e jogo

- Testa o que aprendeste no [quiz do módulo 02](quiz.md).
- Joga o [Terminus](../../desafios/README.md#terminus), uma aventura de texto onde te deslocas com `cd` e `ls`, e faz os exercícios indicados.

## Checklist

- [ ] Sei sempre em que pasta estou (`pwd`).
- [ ] Consigo navegar com `cd` e listar com `ls`.
- [ ] Consigo criar e apagar ficheiros e pastas.
- [ ] Uso o `Tab` para completar nomes.

## Referências

**Português**

- [Pro Git: A linha de comando](https://git-scm.com/book/pt-br/v2/Primeiros-Passos-A-Linha-de-Comando)

**English**

- [MDN: Command line crash course](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Environment_setup/Command_line)
- [MIT Missing Semester: The Shell](https://missing.csail.mit.edu/2020/course-shell/)
- [Ubuntu: The Linux command line for beginners](https://ubuntu.com/tutorials/command-line-for-beginners)

---

[← 01 Preparar o ambiente](../01-preparar-ambiente/README.md) · [Início](../../README.md) · Seguinte: [03 Primeiro repositório →](../03-primeiro-repositorio/README.md)
