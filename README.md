<p align="center">
  <a href="https://revealjs.com">
  <img src="https://hakim-static.s3.amazonaws.com/reveal-js/logo/v1/reveal-black-text-sticker.png" alt="reveal.js" width="500">
  </a>
  <br><br>
  <a href="https://github.com/hakimel/reveal.js/actions"><img src="https://github.com/hakimel/reveal.js/workflows/tests/badge.svg"></a>
  <a href="https://slides.com/"><img src="https://s3.amazonaws.com/static.slid.es/images/slides-github-banner-320x40.png?1" alt="Slides" width="160" height="20"></a>
</p>

A biblioteca open-source reveal.js é um fremework para criação de apresentações.
Uma demostração de seu poderá ser acessado em [revealjs.com](https://revealjs.com/).
Esta biblioteca vem com várias funcionalidades como [slides hierárquicos](https://revealjs.com/vertical-slides/), [suporte a markdown](https://revealjs.com/markdown/), [animações](https://revealjs.com/auto-animate/), [exportar para PDF](https://revealjs.com/pdf-export/), [notas para o apresentador](https://revealjs.com/speaker-view/), [LaTeX typesetting](https://revealjs.com/math/), [sintaxe para demonstrar código](https://revealjs.com/code/) e uma [extensiva API](https://revealjs.com/api/).

---

Este repositório é um fork do [repositório original](https://github.com/hakimel/reveal.js) visando sempre buscar as versões mais atualizadas do mesmo.
Por não ser um repositório da organização [transparencia-mg](https://github.com/transparencia-mg) não é permitido a inclusão de issues no mesmo.
Neste sentido, os issues para solicitação de melhoria e ou correção de bugs poderão ser abertos no repositório [handbook](https://github.com/transparencia-mg/handbook/issues), com a inclusão da tag `reveal.js`.

---

### Vídeo demonstração

[![Watch the video](https://img.youtube.com/vi/YMAcnwdf8rw/maxresdefault.jpg)](https://youtu.be/YMAcnwdf8rw)

### Instalação

Para utilização do repositório necessário realizar a instalação do programa Docker:
    - 🚀 [Instalação docker windows](https://docs.docker.com/desktop/install/windows-install/#:~:text=Double%2Dclick%20Docker%20Desktop%20Installer,bottom%20of%20your%20web%20browser.)
    - 🚀 [Instalação docker linux](https://docs.docker.com/desktop/install/linux-install/)

### Comandos automatizados

```
# Listar comandos disponíveis
task --list

# Update index.html file com novas apresentações
task index

# Criar estrutura de nova apresentação
task presentation <nome_da_nova_apresentação>

Inicializa container docker e servidor local
task container
```

Obs.: Ao executar o comando `task presentation <nome_da_nova_apresentação>` o nome da nova apresentação deverá ser informada no padrão [`snaque_small_case`](https://en.wikipedia.org/wiki/Snake_case) sem caracteres acentuação e ou especiais.

Comandos `task presentation <nome_da_nova_apresentação>` e `task index` realizam modificações/criações de arquivos no repositório, sendo necessário, portanto, posterior commit.

### Suas apresentações

Para criar uma nova apresentação basta rodar o comando `task presentation nome_da_nova_apresentação`.
Uma pasta com o nome da apresentação será adicionada em `presentations/`.
A nova apresentação deverá ser criada utilizando Markdown no arquivo `index.md`.
Três linhas em branco separam um slide do outro horizontalmente.
Duas linhas em branco separam um slide do outro verticalmente.
`Note:` Adiciona notas que podem ser acessadas com o "speaker view".

Este template possui a ferramenta "speaker view".
Ao apertar a tecla "s" uma nova janela será aberta, apenas para o apresentador, com um relógio, preview dos slides e notas (caso elas existam).
O "speaker view" desta apresentação também foi configurado para ajudar na gestão do tempo.
A configuração padrão adotada foi de 3600 segundos (ou uma hora). Caso necessite, esta  poderá ser modificada no parâmetro `totalTime` ta tag `script` do arquivo `index.html` existente na raiz da sua apresentação.

```
    <script>
      // More info about initialization & config:
      // - https://revealjs.com/initialization/
      // - https://revealjs.com/config/
      Reveal.initialize({
        hash: true,
        progress: true,
        slideNumber: 'c/t',
        totalTime: 3600,

        // Learn about plugins: https://revealjs.com/plugins/
        plugins: [ RevealMarkdown, RevealHighlight, RevealNotes ]
      });
    </script>
```

O [plugin Mermaid foi instalado](https://github.com/transparencia-mg/handbook/issues/64#issuecomment-1474349126) no template, devendo a sintaxe abaixo ser utilizada normalmente nos arquivos markdow:

```
<div class="mermaid">
  <pre>
    <!-- %%{init: {'theme': 'dark', 'themeVariables': { 'darkMode': true }}}%% -->
    flowchart TD
      A[Start] --> B;
      B[End];
  </pre>
</div>
```

Para consulta a sintaxe para escrita de gráficos e fluxogramas com Mermaid consulte a [documentação da ferramenta](https://mermaid.js.org/intro/). Diversas opções estão disponíveis, sendo provavelmente o [fluxograma](https://mermaid.js.org/syntax/flowchart.html) o mais utilizado. Para configurar o tema Mermaid (linha `<!-- %%{init: {'theme': 'dark', 'themeVariables': { 'darkMode': true }}}%% -->` comentada no script acima) basta acessar, também, a [documentação](https://mermaid.js.org/config/theming.html#theme-configuration).

Outro plugin instalado foi o [menu](https://github.com/denehyg/reveal.js-menu). Todas as suas funcionalidades podem ser acessadas [neste live demo](https://denehyg.github.io/reveal.js-menu/#/home). O arquivo `links.html` criado na pasta de todas as apresentações é uma de suas funcionalidades e possibilita a inclusão de links na apresentação. Suas opções podem ser acessadas em um menu sanduíche criado no canto inferior esquerdo das apresentações, não deixe de conferir e experimentar.

As apresentações pode ser [salvas em pdf](https://revealjs.com/pdf-export/) no navegador Google Chrome, bastando acrescentar `?print-pdf` ao final da URL da mesma e utilizando o atalho `CTRL+P` para selecionar o local aonde a mesma será salva em sua máquina.

### Atalhos

- `esc`: Visualização de todos os slides.
- `g`: Dá possibilidade de indicar o número do slide que deseja acessar.
- `s`: Acessa página speaker view.

### Atualizações com o repositório forkado

Com exceção dos arquivos `index.html` e `README.md` as demais adaptações no repositório ocorreram em arquivos próprios.
Seguindo orientações [deste post Stackoverflow](https://stackoverflow.com/a/41448584/11755155) as atualizações deverão ocorrer da seguinte maneira:

```
# Sem nada para commitar na master
$ git checkout master

# Pull da master
$ git pull origin master

# Fetch upstream
$ git pull upstream master

# Rebase
$ git rebase upstream/master

# git rebase --skip poderá ser utilizado para facilitar o processo

# Caso não acha nenhum conflito - Successfully rebased and updated refs/heads/master.
# Ligar o servidor para testar se nada quebrou
$ task container

# Tudo funcionando realizar o push para origin
$ git push origin master
```
