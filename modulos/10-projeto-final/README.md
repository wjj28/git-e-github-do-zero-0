# Módulo 10 · Projeto final

## Objetivo

Aplicar tudo o que aprendeste num projeto completo, do `git init` ao pull request integrado, sem seguir um guião passo a passo.

## O projeto: o teu repositório de estudos

Vais criar o repositório que te vai acompanhar na próxima etapa da trilha (Python). Será o sítio onde guardas apontamentos, exercícios e pequenos projetos, e a primeira peça do teu portefólio.

Nome sugerido: `estudos-python`.

### Estrutura mínima

```text
estudos-python/
├── README.md
├── LICENSE
├── .gitignore
├── apontamentos/
│   └── git-resumo.md
└── exercicios/
    └── README.md
```

## Requisitos

### Parte 1 · Base

- [ ] Repositório criado localmente com `git init` e publicado no GitHub.
- [ ] `README.md` com: o que é o repositório, como está organizado, e os teus objetivos de estudo.
- [ ] `.gitignore` adequado a Python (`__pycache__/`, `venv/`, `.env`).
- [ ] Ficheiro `LICENSE`.
- [ ] Pelo menos **5 commits** com mensagens claras.

### Parte 2 · Branches e pull requests

- [ ] `apontamentos/git-resumo.md`: um resumo, por palavras tuas, dos comandos que mais usaste neste curso. Feito numa branch e integrado por **pull request**.
- [ ] Uma **issue** criada para uma melhoria, resolvida num PR que a fecha automaticamente (`Closes #N`).
- [ ] Nenhum commit feito diretamente na `main` depois da Parte 1.

### Parte 3 · Conflito e recuperação

- [ ] Um conflito de merge provocado e resolvido. Descreve em `apontamentos/git-resumo.md` como o resolveste.
- [ ] Um commit anulado com `git revert`.

### Parte 4 · Versão

- [ ] Tag `v1.0.0` criada e enviada para o GitHub.
- [ ] Uma Release publicada a partir da tag, com notas.

### Parte 5 · Colaboração (em pares ou com o formador)

- [ ] Um colega faz fork do teu repositório e abre um PR com uma sugestão.
- [ ] Tu revês o PR com pelo menos um comentário e integra-lo.
- [ ] Tu fazes o mesmo no repositório dele.

## Critérios de avaliação

| Critério | O que se observa |
|----------|------------------|
| Histórico | Commits pequenos, focados, com mensagens que se percebem |
| Fluxo | Trabalho feito em branches e integrado por PR |
| Documentação | README claro, Markdown bem formatado |
| Higiene | `.gitignore` correto, sem segredos nem ficheiros gerados |
| Colaboração | PR com descrição, revisão com comentários construtivos |

## Autoavaliação

Corre estes comandos no fim e olha para o resultado com olhos críticos:

```bash
git log --oneline --graph --all
git status
git tag
git remote -v
```

- O histórico conta uma história que outra pessoa conseguiria seguir?
- O `git status` está limpo?
- Alguém que chegue ao repositório pelo GitHub percebe o que é em 30 segundos?

## Desafios extra

- Chega à meta Prata do [Desafio Learn Git Branching](../../desafios/learn-git-branching.md) e regista o progresso em `apontamentos/learn-git-branching.md`, com um commit por etapa.
- Protege a branch `main` para exigir pull request.
- Cria um modelo de issue em `.github/ISSUE_TEMPLATE/`.
- Cria o repositório de perfil (com o nome do teu utilizador) e fixa o `estudos-python` no perfil.
- Configura a autenticação por SSH, se ainda usas HTTPS.

## Exercícios

Revisão final, para fazer depois de entregares o projeto.

1. Sem consultar nada, escreve num papel a sequência completa de comandos de uma tarefa, desde atualizar a `main` até apagar a branch depois do PR integrado. Compara com o "Fluxo completo de uma tarefa" da [cheatsheet](../../materiais/cheatsheet.md).
2. Refaz os quizzes dos módulos onde erraste mais de duas perguntas.
3. Abre o `git log --oneline` do teu projeto e escolhe o commit com a pior mensagem. Como a escreverias hoje?
4. Explica a um colega, em dois minutos e sem computador, a diferença entre `merge` e `rebase`.
5. Escolhe, em [Jogos e prática interativa](../../desafios/README.md), um jogo que ainda não fizeste e completa-o.

## E agora?

Tens as ferramentas para versionar e partilhar tudo o que vais construir. Na próxima etapa da trilha começamos o **Python do zero**, e cada exercício vai ser um commit neste repositório.

Até lá, a melhor forma de consolidar é usar o Git todos os dias, mesmo em coisas pequenas.

---

[← 09 Ferramentas avançadas](../09-ferramentas-avancadas/README.md) · [Início](../../README.md)
