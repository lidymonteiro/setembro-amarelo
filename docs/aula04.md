# Tutorial: Construindo a seção de ajuda com cards

Depois de apresentar a campanha, é fundamental oferecer caminhos para quem precisa de ajuda. Faremos isso criando uma seção com três cards informativos, cada um focado em um recurso diferente.

**Nosso objetivo:** Construir uma seção com um layout de três cards, alinhados e interativos.

**Conceitos que vamos aprender:** Reutilização de componentes HTML (cards), uso de Flexbox para centralizar e distribuir itens, estilização de cards com sombra e interatividade.

**Onde Adicionar o novo código?**
Como nas outras vezes, a localização é muito importante. A nova seção ajuda deve ser adicionada depois da seção sobre, mas ainda dentro da tag `<main>`.

- ANTES: Como seu código está agora

O final do seu arquivo `index.html` deve se parecer com isto, terminando com a seção sobre:

```html
                <div class="video-container">
                    <!-- Aqui os códigos da div ... -->
                </div>
            </div>
        </section> <!-- fim da seção sobre -->

    </main>

</body>
</html>
```

- DEPOIS: Como seu código deve ficar

Agora, vamos adicionar a nova seção ajuda no espaço em branco entre o final da seção `sobre` e o fechamento da tag `</main>`.

O resultado final, com a nova seção adicionada no lugar certo, ficará assim:


```html
                <div class="video-container">
                    <!-- Aqui os códigos da div ... -->
                </div>
            </div>
        </section> <!-- fim da seção sobre -->

        <!-- Adicionando a seção de ajuda -->
        <section id="ajuda" class="call-to-action light-bg">
            <div class="container">
                <h3>Você não está sozinha(o). Busque Ajuda!</h3>
            </div>
        </section>

    </main>

</body>
</html>
```

**O que são as novas classes `call-to-action` e `light-bg`?** 

Você deve ter notado que adicionamos duas classes à nossa nova tag <section>. O motivo é a reutilização e organização do nosso CSS:

- `light-bg:` É uma classe "utilitária". A única função dela será aplicar uma cor de fundo suave (`background-color`). Poderemos reutilizar essa mesma classe em qualquer outra seção do site que quisermos destacar com essa cor de fundo, sem precisar reescrever o código.

- `call-to-action:` É uma classe "semântica", ou seja, que descreve o propósito da seção. Damos esse nome para que possamos aplicar um conjunto de estilos padrão (como espaçamentos e tamanho de fonte do título) a todas as seções do nosso site que funcionem como uma "Chamada para Ação".


**Resumindo:** A nova `<section id="ajuda" class="call-to-action light-bg">` é a terceira "irmã" que vai morar dentro da "casa" `<main>`, junto com as seções inicio e sobre. E demos dois "sobrenomes" (classes): `call-to-action` e `light-bg`. Que nos ajudarão a aplicar estilos de forma inteligente e organizada no CSS.


## Parte 1: A estrutura HTML dos cards

Com a estrutura da seção no lugar certo, vamos construir o conteúdo dela.

### Passo 1: O Agrupador dos cards (`.cards-ajuda`)

Para que possamos alinhar todos os nossos cards de uma vez, precisamos de uma `div` "pai" para agrupar. 

Dentro do container da nova seção, logo após o `<h3>`, adicione o agrupador:

```html
<div class="cards-ajuda">

</div>
```

**Explicação:** A `<div class="cards-ajuda">` será o nosso container Flexbox. No CSS, vamos instruir essa `div` a alinhar todos os seus filhos (os cards) horizontalmente, com um espaçamento entre eles.


## Passo 2: Construindo o primeiro card

Agora vamos criar a estrutura do nosso primeiro card. Todos os outros cards seguirão exatamente o mesmo modelo, o que nos ensina sobre componentes reutilizáveis.

Dentro da `<div class="cards-ajuda">`, adicione o código do primeiro card:

