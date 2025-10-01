# Tutorial: Construindo a seção "Sobre" (conteúdo e mídia)

Com o topo do site pronto, o próximo passo é criar a seção que apresenta a campanha. Aqui, vamos aprender a criar um dos layouts mais úteis e comuns na web: um bloco de texto alinhado ao lado de uma imagem. Além disso, vamos aprender a técnica correta para incorporar um vídeo do YouTube de forma responsiva.

Ao final desse tutorial, teremos construído essa área do [site setembro amarelo](https://inspiradanacomputacao.com/setembro-amarelo/): 
<img width="1233" height="807" alt="Captura de Tela 2025-10-01 às 20 24 32" src="https://github.com/user-attachments/assets/6abcddf3-744b-435f-9489-d78ccdd83faa" />

**Nosso objetivo:** Construir a seção "Sobre" com layout de duas colunas e um vídeo.

**Conceitos que vamos aprender:** Reforçar o uso de Flexbox, incorporar mídias (`<img>`, `<iframe>`) e a técnica profissional para vídeos responsivos.

Vamos continuar nosso projeto no ponto em que paramos.

## A Estrutura HTML da seção "Sobre"

Vamos adicionar o código desta nova seção no `index.html`, logo após o fechamento da `<section id="inicio" class="hero">`.


### Passo 1: A estrutura principal da seção

Toda nova área do site começa com uma tag `<section>`. Vamos criar a nossa e já adicionar o título principal.

Ainda dentro da tag `<main>`, adicione o código abaixo após o fechamento da `section` de inicio:

```html
<section id="sobre" class="info-section">
    <div class="container">
        <h3>O que é o Setembro Amarelo?</h3>
    </div>
</section>
```

#### Explicação: 

- `<section id="sobre"...>`: O `id="sobre"` é o que permite que o link "Sobre" do menu principal role a página diretamente para esta área.

- `class="info-section"`: Usamos uma classe genérica que poderá ser reutilizada para estilizar outras seções de texto do site, mantendo a consistência.

- `<h3>`: Como `<h2>` foi usado no Hero (área de destaque), usamos `<h3>` para o título da seção, mantendo a hierarquia correta de títulos.
  

### Passo 2: O layout de duas colunas (texto e imagem)


Agora, vamos criar a estrutura que nos permitirá ter o texto na esquerda e a imagem na direita. A chave para isso é criar um "agrupador" (wrapper) que conterá as duas colunas.

Na pasta `images` adicione a foto: [https://www.gruposelpe.com.br/wp-content/uploads/2022/08/setembro-amarelo-nas-empresas-como-apoiar-essa-campanha.png](https://www.gruposelpe.com.br/wp-content/uploads/2022/08/setembro-amarelo-nas-empresas-como-apoiar-essa-campanha.png)

Dentro da div `container` que criamos no passo anterior, logo após o `<h3>`, adicione a seguinte estrutura:


```html
<div class="sobre-content">
    <div class="sobre-texto">
        <p>O Setembro Amarelo é uma campanha de prevenção ao suicídio, com o objetivo direto de alertar a população sobre a realidade do suicídio e suas formas de prevenção. A campanha acontece durante o mês de setembro, mas a conscientização é para o ano todo.</p>
        <p>É um movimento iniciado no Brasil em 2015 pelo Centro de Valorização da Vida (CVV), Conselho Federal de Medicina (CFM) e Associação Brasileira de Psiquiatria (ABP).</p>
    </div>
    <div class="sobre-imagem">
        <img src="images/grupo-amigos.png" alt="Duas pessoas se consolando com um abraço, simbolizando apoio e empatia.">
    </div>
</div>
```

#### Explicação: 

- `<div class="sobre-content">`: Esta é a nossa div "pai". No CSS, vamos transformá-la em um container Flexbox para alinhar seus filhos (.sobre-texto e .sobre-imagem) lado a lado.

- `<div class="sobre-texto">` e `<div class="sobre-imagem">`: Criamos "caixas" dedicadas para o texto e para a imagem. Isso nos dá controle total para dizer, por exemplo, "cada uma dessas caixas deve ocupar 50% do espaço disponível".


### Passo 3: A estrutura para o vídeo responsivo

Por fim, vamos adicionar um vídeo do YouTube. Para que ele se ajuste a diferentes tamanhos de tela, também o colocaremos dentro de um "agrupador" específico para ele.

Ainda na `<div class="container">`, após o fechamento da div `class="sobre-content"`, adicione o bloco do vídeo:

```html
<div class="video-container">
    <p>Assista ao vídeo da campanha do CVV para entender melhor a importância de falar.</p>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/7YzmGnMDNvk?rel=0" title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>
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

                <br>

                <div class="video-container">
                    <p>Assista ao vídeo da campanha do CVV para entender melhor a importância de falar.</p>

                    <iframe width="560" height="315"
                    src="https://www.youtube-nocookie.com/embed/7YzmGnMDNvk?rel=0"
                    title="YouTube video player" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                    referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

                </div>
            </div>
        </section>

    </main>

    <!-- Continua abaixo o HTML das outras áreas do site... -->

</body>
</html>



```

## Estilizando a seção "Sobre" com CSS

Com o HTML pronto, vamos ao `style.css` para criar o visual desta seção.

### Passo 1: Estilos gerais da seção

Vamos criar um estilo base para nossas seções de informação. Se você já criou essa classe em outro momento, pode apenas revisar.

Adicione o seguinte código ao seu `style.css`:

```css
.info-section {
    padding: 80px 0; /* Espaçamento interno para a seção "respirar" */
    text-align: center; /* Centraliza o título h3 por padrão */
}

.info-section h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2em;
    color: var(--dark-violet); /* Usando nossa variável de cor */
    margin-bottom: 40px; /* Espaço abaixo do título */
}
```

### Passo 2: Criando as duas colunas com flexbox

Agora, vamos transformar nosso .sobre-content em um layout de duas colunas. Adicione o código abaixo:


```css
.sobre-content {
    display: flex;          /* Ativa o layout flexível */
    align-items: center;    /* Alinha o texto e a imagem verticalmente no centro */
    gap: 40px;              /* Cria um espaço de 40px entre as duas colunas */
    text-align: left;       /* Alinha o texto dos parágrafos à esquerda */
    margin-top: 40px;
}
```

### Passo 3: Ajustando o tamanho das colunas e a imagem

Vamos fazer com que cada coluna ocupe metade do espaço e estilizar a imagem. Adicione os seguintes estilos:

```css

.sobre-texto, .sobre-imagem {
    flex: 1; /* Faz com que cada coluna (texto e imagem) ocupe o mesmo espaço disponível. */
}

.sobre-imagem img {
    width: 100%; /* Faz a imagem ocupar 100% da largura da sua coluna. */
    border-radius: 8px; /* Cantos arredondados */
    box-shadow: 0 4px 15px rgba(0,0,0,0.1); /* Sombra sutil para dar profundidade */
}
```

**Conceito-chave**: `flex: 1` é um atalho poderoso. Ao aplicá-lo a todos os filhos de um container flex, ele distribui o espaço igualmente entre eles.


### Passo 4: A técnica do vídeo responsivo

Um `iframe` do YouTube não se ajusta ao tamanho da tela por padrão. Vamos usar uma técnica de CSS muito comum para resolver isso.


Adicione o código abaixo. Preste atenção nos comentários, eles explicam a "mágica".

```css
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
```

### Conclusão

Excelente trabalho! Você acabou de construir uma das seções mais importantes e versáteis do site.
Atualize o navegador e veja como a página está ganhando forma!
