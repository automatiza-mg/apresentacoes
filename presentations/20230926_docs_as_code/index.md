# Documentação como código

O que iremos automatizar hoje?



## Agenda
- [Docs as code](https://www.writethedocs.org/guide/docs-as-code/).
- Pré-requisitos:
    - GitHub.
    - Instalações.
    - 101 terminal.
    - Markdown.
    - Site estático.
- Publicação.



## [Docs as code](https://www.writethedocs.org/guide/docs-as-code/)
- Filosofia de escrita de documentação com as [mesmas ferramentas utilizadas para criação de códigos](https://ofuturojacomecou.com.br/blog/como-o-github-pode-ser-utilizado-para-facilitar-o-entendimento-das-normas-de-sua-equipe/):
    - Issues.
    - Controle de versão.
    - Texto.
    - Revisões.
    - Automatizações.


## [Docs as code](https://www.writethedocs.org/guide/docs-as-code/)
- Exemplos:
  - [Handbook SUGES-MG](https://suges-mg.github.io/handbook/).
  - [Esta apresentação](https://github.com/suges-mg/reveal.js/blob/master/presentations/20230926_docs_as_code/index.md).



## Pré-requisitos


## GitHub
- Já tem uma conta registrada?


## Instalações
- Editor VsCode.
- Git.
- Python.


## 101 terminal
- Terminal: pwd, ls, cd, mkdir, touch, cat, rm.
- Git: init, status, log, add, commit, checkout, clone, pull, push.


## Markdown
- Cabeçalho: #
- Negrito: `**texto em negrito**`
- Itálico: `*texto em italico*`
- Citação: >
- Lista ordenada: 1. Primeiro
- Lista não ordenada: - Item
- Código em linha: "``"
- Links: `[]()`
- Imagens: `![]()` - https://imgur.com/


## Markdown Extendido (Atenção)
- Tabelas: [Table Generator](https://www.tablesgenerator.com/markdown_tables)
- Lista de Tarefas: - [ ] Tarefa 1
- Bloco de Código: "```"
- Emoji: :snake:
- Tachado: `~~tachado~~`
- Realçado: ==realçado==
- [Mermaid](https://mermaid.js.org/intro/)



## Site estático


## Mkdocs
- Arquitetura
    - docs/
    - site/
    - mkdocs.yml


## Mkdocs
- **Para criar um projeto**: `mkdocs new <nome_projeto>`
- **Conversão md para html**: `mkdocs build`
- **Iniciar um servidor**: `mkdocs serve`
- **Fazer deploy**: `mkdocs gh-deploy`
- **Para pedir ajuda**: `mkdocs --help`


## Mkdocs

```
mkdir meu-primeiro-site-estatico
cd meu-primeiro-site-estatico
touch .gitignore # https://www.toptal.com/developers/gitignore/
touch requirements.txt # mkdocs on pypi
python -m venv venv # python3 -m venv venv no Linux
source venv/Scripts/activate # source venv/bin/activate
pip install -r requirements.txt
git init
git branch -M main # Pode ser configurado
git add .
git commit -m "Commit Inicial"
mkdocs new .
mkdocs serve # Testa mudanças ao vivo
```


## Customizações
- Instalação de Pacote `pymdown-extensions`:

```
$ pip install pymdown-extensions

# mkdocs.yml
markdown_extensions:
  - pymdownx.tasklist
  - pymdownx.emoji
  - pymdownx.mark      # Realçado
  - pymdownx.tilde     # Tachado
  - pymdownx.highlight # Códigos
```


## Customatizações

```
# Mermaid

# mkdocs.yml
markdown_extensions:
  - pymdownx.superfences:
      custom_fences:
        - name: mermaid
          class: mermaid
          format: !!python/name:pymdownx.superfences.fence_div_format

extra_css:
  - https://unpkg.com/mermaid@10.4.0/dist/mermaid.css
extra_javascript:
  - https://unpkg.com/mermaid@10.4.0/dist/mermaid.min.js
```


## Customatizações
- Instalação de Pacote [mkdocs-material](https://squidfunk.github.io/mkdocs-material/getting-started/):

```
$ pip install mkdocs-material

# mkdocs.yml
theme:
  name: material
  palette:
    - scheme: default
      toggle:
        icon: material/weather-night
        name: Modo noturno
    - scheme: slate
      toggle:
        icon: material/weather-sunny
        name: Modo claro
```


## Customatizações
Utilização Superfences

```
hl_lines="" linenums="" title="Meu Arquivo.py"
```


## Publicação