```html
<div class="card">
    <h4>CVV - Centro de Valorização da Vida</h4>
    <p>Atendimento voluntário e gratuito, 24 horas por dia, todos os dias da semana. Sigiloso.</p>
    <a href="tel:188" class="btn-card">Ligue 188</a>
    <a href="https://www.cvv.org.br/" target="_blank" class="btn-card">Site do CVV</a>
</div>
```

Ao final do passo 2 esse será o HTML da área de ajuda, com apenas 1 card: 

```html
<section id="ajuda" class="call-to-action light-bg">
    <div class="container">
        <h3>Você não está sozinha(o). Busque Ajuda!</h3>
        <div class="cards-ajuda">

            <div class="card">
                <h4>CVV - Centro de Valorização da Vida</h4>
                <p>Atendimento voluntário e gratuito, 24 horas por dia, todos os dias da semana. Sigiloso.</p>
                <a href="tel:188" class="btn-card">Ligue 188</a>
                <a href="https://www.cvv.org.br/" target="_blank" class="btn-card">Site do CVV</a>
            </div>

        </div>
    </div>
</section>
```

Passo 3: Criando os outros cards

No layout da área de ajuda, temos 3 cards. E já aprendemos como criar o primeiro card.  Como a estrutura é a mesma, podemos simplesmente copiar e colar o primeiro card mais duas vezes, alterando apenas o conteúdo de cada um.


Logo após o primeiro card, adicione os outros dois dentro da `<div class="cards-ajuda"` e edite o conteúdo: 

```html
<div class="card">
    <h4>CAPS - Centro de Atenção Psicossocial</h4>
    <p>Serviços de saúde mental públicos e gratuitos.</p>
    <a href="#" class="btn-card">Encontre um CAPS</a>
</div>

<div class="card">
    <h4>Urgências e emergências</h4>
    <p>Em casos de emergência, procure um pronto atendimento médico ou hospitalar.</p>
    <a href="tel:192" class="btn-card">SAMU 192</a>
</div>
```

Ao final dessa etapa, esse será o código final da área de ajuda: 


```html
<section id="ajuda" class="call-to-action light-bg">
    <div class="container">
        <h3>Você não está sozinha(o). Busque Ajuda!</h3>
        <div class="cards-ajuda">

            <div class="card">
                <h4>CVV - Centro de Valorização da Vida</h4>
                <p>Atendimento voluntário e gratuito, 24 horas por dia, todos os dias da semana. Sigiloso.</p>
                <a href="tel:188" class="btn-card">Ligue 188</a>
                <a href="https://www.cvv.org.br/" target="_blank" class="btn-card">Site do CVV</a>
            </div>

            <div class="card">
                <h4>CAPS - Centro de Atenção Psicossocial</h4>
                <p>Serviços de saúde mental públicos e gratuitos.</p>
                <a href="#" class="btn-card">Encontre um CAPS</a>
            </div>

            <div class="card">
                <h4>Urgências e emergências</h4>
                <p>Em casos de emergência, procure um pronto atendimento médico ou hospitalar.</p>
                <a href="tel:192" class="btn-card">SAMU 192</a>
            </div>

        </div>
    </div>
</section>
```

### Revisão do HTML: 


