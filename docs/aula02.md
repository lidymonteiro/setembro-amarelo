# Tutorial: Construindo a área de destaque

Com nosso cabeçalho pronto, vamos criar a primeira seção de conteúdo da página. Chamamos essa área de "Seção Hero", pois é a primeira coisa que o visitante vê e serve para causar um grande impacto inicial, apresentando o tema principal do site.

<img width="1238" height="468" alt="Captura de Tela 2025-10-01 às 19 06 19" src="https://github.com/user-attachments/assets/0ede453f-1093-4c00-96d6-4b0434a9b03d" />


**Nosso objetivo**: Construir a seção de boas-vindas com uma imagem de fundo, um título chamativo e um botão de ação.

**Conceitos que vamos aprender**: Backgrounds com imagens e gradientes, estilização de tipografia (fontes, tamanhos) e a criação de botões interativos.

Ao final desse tutorial, teremos o nosso site assim: 

<img width="1237" height="553" alt="Captura de Tela 2025-10-01 às 19 07 47" src="https://github.com/user-attachments/assets/d3ebf8a5-3709-4ab9-bf79-13510dee4d2b" />



## A Estrutura HTML da Seção Hero

Vamos adicionar o "esqueleto" (estrutura) da nossa seção no arquivo `index.html`, logo após o fechamento da tag `</header>`.


### Passo 1: Criando a Seção e o Container

Toda nova área do nosso site será uma `<section>`. E, para manter o conteúdo alinhado com o menu, usaremos novamente nossa `div` com a `class="container"`.


Abaixo do `</header>`, adicione o seguinte código:

```html
<main>
    <section id="inicio" class="hero">
        <div class="container">
        
        </div>
    </section>
</main>
```

#### Explicação: 

- `<main>`: É uma tag semântica que indica o início do conteúdo principal da página.

- `<section id="inicio" class="hero">`: Criamos a seção. O `id="inicio"` permite que o link `"Início"` do menu role a tela para cá. A `class="hero"` será usada para aplicarmos todo o nosso estilo de destaque no CSS.

- `<div class="container">`: Reutilizamos nossa classe container para garantir que o conteúdo desta seção fique centralizado e com a mesma largura do nosso cabeçalho.


### Passo 2: Adicionando o conteúdo de destaque

Agora, dentro do `<div class="container">`, vamos adicione os textos e o botão que compõem nossa mensagem principal.

```html
<h2>Conversar pode mudar vidas</h2>
<p class="hero-hashtag">#VocêNãoEstáSozinho</p>
<p>Uma campanha de conscientização sobre a prevenção do suicídio.</p>
<a href="#ajuda" class="btn-cta">Quero ajuda</a>
```

####  Explicação: 

- `<h2>`: Usamos um título de nível 2 para a chamada principal da seção.

- `<p class="hero-hashtag">`: Um parágrafo com uma classe específica para que possamos dar um estilo diferente à hashtag.

- `<a href="#ajuda" class="btn-cta">`: Este é o nosso "Call to Action" (Chamada para Ação). É um link, mas vamos estilizá-lo para que se pareça com um botão. A classe `btn-cta` será usada para essa finalidade.


### Revisão do HTML da sessão:

Ao final, a estrutura completa da sua nova seção deve ser esta:

```html
<main>
    <section id="inicio" class="hero">
        <div class="container">
            <h2>Conversar pode mudar vidas</h2>
            <p class="hero-hashtag">#VocêNãoEstáSozinho</p> 
            <p>Uma campanha de conscientização sobre a prevenção do suicídio.</p>
            <a href="#ajuda" class="btn-cta">Quero ajuda</a>
        </div>
    </section>
</main>

```

