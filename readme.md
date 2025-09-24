# Landing page: Setembro Amarelo


Você é uma pessoa desenvolvedora front-end na consultoria TS Software e acaba de ser chamada para um projeto prioritário.

A equipe de UX/UI finalizou o design da nova landing page para a campanha do Setembro Amarelo, a pedido de uma importante ONG de prevenção ao suicídio. O layout foi pensado para ser acolhedor, direto e, acima de tudo, útil.

![Mockup - Landing page Setembro Amarelo](images/mockup-site.png)


Seu desafio: Transformar este design em um site real, funcional e acessível.

Suas tarefas são claras:

- Estruturar a página com HTML semântico.

- Estilizar todos os componentes com CSS moderno.

- Garantir que o site seja 100% responsivo, pois o acesso via celular é crucial.

Este não é um trabalho comum. É a sua chance de usar suas habilidades técnicas para construir uma ferramenta que pode oferecer esperança e ajuda real às pessoas.


O desafio está lançado e as etapas das entregas bem definidas pelo líder técnico.

Com o design finalizado em mãos e a missão clara, você volta para a sua mesa, abre o seu editor de código favorito e cria a pasta do projeto: `site-setembro-amarelo`.

Vamos começar a construir algo que realmente importa.

---

## Etapa 1 - [HTML] Estrutura e mídia estática 

* **Meta:** Construir a estrutura superior e central da página, já incorporando a imagem para praticar o planejamento de layout desde o HTML.

* **Tarefas:**
    - [ ] **Configuração e Estrutura Básica:**
        - [ ] Apresentação do projeto e do layout final esperado.
        - [ ] Criação da estrutura de pastas (css/, images/) e do arquivo index.html.
        - [ ] Escrita do boilerplate HTML (`<!DOCTYPE>`, `<head>`, `<body>`, metatags, link para o CSS).
    - [ ] **Construção do Cabeçalho:**
        - [ ] Criar o header `<header>` semântico com logo e menu de navegação (`<nav>`).
        - [ ] Foco em tags semânticas e na criação de links âncora (`href="#..."`).
    - [ ] **Construção da Seção Hero (`#inicio`):**
        - [ ] Criar a primeira seção de conteúdo `<section id="inicio" class="hero"></section>`, com títulos, parágrafos e o link do botão CTA.
    - [ ] **Construção da Seção "Sobre" com imagem e vídeo (`#sobre`):**
      - [ ] Implementar a estrutura de div aninhadas para o layout de texto e imagem (`.sobre-content`, `.sobre-texto`, `.sobre-imagem`).
      - [ ] Inserir a tag <img> e reforçar a importância do atributo alt para acessibilidade.
      - [ ] Encontrar e incorporar um `<`iframe> do YouTube.
      - [ ] Envolver o `<iframe>` em uma div (`.video-container`) e explicar a boa prática para responsividade futura.
      - [ ] Análise do por que essa estrutura em HTML facilitará a estilização com CSS posteriormente.

* **Resultado Esperado:** Construção da metade superior da página completamente estruturada. O `index.html` conterá desde o cabeçalho até a seção "Sobre", já com a imagem e o vídeo posicionados na estrutura.

---

## Etapa 2 - [HTML] Estrutura de conteúdo interativo 

* **Meta:** Finalizar 100% da estrutura HTML da página, focando nos elementos mais complexos como os cards, vídeo e o formulário.

* **Tarefas:**
    - [ ] **Construção das Seções de Ajuda (`#ajuda` e `#como-ajudar`):**
      - [ ] Criar cada sessão e estruturas repetitivas com a tag `div` para os cards (`.card`)
    - [ ] **Construção da Seção de Recursos (`#recursos`):**
      - [ ] Criar a seção e a lista não ordenada `<ul>` com os links externos.
      - [ ] Usar atributo `target="_blank"` para links que levam a outros sites.

    - [ ] **Construção da Seção de Contato com Formulário (#contato)**:
      - [ ]Criar sessão e usar tags de formulário: `<form>`, `<label>`, `<input>`, `<textarea>`, `<button>`.
      - [ ] Usar recursos como label `for="..."` e `input id="..."` para acessibilidade.
      - [ ] Usar diferentes type de input (text, email) e o atributo `required`.

    - [ ] **Construção do Rodapé (`<footer>`):**
        - [ ] Finalizar a estrutura da página com o rodapé semântico.

* **Resultado Esperado:** O arquivo `index.html` estará 100% completo e estruturado, com todos os elementos (estáticos, de mídia e interativos) no lugar. A página está pronta para a estilização.

---

## Etapa 3: Estilização e Layouts (CSS) - Sem responsividade

* **Meta da Aula:** Estilizar a página, aplicando desde os fundamentos (cores, fontes) até os layouts mais complexos (Flexbox, Grid) e os estilos para os novos componentes.

* **Tarefas**
    - [ ] **Configuração inicial e estilos globais:**
        - [ ] Criar e vincular o `style.css`.
        - [ ] Configurar fontes (`@import`), variáveis de cores (`:root`), o reset (`*`) e os estilos do `<body>` e `.container`.
    - [ ] **Estilização do Header e Hero:**
        - [ ] Aplicar `display: flex` no cabeçalho e no `.logo-wrapper`.
        - [ ] Estilizar o `background` da seção Hero e o botão CTA (`.btn-cta`).
    - [ ] **Estilização dos layouts principais:**
        - [ ] Layout da Seção "Sobre": Usar `display: flex` em `.sobre-content` para alinhar texto e imagem.
        - [ ] Vídeo Responsivo: Aplicar o "truque" do `a`spect-ratio no .`video-container`.
        - [ ] Estilo dos Cards: Usar display: flex em `.cards-ajuda`.
        - [ ] Estilo do Grid: Usar display: grid em `.grid-ajuda`.
    - [ ] **Estilização do Formulário:**
        - [ ]  Estilizar a seção #contato e o contêiner do formulário (`.form-contato`).
        - [ ] Aplicar estilos aos campos `input`, `textarea`, `label` e ao botão de envio.
        - [ ] Estilizar o rodapé (`<footer>`).

* **Resultado Esperado:** A landing page estará completa, funcional e visualmente coesa, com todos os elementos perfeitamente integrados e estilizados.

---


## Etapa 4: Finalização e responsividade

* **Meta da Aula:** Adaptar a landing page para que ela seja funcional e visualmente agradável em diferentes tamanhos de tela, como celulares e tablets, utilizando Media Queries.

* **Tarefas**
  
    - [ ] Testes e análise com Dev Tools
    - [ ] Revisão da navegação
    - [ ] Revisão para telas pequenas
    - [ ] Revisão para telas médias
    - [ ] Revisão para telas grandes
 

* **Resultado Esperado:** A landing page estará 100% responsiva, oferecendo uma experiência de usuário consistente e de alta qualidade tanto em desktops quanto em dispositivos móveis.

---