Após realizar as etapas anteriores, esse será o código HTML completo do seu site: 

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

        <section id="sobre" class="info-section">
            <div class="container">
                <h3>O que é o Setembro Amarelo?</h3>
                <div class="sobre-content">
                    <div class="sobre-texto">
                        <p>O Setembro Amarelo é uma campanha de prevenção ao suicídio, com o objetivo direto de alertar a população sobre a realidade do suicídio e suas formas de prevenção. A campanha acontece durante o mês de setembro, mas a conscientização é para o ano todo.</p>
                        <p>É um movimento iniciado no Brasil em 2015 pelo Centro de Valorização da Vida (CVV), Conselho Federal de Medicina (CFM) e Associação Brasileira de Psiquiatria (ABP).</p>
                    </div>
                    <div class="sobre-imagem">
                        <img src="images/grupo-amigos.png" alt="Duas pessoas se consolando com um abraço, simbolizando apoio e empatia.">
                    </div>
                </div>

                <div class="video-container">
                    <p>Assista ao vídeo da campanha do CVV para entender melhor a importância de falar.</p>
                    <iframe width="560" height="315"
                    src="https://www.youtube-nocookie.com/embed/7YzmGnMDNvk?rel=0"
                    title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                    referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
                </div>
            </div>
        </section>

        <section id="ajuda" class="call-to-action light-bg">
            <div class="container">
                <h3>Você não está sozinha(o). Busque Ajuda!</h3>
                <div class="cards-ajuda">

                    <div class="card">
                        <h4>CVV - Centro de Valorização da Vida</h4>
                        <p>Atendimento voluntário e gratuito, 24 horas por dia, todos os dias da semana. Sigiloso.</p>
                        <a href="tel:188" class="btn-card">Ligue 188</a>
                        <a href="https://www.cvv.org.br/" target="_blank" class="btn-card">Site do CVV</a>
                    </div>

                    <div class="card">
                        <h4>CAPS - Centro de Atenção Psicossocial</h4>
                        <p>Serviços de saúde mental públicos e gratuitos.</p>
                        <a href="#" class="btn-card">Encontre um CAPS</a>
                    </div>

                    <div class="card">
                        <h4>Urgências e emergências</h4>
                        <p>Em casos de emergência, procure um pronto atendimento médico ou hospitalar.</p>
                        <a href="tel:192" class="btn-card">SAMU 192</a>
                    </div>

                </div>
            </div>
        </section>

    </main>

    <!-- Continua abaixo os outros códigos HTML -->

</body>
</html>
```


## Estilizando a seção "Ajuda" com CSS

Com a estrutura HTML pronta, vamos ao `style.css` para criar o visual elegante dos nossos cards.

### Passo 1: Estilos gerais da seção

Primeiro, vamos definir a cor de fundo suave da nossa seção usando a classe `light-bg`. Adicione o seguinte código no final do seu `style.css`:

```css
.light-bg {
    background-color: var(--light-bg); /* Usando nossa variável de cor para fundo claro */
}
```

Agora, vamos estilizar o título da nossa nova seção. Aqui, temos uma ótima oportunidade de melhorar nosso código.

#### O Princípio DRY (Don't Repeat Yourself - Não se Repita)

Analisando o layout/design do site notamos que o estilo do nosso novo título na área de "Ajuda" (`.call-to-action h3`) é idêntico ao estilo do título da seção anterior "Sobre" (`.info-section h3`). 

Em vez de copiar e colar o código, o que gera duplicidade, vamos agrupar os seletores.

O CSS nos permite aplicar o mesmo bloco de estilos a múltiplos seletores, bastando separá-los por uma vírgula (`,`).

- Encontre a regra de estilo para `.info-section h3` que você já escreveu no seu `style.css`.

- Adicione o novo seletor `.call-to-action h3` ao lado dele, separado por uma vírgula.

O resultado ficará assim:

```css
/* Estilos para os títulos de TODAS as nossas seções de informação */
.info-section h3,
.call-to-action h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2em;
    color: var(--dark-violet);
    margin-bottom: 40px;
}
```

Agora temos um código de fácil manutenção. Por exemplo, se amanhã decidirmos que todos os títulos de seção devem ser maiores, só precisamos mudar o `font-size` em um único lugar, e a mudança será aplicada a todas as seções instantaneamente.


### Passo 2: Alinhando os cards com Flexbox

Agora, vamos usar o Flexbox no nosso agrupador `.cards-ajuda` para alinhar os cards. Adicione o código abaixo:

```css
.cards-ajuda {
    display: flex;             /* Ativa o layout flexível */
    justify-content: center;   /* Centraliza o conjunto de cards na página */
    gap: 30px;                 /* Cria um espaço de 30px entre cada card */
    margin-top: 40px;
}
```

### Passo 3: O visual do card individual (`.card`)

Vamos estilizar a "caixa" de cada card para que ela tenha a aparência clássica: bordas arredondadas, sombra e um fundo branco.

Adicione o estilo para a classe `.card`:

```css
.card {
    background-color: var(--white);
    border-radius: 8px;                          /* Cantos arredondados */
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);    /* Sombra suave para dar profundidade */
    padding: 30px;                               /* Espaçamento interno generoso */
    width: 300px;                                /* Largura fixa para cada card */
    text-align: center;
    transition: transform 0.3s ease;             /* Animação suave para o efeito hover */
}
```

### Passo 4: Adicionando interatividade ao card (`:hover`)

Vamos fazer o card "saltar" levemente quando o mouse passar por cima. Adicione o estilo para o estado `:hover`:

```css
.card:hover {
    transform: translateY(-5px); /* Move o card 5px para cima */
}
```

### Passo 5: Estilizando o conteúdo interno dos cards

Com nossos cards já alinhados e com uma aparência básica, o próximo passo é organizar o conteúdo dentro deles. Vamos ajustar os títulos, os parágrafos e, principalmente, transformar os links em botões funcionais e atraentes.

#### Ajustando os textos (título e parágrafo)

Primeiro, vamos cuidar da tipografia para criar uma hierarquia visual clara, onde o título se destaca e o parágrafo é fácil de ler. Adicione o seguinte código ao seu `style.css`:

```css
/* Estiliza o título de nível 4 dentro de cada card */
.card h4 {
    font-family: 'Montserrat', sans-serif; /* Usa a mesma fonte dos títulos principais para manter a consistência */
    color: var(--dark-violet);
    margin-bottom: 15px; /* Cria um espaço abaixo do título, separando-o do texto */
    font-size: 1.3em;
}