O HTML completo da página até a sessão que acabamos de criar fica assim: 

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   
    <title>Setembro Amarelo - Abrace a Vida</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>

    <header>
        <div class="container">
            <div class="logo-wrapper">  <span class="logo-icon" aria-hidden="true">🎗️</span>
                <h1 class="logo-text">Setembro Amarelo</h1>
            </div>
            <nav>
                <ul>
                    <li><a href="#inicio">Início</a></li>
                    <li><a href="#sobre">Sobre</a></li>
                    <li><a href="#ajuda">Onde buscar ajuda</a></li>
                    <li><a href="#como-ajudar">Como ajudar</a></li>
                    <li><a href="#recursos">Recursos</a></li>
                    <li><a href="#contato">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <main>
        <section id="inicio" class="hero">
            <div class="container">
                <h2>Conversar pode mudar vidas</h2>
                <p class="hero-hashtag">#VocêNãoEstáSozinho</p> 
                <p>Uma campanha de conscientização sobre a prevenção do suicídio.</p>
                <a href="#ajuda" class="btn-cta">Quero ajuda</a>
            </div>
        </section>
    </main>

    <!-- Continua abaixo o HTML das outras áreas do site... -->

</body>
</html>

```


## Estilizando a Seção Hero com CSS

Com o HTML da seção pronto, vamos ao `style.css` para criar o visual impactante da nossa seção.


### Passo 1: O Fundo de impacto (`.hero`)

Esta é a parte mais importante. Vamos adicionar a imagem de fundo e uma camada escura por cima para garantir que o texto branco fique legível.

Para começar, crie no projeto uma pasta `images` e adicione a imagem: [https://blog.unoeste.br/wp-content/uploads/2021/09/setembro-amarelo.jpg](https://blog.unoeste.br/wp-content/uploads/2021/09/setembro-amarelo.jpg)

No seu `style.css`, após os estilos do `header`, adicione o código abaixo para estilizar a classe `.hero` que é utilizada na seção que criamos. 


```css
.hero {
    /* A mágica acontece aqui! Combinamos 3 camadas de fundo: */
    background: 
        linear-gradient(0deg, rgb(0 0 0 / 65%), rgb(4 1 1 / 35%)), /* 1. Camada de gradiente escuro por cima */
        url("../images/setembro-amarelo.jpg") center / cover no-repeat; /* 2. Nossa imagem de fundo */

    color: var(--white); /* Define que todo o texto dentro do hero será branco */
    text-align: center; /* Centraliza todo o conteúdo */
    padding: 100px 0; /* Adiciona um grande espaçamento interno (em cima e embaixo) para a seção ficar alta */
}
```

### Passo 2: Estilizando os Textos

Agora, vamos ajustar os tamanhos e fontes dos textos para criar uma hierarquia visual clara.

Adicione os estilos para o título e os parágrafos:

```css
.hero h2 {
    font-family: 'Montserrat', sans-serif; /* Usando a fonte de títulos que importamos */
    font-size: 3em; /* Tamanho 3x maior que o texto padrão */
    margin-bottom: 20px; /* Espaço abaixo do título */
}

.hero p {
    font-size: 1.2em;
    margin-bottom: 30px;
    max-width: 800px; /* Limita a largura do parágrafo para não ficar muito extenso */
    margin-left: auto; /* Truque para centralizar um elemento com largura máxima */
    margin-right: auto;
}

