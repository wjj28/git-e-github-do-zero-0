# Módulo 08 · Boas práticas

## Objetivos

No fim deste módulo consegues:

- Escrever mensagens de commit úteis.
- Escrever um README em Markdown.
- Escolher uma licença.
- Apresentar bem o teu perfil no GitHub.

## Mensagens de commit

O histórico é documentação. Daqui a seis meses, a mensagem do commit é a única explicação do motivo de uma alteração.

### Estrutura

```text
Título curto, até cerca de 50 caracteres

Corpo opcional. Explica o porquê da alteração e o contexto,
não o que cada linha faz (isso já se vê no diff).
```

Regras práticas:

- O título completa a frase "Este commit...": *Adiciona*, *Corrige*, *Remove*, *Atualiza*.
- Sem ponto final no título.
- Uma linha em branco entre o título e o corpo.
- Um commit, uma ideia. Se o título precisa de um "e", provavelmente são dois commits.

Para escrever título e corpo, corre `git commit` sem `-m`. Abre-se o editor que configuraste.

### Conventional Commits

Muitas equipas seguem a convenção **Conventional Commits**, que acrescenta um prefixo com o tipo da alteração:

```text
feat: adiciona exportação do relatório para Excel
fix: corrige cálculo do total com valores vazios
docs: atualiza instruções de instalação
refactor: separa leitura de dados em função própria
chore: atualiza dependências
```

| Prefixo | Uso |
|---------|-----|
| `feat` | Funcionalidade nova |
| `fix` | Correção de erro |
| `docs` | Só documentação |
| `refactor` | Reorganização sem mudar o comportamento |
| `test` | Testes |
| `chore` | Manutenção (configuração, dependências) |

### Em que língua?

Combina com a equipa e sê consistente. Em projetos abertos e em muitas empresas usa-se inglês. Em projetos pessoais ou equipas locais, português é perfeitamente válido.

## README

O `README.md` é a página de entrada do repositório. O GitHub mostra-o automaticamente. Um projeto sem README parece abandonado.

Um bom README responde a:

1. **O que é** o projeto, numa ou duas frases.
2. **Como instalar.**
3. **Como usar**, com um exemplo.
4. **Como contribuir** (se aplicável).
5. **Licença.**

Modelo para um projeto de automação:

````markdown
# Relatório de Vendas

Script que lê as vendas de um ficheiro Excel e envia um resumo semanal por email.

## Instalação

```bash
git clone https://github.com/utilizador/relatorio-vendas.git
cd relatorio-vendas
pip install -r requirements.txt
```

## Utilização

```bash
python relatorio.py --mes 2026-11
```

## Configuração

Copia `.env.exemplo` para `.env` e preenche as credenciais de email.

## Licença

MIT
````

## Markdown em 5 minutos

Markdown é a linguagem de formatação dos READMEs, issues e pull requests.

| Escreves | Obténs |
|----------|--------|
| `# Título` | Título principal |
| `## Subtítulo` | Subtítulo |
| `**negrito**` | **negrito** |
| `*itálico*` | *itálico* |
| `` `código` `` | `código` |
| `[texto](https://exemplo.com)` | ligação |
| `![descrição](imagem.png)` | imagem |
| `- item` | lista |
| `1. item` | lista numerada |
| `- [ ] tarefa` | caixa de verificação |
| `> texto` | citação |

Blocos de código usam três acentos graves, com o nome da linguagem para ativar as cores:

````markdown
```python
print("Olá, mundo")
```
````

No VS Code, `Ctrl+Shift+V` mostra a pré-visualização do Markdown.

## Licença

Sem licença, ninguém tem autorização legal para usar o teu código, mesmo estando público. Adiciona um ficheiro `LICENSE` na raiz.

| Licença | Em resumo |
|---------|-----------|
| **MIT** | Podem fazer quase tudo, desde que mantenham o aviso de autoria. A mais usada |
| **Apache 2.0** | Semelhante à MIT, com proteção quanto a patentes |
| **GPL v3** | Quem distribuir versões modificadas tem de as partilhar sob a mesma licença |

O site [choosealicense.com](https://choosealicense.com) ajuda a escolher. No GitHub, ao criares um ficheiro chamado `LICENSE` pelo site, aparece um botão para escolher um modelo.

## O que não pôr num repositório

- Palavras-passe, tokens, chaves de API, ficheiros `.env`.
- Dados pessoais de clientes ou colegas.
- Ficheiros gerados (`__pycache__`, `venv`, `node_modules`).
- Ficheiros muito grandes (vídeos, bases de dados).

Para credenciais, o padrão habitual é: o `.env` real fica no `.gitignore`, e no repositório vai um `.env.exemplo` com os nomes das variáveis e valores fictícios.

## O teu perfil

- Fotografia, nome e biografia preenchidos.
- **Fixa** (*pin*) os teus melhores repositórios no perfil.
- Cria um repositório com o mesmo nome do teu utilizador: o README dele aparece no topo do teu perfil.
- Cada repositório com descrição curta e README.

## Exercícios

1. Reescreve estas mensagens de commit: `update`, `corrigi cenas`, `versão final 2`.
2. Escreve um README completo para o `meu-diario`, com pelo menos um título, uma lista, uma ligação e um bloco de código.
3. Adiciona uma licença ao repositório.
4. Faz três commits seguindo Conventional Commits.
5. Cria o repositório de perfil (com o nome do teu utilizador) e escreve uma apresentação.
6. Percorre os teus repositórios e dá uma descrição a cada um.

## Checklist

- [ ] As minhas mensagens de commit explicam o que mudou e porquê.
- [ ] Os meus repositórios têm README.
- [ ] Sei escrever Markdown básico sem consultar.
- [ ] O meu perfil está apresentável.

## Referências

**Português**

- [Conventional Commits (em português)](https://www.conventionalcommits.org/pt-br/v1.0.0/)
- [GitHub Docs: Sintaxe básica de escrita e formatação](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
- [GitHub Docs: Sobre READMEs](https://docs.github.com/pt/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes)

**English**

- [How to Write a Git Commit Message (cbea.ms)](https://cbea.ms/git-commit/)
- [Markdown Guide](https://www.markdownguide.org/basic-syntax/)
- [Choose a License](https://choosealicense.com)
- [Make a README](https://www.makeareadme.com)

---

[← 07 Colaboração](../07-colaboracao/README.md) · [Início](../../README.md) · Seguinte: [09 Ferramentas avançadas →](../09-ferramentas-avancadas/README.md)