/* Estiliza o parágrafo dentro de cada card */
.card p {
    font-size: 0.95em; /* Deixa o texto um pouco menor que o padrão para caber bem no card */
    color: var(--text-color);
    margin-bottom: 20px; /* Cria um espaço maior abaixo do texto, preparando para os botões */
}
```

#### Transformando links em botões (`.btn-card`)

Agora, a parte mais importante: vamos transformar as tags `<a>` (links) em botões visualmente claros e clicáveis. Adicione o bloco de estilos para a classe `.btn-card`:

```css
.btn-card {
    display: block;
    background-color: var(--primary-color);
    color: var(--dark-violet);
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
    margin-top: 10px;
    transition: background-color 0.3s ease;
}
```

**Explicação:**

- `display: block;`: Esta é a regra mais importante aqui. Por padrão, links são elementos inline (se comportam como texto). Ao mudarmos para block, forçamos o link a se comportar como uma "caixa": ele passa a ocupar sua própria linha, permitindo que os botões fiquem empilhados verticalmente (como no card do CVV).

- `padding: 10px 20px;`: Adiciona o espaçamento interno que dá "corpo" ao botão, tornando a área clicável maior.

- `text-decoration: none;`: Remove o sublinhado azul padrão que todo link possui.

- `margin-top: 10px;`: Garante um pequeno espaço acima de cada botão, para que não fiquem colados um no outro.

- `transition: ...`: Prepara o botão para uma animação suave. Sem isso, qualquer efeito :hover seria instantâneo e "duro".

#### Adicionando o efeito de interatividade (`:hover`)

Um bom botão deve dar um feedback visual quando o usuário interage com ele. Vamos fazer com que ele mude de cor ao passar o mouse por cima.
Adicione o código para o estado `:hover` do botão:

```css
.btn-card:hover {
    background-color: #e6b300; /* Um tom de amarelo um pouco mais escuro */
}
```

**Explicação:** A pseudo-classe `:hover` aplica o estilo somente quando o cursor do mouse está sobre o elemento. Graças à propriedade `transition` que definimos antes, essa mudança de cor acontecerá de forma suave em 0.3 segundos.


### Revisão do Código CSS

Ao final da execução desse tutorial, o código CSS completo do site estará assim: 

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

.info-section {
    padding: 80px 0; /* Espaçamento interno para a seção "respirar" */
    text-align: center; /* Centraliza o título h3 por padrão */
}

.info-section h3,
.call-to-action h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2em;
    color: var(--dark-violet); /* Usando nossa variável de cor */
    margin-bottom: 40px; /* Espaço abaixo do título */
}

.sobre-content {
    display: flex;          /* Ativa o layout flexível */
    align-items: center;    /* Alinha o texto e a imagem verticalmente no centro */
    gap: 40px;              /* Cria um espaço de 40px entre as duas colunas */
    text-align: left;       /* Alinha o texto dos parágrafos à esquerda */
    margin-top: 40px;
}

.sobre-texto, .sobre-imagem {
    flex: 1; /* Faz com que cada coluna (texto e imagem) ocupe o mesmo espaço disponível. */
}

.sobre-imagem img {
    width: 100%; /* Faz a imagem ocupar 100% da largura da sua coluna. */
    border-radius: 8px; /* Cantos arredondados */
    box-shadow: 0 4px 15px rgba(0,0,0,0.1); /* Sombra sutil para dar profundidade */
}

.video-container {
    position: relative; /* Define o contexto para o posicionamento do iframe */
    /* A técnica da proporção 16:9: (9 / 16 * 100) = 56.25% */
    padding-bottom: 56.25%; 
    height: 0; /* A altura será definida pelo padding-bottom */
    overflow: hidden; /* Garante que nada escape do container */
    max-width: 100%;
    margin-top: 50px; /* Cria um espaço acima do vídeo */
    border-radius: 8px;
}

.video-container iframe {
    position: absolute; /* Posiciona o vídeo em relação ao container */
    top: 0;
    left: 0;
    width: 100%; /* Faz o vídeo ocupar toda a largura do container */
    height: 100%; /* Faz o vídeo ocupar toda a altura do container */
}

.light-bg {
    background-color: var(--light-bg); /* Usando nossa variável de cor para fundo claro */
}

.cards-ajuda {
    display: flex;             /* Ativa o layout flexível */
    justify-content: center;   /* Centraliza o conjunto de cards na página */
    gap: 30px;                 /* Cria um espaço de 30px entre cada card */
    margin-top: 40px;
}

.card {
    background-color: var(--white);
    border-radius: 8px;                          /* Cantos arredondados */
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);    /* Sombra suave para dar profundidade */
    padding: 30px;                               /* Espaçamento interno generoso */
    width: 300px;                                /* Largura fixa para cada card */
    text-align: center;
    transition: transform 0.3s ease;             /* Animação suave para o efeito hover */
}

.card:hover {
    transform: translateY(-5px); /* Move o card 5px para cima */
}

.card h4 {
    font-family: 'Montserrat', sans-serif;
    color: var(--dark-violet);
    margin-bottom: 15px;
    font-size: 1.3em;
}

.card p {
    font-size: 0.95em;
    color: var(--text-color);
    margin-bottom: 20px;
}

.btn-card {
    display: block; /* Faz os botões ocuparem a largura toda e ficarem um sobre o outro */
    background-color: var(--primary-color);
    color: var(--dark-violet);
    padding: 10px 20px;
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
    margin-top: 10px;
    transition: background-color 0.3s ease;
}

.btn-card:hover {
    background-color: #e6b300; /* Um tom de amarelo um pouco mais escuro */
}
```


## Conclusão

Parabéns! Você construiu uma seção de cards completa e profissional.
Atualize o navegador e veja como a página está ganhando forma! Compare com o site de exemplo: [https://inspiradanacomputacao.com/setembro-amarelo/](https://inspiradanacomputacao.com/setembro-amarelo/)