.hero-hashtag {
    font-weight: bold; /* Deixa a hashtag em negrito */
    color: var(--primary-color); /* Deixa a hashtag com a cor amarela da campanha */
    font-size: 1.3em;
    margin-top: -10px; /* Puxa a hashtag um pouco para cima */
}
```


### Passo 3: Criando o Botão de Ação (`.btn-cta`)
Vamos transformar nosso link `<a>` em um botão atraente e interativo.

Adicione os estilos para a classe `.btn-cta`:

```css
.btn-cta {
    display: inline-block; /* Permite que o link tenha altura, largura e padding */
    background-color: var(--hero-light-yellow); /* Usando nossa variável de cor */
    color: var(--dark-violet); /* Cor do texto do botão */
    padding: 15px 30px; /* Espaçamento interno que cria o tamanho do botão */
    text-decoration: none; /* Remove o sublinhado padrão do link */
    border-radius: 8px; /* Deixa os cantos do botão arredondados */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 0.3s ease; /* Animação suave para todas as propriedades */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra sutil */
}
```


#### Explicação: 
A propriedade `display: inline-block;` é essencial para estilizar links como se fossem botões.


### Passo 4: Adicionando interatividade (`:hover`)

Um bom botão reage quando o mouse passa por cima. Vamos adicionar esse efeito.
Adicione o estilo para o estado `:hover` do nosso botão:

```css
.btn-cta:hover {
    background-color: var(--primary-color); /* Muda a cor de fundo ao passar o mouse */
    transform: translateY(-2px); /* Efeito de "levantar" o botão sutilmente */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Aumenta a sombra para dar profundidade */
}
```

#### Explicação: 
A `transition` que definimos no passo anterior fará com que essa mudança de estilos aconteça de forma suave e agradável.


### Revisão do código CSS: 

Após realizar as etapas acima o seu código CSS será: 

```css
.hero {
    /* A mágica acontece aqui! Combinamos 3 camadas de fundo: */
    background: 
        linear-gradient(0deg, rgb(0 0 0 / 65%), rgb(4 1 1 / 35%)), /* 1. Camada de gradiente escuro por cima */
        url(https://blog.unoeste.br/wp-content/uploads/2021/09/setembro-amarelo.jpg) center / cover no-repeat; /* 2. Nossa imagem de fundo */

    color: var(--white); /* Define que todo o texto dentro do hero será branco */
    text-align: center; /* Centraliza todo o conteúdo */
    padding: 100px 0; /* Adiciona um grande espaçamento interno (em cima e embaixo) para a seção ficar alta */
}

.hero h2 {
    font-family: 'Montserrat', sans-serif; /* Usando a fonte de títulos que importamos */
    font-size: 3em; /* Tamanho 3x maior que o texto padrão */
    margin-bottom: 20px; /* Espaço abaixo do título */
}

.hero p {
    font-size: 1.2em;
    margin-bottom: 30px;
    max-width: 800px; /* Limita a largura do parágrafo para não ficar muito extenso */
    margin-left: auto; /* Truque para centralizar um elemento com largura máxima */
    margin-right: auto;
}

.hero-hashtag {
    font-weight: bold; /* Deixa a hashtag em negrito */
    color: var(--primary-color); /* Deixa a hashtag com a cor amarela da campanha */
    font-size: 1.3em;
    margin-top: -10px; /* Puxa a hashtag um pouco para cima */
}

.btn-cta {
    display: inline-block; /* Permite que o link tenha altura, largura e padding */
    background-color: var(--hero-light-yellow); /* Usando nossa variável de cor */
    color: var(--dark-violet); /* Cor do texto do botão */
    padding: 15px 30px; /* Espaçamento interno que cria o tamanho do botão */
    text-decoration: none; /* Remove o sublinhado padrão do link */
    border-radius: 8px; /* Deixa os cantos do botão arredondados */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 0.3s ease; /* Animação suave para todas as propriedades */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra sutil */
}

.btn-cta:hover {
    background-color: var(--primary-color); /* Muda a cor de fundo ao passar o mouse */
    transform: translateY(-2px); /* Efeito de "levantar" o botão sutilmente */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Aumenta a sombra para dar profundidade */
}

```

### Revisão CSS de todo o site: 

Segue abaixo o código completo do arquivo style.css após realizadas as mudanças que aprendemos nesse tutorial, acrescido do CSS do menu que adicionamos no outro tutorial: 

```css

/* Importa as fontes 'Montserrat' e 'Open Sans' do Google Fonts para serem usadas no site. */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Open+Sans:wght@400;600&display=swap');

/* Variáveis CSS para organizar nossas cores */
:root { 
    --primary-color: #F7C948; /* Amarelo principal */
    --secondary-color: #333;
    --text-color: #555;
    --light-bg: #f9f9f9;
    --white: #fff;
    --dark-violet: #3d3dcd; /* Roxo escuro para contraste */
    --hero-light-yellow: #fbecbb;
    --hero-lighter-yellow: #FFFFFF;
}

/* Reset básico para remover estilos padrão do navegador */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Estilos padrão para o corpo da página */
body {
    font-family: 'Open Sans', sans-serif;
    line-height: 1.6;
    color: var(--text-color);
    background-color: var(--white);
}


/* Container para centralizar o conteúdo. Será aplicado a qualquer elemento que tenha a class="container" no HTML */
.container { 
    width: 960px;                         /* Define uma largura máxima fixa para a área de conteúdo. */
    margin: 0 auto;                       /* Centraliza o container na página (0 de margem em cima/baixo, 'auto' nas laterais). */
    padding: 0 20px;                      /* Adiciona um espaçamento interno de 20px nas laterais, para o conteúdo não colar nas bordas. */
}


header {
    background-color: #242474;
    padding: 10px 0;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo-wrapper {
    display: flex;
    align-items: center; /* Alinha a logo ao centro */
    gap: 8px; /* Cria um espaço entre o ícone e o texto */
}

.logo-icon {
    font-size: 2em; /* Aumenta o tamanho do emoji */
}

.logo-text {
    font-size: 1.3em;
    color: var(--primary-color); /* Cor amarela */
    margin: 0;
}


header nav ul {
    list-style: none; /* Remove as bolinhas */
    display: flex;    /* Coloca os itens um ao lado do outro no menu */
}

header nav ul li {
    margin-left: 25px; /* Cria um respiro entre cada item do menu */
}

header nav ul li a {
    color: var(--white);
    text-decoration: none; /* Remove o sublinhado */
    font-weight: bold;
    font-size: 15px;
    transition: color 0.3s ease; /* Animação suave na troca de cor */
}

header nav ul li a:hover {
    color: var(--primary-color); /* Muda a cor para amarelo ao passar o mouse */
}

.hero {
    /* A mágica acontece aqui! Combinamos 3 camadas de fundo: */
    background: 
        linear-gradient(0deg, rgb(0 0 0 / 65%), rgb(4 1 1 / 35%)), /* 1. Camada de gradiente escuro por cima */
        url(https://blog.unoeste.br/wp-content/uploads/2021/09/setembro-amarelo.jpg) center / cover no-repeat; /* 2. Nossa imagem de fundo */

    color: var(--white); /* Define que todo o texto dentro do hero será branco */
    text-align: center; /* Centraliza todo o conteúdo */
    padding: 100px 0; /* Adiciona um grande espaçamento interno (em cima e embaixo) para a seção ficar alta */
}

.hero h2 {
    font-family: 'Montserrat', sans-serif; /* Usando a fonte de títulos que importamos */
    font-size: 3em; /* Tamanho 3x maior que o texto padrão */
    margin-bottom: 20px; /* Espaço abaixo do título */
}

.hero p {
    font-size: 1.2em;
    margin-bottom: 30px;
    max-width: 800px; /* Limita a largura do parágrafo para não ficar muito extenso */
    margin-left: auto; /* Truque para centralizar um elemento com largura máxima */
    margin-right: auto;
}

.hero-hashtag {
    font-weight: bold; /* Deixa a hashtag em negrito */
    color: var(--primary-color); /* Deixa a hashtag com a cor amarela da campanha */
    font-size: 1.3em;
    margin-top: -10px; /* Puxa a hashtag um pouco para cima */
}

.btn-cta {
    display: inline-block; /* Permite que o link tenha altura, largura e padding */
    background-color: var(--hero-light-yellow); /* Usando nossa variável de cor */
    color: var(--dark-violet); /* Cor do texto do botão */
    padding: 15px 30px; /* Espaçamento interno que cria o tamanho do botão */
    text-decoration: none; /* Remove o sublinhado padrão do link */
    border-radius: 8px; /* Deixa os cantos do botão arredondados */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 0.3s ease; /* Animação suave para todas as propriedades */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra sutil */
}

.btn-cta:hover {
    background-color: var(--primary-color); /* Muda a cor de fundo ao passar o mouse */
    transform: translateY(-2px); /* Efeito de "levantar" o botão sutilmente */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Aumenta a sombra para dar profundidade */
}

```


### Conclusão:

Trabalho fantástico! Agora você tem um cabeçalho funcional e uma seção de destaque visualmente impactante.

