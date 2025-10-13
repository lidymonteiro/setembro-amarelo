# Tutorial: Construindo a responsividade do site e primeira entrega ao cliente

A responsividade é crucial para que o site se adapte e tenha uma boa aparência em diversos dispositivos, desde celulares até telas de desktop grandes. O CSS que construimos até aqui já está mais focado em desktop, então usaremos o `max-width` para aplicar estilos a telas menores.


## Índice



- [Como usar este tutorial](#como-usar-este-tutorial) 
- [Passo 0: Código HTML e CSS3 correto do site sem responsividade](https://github.com/lidymonteiro/setembro-amarelo/blob/main/docs/aula08.md#passo-0-c%C3%B3digo-html-e-css3-completo-do-site-sem-responsividade)
  - [Código HTML completo da página](https://github.com/lidymonteiro/setembro-amarelo/blob/main/docs/aula08.md#passo-3-publica%C3%A7%C3%A3o-da-primeira-vers%C3%A3o-para-feedback)
  - [Código CSS completo da página](#codigo-css-completo-da-pagina)
- [Passo 1: Ajustes importantes no CSS existente em body e .container](#passo-1-ajustes-importantes-no-css-existente-em-body-e-container)
- [Passo 2: Definindo os breakpoints com Media Queries](#passo-2-definindo-os-breakpoints-com-media-queries)
- [Passo 3: Deploy e entrega da primeira versão para feedback do cliente](https://github.com/lidymonteiro/setembro-amarelo/blob/main/docs/aula08.md#passo-3-publica%C3%A7%C3%A3o-da-primeira-vers%C3%A3o-para-feedback)


## Como usar este tutorial:
**Entenda e revise a Lógica:** Leia as explicações para cada bloco de código. Perceba como os estilos são "cascateados" (herdados e sobrescritos) de telas maiores para menores.

***Teste no Navegador:** Abra seu site em um navegador (como Chrome ou Firefox) e use as ferramentas de desenvolvedor (clique direito > "Inspecionar" ou F12). Use a função de "Device Mode" (ícone de celular/tablet) para simular diferentes tamanhos de tela. Redimensione a janela do navegador para ver os breakpoints em ação.

**Ajuste fino:** A responsividade é um processo iterativo. Você pode precisar ajustar os `font-size`, `padding`, `margin` ou `gap` em alguns lugares específicos para que o layout fique perfeito em todos os tamanhos de tela que você deseja suportar.

HTML Semântico: Lembre-se que um HTML bem estruturado e semântico (usando `<header>`, `<nav>`, `<section>`, `<footer>` etc.) facilita muito a aplicação de estilos responsivos.

Ao seguir este guia e entender cada linha de código, você terá um controle muito maior sobre como seu site aparece em qualquer dispositivo.


**Conceitos principais**:

- **Media Queries:** São regras CSS que aplicam estilos específicos apenas se certas condições forem verdadeiras (por exemplo, a largura da tela).

- `max-width`: Usado em media queries para aplicar estilos a telas até uma determinada largura.

- **Flexbox:** Ótimo para layouts unidimensionais (linha ou coluna), como cabeçalhos, rodapés ou grupos de cards.

- **Grid CSS:** Excelente para layouts bidimensionais complexos, como galerias ou seções com múltiplos itens.



## Passo 0: Código HTML e CSS3 completo do site sem responsividade 

Antes de aplicar a responsividade, garanta que seu projeto já esteja com a estrutura base correta — HTML organizado, classes e IDs consistentes e o CSS das etapas anteriores funcionando.

Para fins didáticos e para evitar qualquer bug desapercebido, abra o `index.html` e o `style.css` e substitua seus conteúdos pelos códigos a seguir. Assim, você parte de uma versão estável e comprovadamente funcional do site.

Após substituir os códigos, abra o seu site no navegador e compare visualmente com o modelo [https://inspiradanacomputacao.com/setembro-amarelo/](https://inspiradanacomputacao.com/setembro-amarelo/) para verificar se está semelhante (áreas, espaçamento, titulo, etc). Caso esteja, siga para a próxima etapa. 


### Código HTML completo da página: 


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

        <section id="como-ajudar" class="info-section">
            <div class="container">
                <h3>Como posso ajudar?</h3>
                <div class="grid-ajuda">
                    <div class="item-ajuda">
                        <h4>Ouça sem julgar</h4>
                        <p>Ofereça um ouvido atento e sem preconceitos. Mostre que você se importa.</p>
                    </div>
                    <div class="item-ajuda">
                        <h4>Incentive a busca por ajuda profissional</h4>
                        <p>Sugira que a pessoa converse com um psicólogo, psiquiatra ou médico.</p>
                    </div>
                    <div class="item-ajuda">
                        <h4>Mantenha contato</h4>
                        <p>Continue demonstrando apoio e acompanhando a pessoa, mesmo que de longe.</p>
                    </div>
                    <div class="item-ajuda">
                        <h4>Fique atento aos sinais</h4>
                        <p>Mudanças de humor, isolamento, perda de interesse em atividades. Não ignore.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="recursos" class="resources-section light-bg">
            <div class="container">
                <h3>Recursos adicionais</h3>
                <ul>
                    <li><a href="https://setembroamarelo.org.br/" target="_blank">Campanha Setembro Amarelo</a></li>
                    <li><a href="https://www.quemcuidadocuida.com.br/" target="_blank">Quem Cuida Cuida</a></li>
                    <li><a href="https://www.paho.org/pt/topicos/saude-mental" target="_blank">Opas - Saúde Mental</a></li>
                    <li><a href="https://www.unicef.org/brazil/saude-mental" target="_blank">UNICEF - Saúde Mental</a></li>
                </ul>

            
            </div>
           
        </section>

        <section id="contato" class="info-section">
            <div class="container">
                <h3>Contato</h3>
                <p>Que bom que você nos procurou. Como podemos te ajudar?</p>
                <form class="form-contato">
                    <div class="form-group">
                        <label for="nome">Seu nome (ou apelido)</label>
                        <input type="text" id="nome" name="nome" placeholder="Como podemos te chamar?" required>
                    </div>
                    <div class="form-group">
                        <label for="email">Seu E-mail (não será divulgado)</label>
                        <input type="email" id="email" name="email" placeholder="exemplo@email.com" required>
                    </div>
                    <div class="form-group">
                        <label for="mensagem">Sua mensagem</label>
                        <textarea id="mensagem" name="mensagem" rows="5" placeholder="Estamos prontos para ouvir. Escreva aqui sua mensagem." required></textarea>
                    </div>
                    <button type="submit" class="btn-form">Enviar mensagem</button>
                </form>
            </div>
        </section>

    </main>

    <footer>
        <div class="container">
            <p>&copy; 2025 Setembro Amarelo. Todos os direitos reservados. #VocêNãoEstáSozinho</p>
            <div class="social-media">
                <a href="#" target="_blank">Facebook</a>
                <a href="#" target="_blank">Instagram</a>
            </div>
        </div>
    </footer>

</body>
</html>
```



### Código CSS completo da página: 

```css
/* Importação de fontes - Exemplo do Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Open+Sans:wght@400;600&display=swap');

/* Variáveis CSS (bom para iniciantes entenderem a organização de cores) */
:root {
    --primary-color: #F7C948; /* Amarelo principal */
    --secondary-color: #333;
    --text-color: #555;
    --light-bg: #f9f9f9;
    --white: #fff;
    --dark-violet: #3d3dcd; /* Roxo escuro para contraste */
    --hero-light-yellow: #fbecbb;   /* NOVO! Amarelo muito claro, mas com mais cor que #FFFDE7 */
    --hero-lighter-yellow: #FFFFFF; /* Branco puro, mas pode ser um toque de amarelo mais claro ainda, ex: #FFFFF0 */
}

/* Reset básico para remover margens e paddings padrão do navegador */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /* Fundamental para o controle de layout */
}

body {
    font-family: 'Open Sans', sans-serif;
    line-height: 1.6; /* Espaçamento entre linhas para melhor leitura */
    color: var(--text-color);
    background-color: var(--white);
}

/* Container para centralizar o conteúdo e limitar a largura */
.container {
    width: 960px; /* Largura fixa para esta versão simples */
    margin: 0 auto; /* Centraliza o container na página */
    padding: 0 20px;
}


/* Wrapper que agrupa o ícone e o texto do logo */
.logo-wrapper {
    display: flex;           /* Alinha o ícone e o texto na mesma linha */
    align-items: center;     /* Centraliza-os verticalmente um em relação ao outro */
    gap: 8px;                /* Controla o ESPAÇO entre o ícone e o texto. Ajuste este valor! */
}

/* Estilização específica do ÍCONE (emoji) */
.logo-icon {
    font-size: 2em;          /* Tamanho do emoji */
    color: var(--primary-color); /* Cor do emoji (amarelo) */
    line-height: 1;          /* Ajuda a centralizar verticalmente */
}

/* Estilização específica do TEXTO do logo */
.logo-text {
    font-family: 'Open Sans', sans-serif; /* Use 'Open Sans' ou 'Montserrat' para os títulos, como sugerido antes */
    font-size: 1.3em;        /* Tamanho do texto */
    color: var(--primary-color); /* Cor do texto (amarelo) */
    margin: 0;               /* Remove margem padrão do h1 */
}

/* Header - Cabeçalho do site */
header {
    background-color: #242474;
    color: var(--white);
    padding: 10px 0;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra sutil */
}

header .container {
    display: flex; /* Usa Flexbox para alinhar logo e navegação na mesma linha */
    justify-content: space-between; /* Espaço entre o logo e a navegação */
    align-items: center; /* Alinha verticalmente no centro */
}

/* Navegação */
header nav ul {
    list-style: none; /* Remove os marcadores de lista */
    display: flex; /* Alinha os itens da navegação na mesma linha */
}

header nav ul li {
    margin-left: 25px; /* Espaçamento entre os itens da navegação */
    font-size: 15px;

}

header nav ul li a {
    color: var(--white);
    text-decoration: none; /* Remove o sublinhado dos links */
    font-weight: bold;
    transition: color 0.3s ease; /* Transição suave na cor ao passar o mouse */
}

header nav ul li a:hover {
    color: var(--primary-color); /* Altera a cor do link ao passar o mouse */
}


.hero-hashtag {
    font-family: 'Open Sans', sans-serif;
    font-size: 1.3em; /* Tamanho bom para destaque, não tão pequeno */
    font-weight: bold; /* Negrito forte para chamar atenção */
    color: var(--secondary-blue); /* Use o AZUL VIBRANTE para a hashtag */
    margin-bottom: 30px; /* Espaçamento maior para separá-la da descrição */
    margin-top: -10px; /* Puxa um pouco para perto do título, sem grudar */
    letter-spacing: 0.5px; /* Adiciona um pouco de espaço entre as letras */
}

/* Hero Section - Seção principal de destaque */
.hero {
    background: linear-gradient(0deg, rgb(0 0 0 / 65%), rgb(4 1 1 / 35%)), url(https://blog.unoeste.br/wp-content/uploads/2025/09/setembro-amarelo.jpg) center / cover no-repeat, linear-gradient(46deg, #e9d18b, #f7f3e7);
    color: var(--dark-violet); /* Cor do texto para contraste com o amarelo */
    text-align: center;
    padding: 100px 0;
}

.hero h2 {
    font-family: 'Montserrat', sans-serif;
    font-size: 3em;
    margin-bottom: 20px;
    color: var(--white);
}

.hero p {
    font-size: 1.2em;
    margin-bottom: 30px;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    color: var(--white);
}

.btn-cta {
    display: inline-block;
    background-color: var(--hero-light-yellow); /* Fundo com o amarelo claro da seção Hero */
    color: var(--secondary-blue); /* Texto em azul vibrante */
    padding: 15px 30px;
    text-decoration: none;
    border: 2px solid var(--secondary-blue); /* Borda sutil no azul */
    border-radius: 8px; /* Cantos mais arredondados para suavidade */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 0.3s ease; /* Transição para todas as propriedades */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra suave para dar profundidade */
}



.btn-cta:hover {
    background-color: var(--primary-color); /* Inverte as cores no hover */
    color: var(--primary-yellow); /* Texto amarelo no hover */
    transform: translateY(-2px); /* Efeito sutil de levantar */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Sombra um pouco mais forte no hover */
}


/* Seções de Conteúdo Geral */
.info-section, .call-to-action, .resources-section {
    padding: 80px 0;
    text-align: center;
}

.info-section h3, .call-to-action h3, .resources-section h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2em;
    color: var(--dark-violet);
    margin-bottom: 40px;
}

.info-section p {
    max-width: 800px;
    margin: 0 auto 20px auto;
    font-size: 1em;
    color: var(--secondary-color);
}

.light-bg {
    background-color: var(--light-bg);
}

/* Seção "Onde Buscar Ajuda?" (Cards) */
.cards-ajuda {
    display: flex; /* Usa Flexbox para os cards */
    justify-content: center; /* Centraliza os cards */
    gap: 30px; /* Espaçamento entre os cards */
    margin-top: 40px;
}

.card {
    background-color: var(--white);
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    padding: 30px;
    width: 300px; /* Largura fixa para cada card */
    text-align: center;
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-5px); /* Efeito sutil de levantar ao passar o mouse */
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
    display: block; /* Cada botão ocupa uma linha */
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
    background-color: #e6c200;
}

/* Seção "Como Posso Ajudar?" (Grid) */
.grid-ajuda {
    display: grid; /* Usa Grid para os itens de ajuda */
    grid-template-columns: repeat(4, 1fr); /* 4 colunas de tamanho igual */
    gap: 30px; /* Espaçamento entre os itens do grid */
    margin-top: 40px;
}

.item-ajuda {
    background-color: var(--white);
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    padding: 25px;
    text-align: center;
}

.item-ajuda h4 {
    font-family: 'Montserrat', sans-serif;
    color: var(--dark-violet);
    margin-bottom: 10px;
    font-size: 1.2em;
}

.item-ajuda p {
    font-size: 0.9em;
    color: var(--text-color);
}

/* Seção Recursos */
.resources-section ul {
    list-style: none; /* Remove marcadores de lista */
    padding: 0;
    margin-top: 30px;
    max-width: 600px; /* Limita a largura da lista */
    margin-left: auto;
    margin-right: auto;
}

.resources-section ul li {
    margin-bottom: 15px;
}

.resources-section ul li a {
    color: var(--dark-blue);
    text-decoration: none;
    font-size: 1.1em;
    font-weight: 600;
    transition: color 0.3s ease;
}

.resources-section ul li a:hover {
    color: var(--primary-color);
}

/* Estilo da Seção Sobre com Imagem */
.sobre-content {
    display: flex;
    align-items: center; /* Alinha verticalmente */
    gap: 40px; /* Espaço entre texto e imagem */
    text-align: left; /* Alinha o texto à esquerda */
    margin-top: 40px;
}

.sobre-texto, .sobre-imagem {
    flex: 1; /* Faz com que ambos ocupem 50% do espaço */
}

.sobre-imagem img {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

/* Estilo do Vídeo Responsivo */
.resources-section h4 {
    font-size: 1.5em;
    color: var(--dark-violet);
    margin-top: 40px;
}

.resources-section p {
    max-width: 600px;
    margin: 10px auto 30px auto;
}

.video-container {
    position: relative;
    padding-bottom: 56.25%; /* Proporção 16:9 (9 / 16 * 100) */
    height: 0;
    overflow: hidden;
    max-width: 100%;
    background: #000;
    margin: 0 auto;
    border-radius: 8px;
}

.video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}


form .btn-form { 
    display: inline-block;
    background-color: var(--primary-color); /* Fundo com o amarelo claro da seção Hero */
    color: var(--dark-violet);
    padding: 15px 30px;
    text-decoration: none;
    border: 2px solid var(--secondary-blue); /* Borda sutil no azul */
    border-radius: 8px; /* Cantos mais arredondados para suavidade */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 
}

form .btn-form:hover {
    background-color: var(--dark-violet); /* Inverte as cores no hover */
    color: var(--white); /* Texto amarelo no hover */
    transform: translateY(-2px); /* Efeito sutil de levantar */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Sombra um pouco mais forte no hover */
}

/* Estilo do Formulário de contato */
.form-contato {
    max-width: 600px;
    margin: 40px auto 0 auto;
    text-align: left;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: var(--secondary-color);
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: 'Open Sans', sans-serif;
    font-size: 1em;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 5px rgba(247, 201, 72, 0.5);
}

/* Footer - Rodapé do site */
footer {
    background-color: var(--secondary-color);
    color: var(--white);
    padding: 30px 0;
    text-align: center;
    font-size: 0.9em;
}

footer .container {
    display: flex; /* Usa Flexbox para alinhar conteúdo do footer */
    flex-direction: column; /* Coloca os itens um abaixo do outro */
    align-items: center; /* Centraliza horizontalmente */
    gap: 15px; /* Espaçamento entre os itens */
}

.social-media a {
    color: var(--white);
    text-decoration: none;
    margin: 0 10px;
    transition: color 0.3s ease;
}

.social-media a:hover {
    color: var(--primary-color);
}

```


## Passo 1: Ajustes importantes no CSS existente em `body` e `.container`

Antes de inlcuirmos as `Media Queries`, alguns ajustes no CSS que já temos são cruciais para a responsividade. Vamos acrescentar: 

**Etapa 1:** Em `*`: Vamos adicionar `box-sizing: border-box;` 

Código antes: 

```css
* {
    margin: 0;
    padding: 0;
}
```

Código depois: 

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /* Fundamental para o controle de layout */
}
```

**Explicação:** Quando criamos layouts em CSS, cada elemento é uma caixa. O `box-sizing` define como o tamanho dessa caixa é calculado. Sem `border-box` (padrão que já vem no navegador) a largura (width) vale só para o conteúdo.  Se você adicionar padding ou border, o elemento fica maior do que o valor definido. Com `box-sizing: border-box`, a largura já inclui o conteúdo, o padding e a border. Ou seja, a caixa mantém exatamente a largura que você definiu.

Lembre-se que em outra etapa do tutorial definimos `margin: 0;` `padding: 0;` em `*` parar zerar/resetar as margens e paddings padrão que os navegadores aplicam a diversos elementos (como h1, p, ul, etc.). Isso nos deu um "quadro em branco" limpo, onde temos controle total sobre o espaçamento, sem surpresas indesejadas do navegador.

**Etapa 2:** Em `.container` alterar `width` para `max-width`:


Em vez de definir uma largura fixa (`width: 960px;`), use `max-width: 960px;` no `.container` junto com um `padding: 0 20px;`.
Essa pequena mudança faz uma grande diferença na responsividade: o container se adapta automaticamente a telas menores, mas nunca ultrapassa 960px em telas grandes.


Código antes:

```css
.container {
    width: 960px;
    margin: 0 auto; 
    padding: 0 20px;
}

```

Código depois: 

```css
.container {
    max-width: 960px; /* Alterado para max-width para ser responsivo */
    margin: 0 auto;   /* Centraliza o container na página */
    padding: 0 20px;  /* Padding lateral para não grudar nas bordas em telas menores */
}
```


**Explicação:** 

- Em telas grandes: o `max-width` impede que o conteúdo fique largo demais, mantendo o design equilibrado.

- Em telas pequenas: o `container` automaticamente ocupa 100% da largura disponível (porque não há `width`/largura fixa), e o `padding` impede que o texto encoste nas bordas.


## Passo 2: Definindo os breakpoints com Media Queries:

Os `breakpoints` são os pontos onde o layout do seu site muda para se adaptar a diferentes tamanhos de tela. Usaremos dois principais: um para tablets (`992px`) e outro para celulares (`768px` e `480px`). Com os breakpoints definidos, podemos ajustar fontes, espaçamentos, colunas e outros elementos para manter tudo legível e bonito em qualquer dispositivo.


### Breakpoints mais utilizados

| Dispositivo / Situação | Largura máxima | Quando usar |
|-------------------------|----------------|--------------|
| **Monitores grandes**   | `1200px`       | Ajustes para telas largas (ex: desktops grandes) |
| **Tablets (horizontal)**| `992px`        | Ajustar grids, fontes e menus para tablets deitados |
| **Tablets (vertical)**  | `768px`        | Reorganizar colunas ou esconder elementos |
| **Celulares**           | `480px`        | Exibir tudo em uma coluna e aumentar áreas clicáveis (botões, etc) |


Esses valores são referências comuns, mas você pode ajustá-los conforme o design do projeto.


- Sintaxe básica (padrão de código): 

```css
@media (max-width: <TAMANHO>px) {
    /* Estilos CSS específicos para telas com largura IGUAL ou MENOR que <tamanho>px */
}
```

```css
@media (max-width: 768px) {
  /* Estilos aplicados quando a tela tiver 768px de largura ou menos */
}
```

Como ler esse código: *Aplique este CSS apenas quando a tela for menor ou igual a 768 pixels de largura.*


**Dica prática:** Comece definindo os breakpoints que fazem sentido para o seu conteúdo. Em vez de pensar em “tamanhos de dispositivos”, pense em pontos onde o layout quebra ou aperta, esses são os melhores lugares para adicionar um breakpoint.



### Etapa 1: Breakpoint para tablets e desktops menores (max-width: 992px)

Este breakpoint é focado para telas médias, como tablets em modo paisagem ou computadores com janelas de navegador reduzidas. Ele garante que o layout continue legível e equilibrado mesmo quando a largura da tela não é tão ampla quanto a de um monitor grande.

Para começar, vamos colocar no final do arquivo `style.css` nossos ajustes dentro de uma `@media query` e definir o primeiro breakpoint:


```css
@media (max-width: 992px) {
    /* Todos os estilos que seguem abaixo serão adicionados/aplicados APENAS aqui */

}
```

Adicione dentro do media query que acabamos de criar os ajustes necessários para que os estilos de classes e tags que definimos antes se adapte ao tamanho de tablets e desktops menores:


1. Otimizando o contêiner principal (`.container`)

Adicionar a classe `.container` ajustada para que ele use toda a largura disponível na tela, mas com um respiro nas laterais:

```css
.container {
    width: 100%; /* Faz com que o contêiner ocupe 100% da largura da tela. */
    padding: 0 15px; /* Adiciona um espaçamento de 15px nas laterais, garantindo que o conteúdo não "cole" nas bordas da tela. */
}
```

Resultado: Seu código deve ficar assim

```css
@media (max-width: 992px) {

    .container {
        width: 100%; /* Faz com que o contêiner ocupe 100% da largura da tela. */
        padding: 0 15px; /* Adiciona um espaçamento de 15px nas laterais, garantindo que o conteúdo não "cole" nas bordas da tela. */
    }

    /* Continue adicionando aqui os próximos códigos que adaptarão as outras partes do site */


}
```

2. Reorganizando o cabeçalho (`header`)

O cabeçalho precisava de uma reestruturação para acomodar o logo e a navegação de forma mais compacta:

```css
header .container {
    flex-direction: column; /* Deixa os itens do cabeçalho (logo e navegação) na vertical, um abaixo do outro (empilhados). */
    gap: 15px; /* Adiciona um espaçamento de 15px entre o logo e a navegação. */
}
header nav ul {
    justify-content: center; /* Centraliza horizontalmente os itens do menu de navegação (Home, Sobre, etc.). */
    flex-wrap: wrap; /* Permite que os itens do menu quebrem para a próxima linha se não houver espaço suficiente. */
    gap: 15px; /* Define um espaçamento de 15px entre cada item do menu. */
}
header nav ul li {
    margin-left: 0; /* Remove a margem lateral que os itens do menu tinham, deixando o `gap` controlar o espaçamento. */
}
```


3. Ajustando a Seção Hero (banner principal)

O título e o parágrafo da seção Hero foram um pouco reduzidos para melhor se encaixar em telas menores:

```css
.hero h2 {
    font-size: 2.5em; /* Reduz o tamanho da fonte do título principal para 2.5 vezes o tamanho base. */
}
.hero p {
    font-size: 1.1em; /* Reduz o tamanho da fonte do parágrafo para 1.1 vezes o tamanho base. */
}
```



4. Organizando o conteúdo da seção "Sobre" na vertical

Para evitar que a imagem e o texto fiquem muito apertados lado a lado, vamos deixá-los na vertical, um abaixo do outro (empilhados):

```css
.sobre-content {
    flex-direction: column; /* Faz com que o texto e a imagem fiquem um abaixo do outro (empilhados). */
    gap: 30px; /* Adiciona um espaçamento de 30px entre o texto e a imagem. */
    text-align: center; /* Centraliza o texto para um visual mais limpo. */
}
.sobre-texto, .sobre-imagem {
    flex: none; /* Remove a regra que fazia texto e imagem dividirem o espaço igualmente (50/50). */
    width: 100%; /* Cada elemento (texto e imagem) agora ocupa 100% da largura disponível. */
}
.sobre-imagem img {
    height: auto; /* Garante que a imagem mantenha suas proporções originais ao se adaptar à nova largura. */
}
```

5. Adaptando os cards da seção "Onde Buscar Ajuda" para duas colunas

Em vez de três cards em uma linha, agora eles se organizarão em duas colunas, quebrando para a próxima linha quando necessário:

```css
.cards-ajuda {
    flex-wrap: wrap; /* Permite que os cards quebrem para a linha de baixo se não houver espaço suficiente. */
    justify-content: center; /* Centraliza os cards horizontalmente. */
    gap: 20px; /* Reduz o espaçamento entre os cards para 20px. */
}
.card {
    width: calc(50% - 10px); /* Cada card ocupa aproximadamente metade da largura da tela, com um pequeno espaço entre eles (`50%` da largura total - `10px` para o `gap` de `20px`). */
    max-width: 300px; /* Mantém uma largura máxima para que os cards não fiquem excessivamente grandes em telas um pouco maiores. */
}
```

6. Ajustando o Grid da seção "Como Posso Ajudar" para duas colunas

Similar aos cards, o grid de 4 colunas foi reconfigurado para 2 colunas:

```css
.grid-ajuda {
    grid-template-columns: repeat(2, 1fr); /* Organiza os itens em 2 colunas de larguras iguais. */
    gap: 20px; /* Reduz o espaçamento entre os itens do grid para 20px. */
}
.item-ajuda {
    padding: 20px; /* Reduz o espaçamento interno dos itens do grid. */
}
```


7. Diminuindo os títulos de seções

```css
.info-section h3, .call-to-action h3, .resources-section h3 {
    font-size: 2em; /* Reduz o tamanho da fonte para 2 vezes o tamanho base. */
}
```


8. Pequenos ajustes no formulário

Garantimos que o formulário tenha um espaçamento adequado para não encostar nas bordas:

```css
.form-contato {
    padding: 15px; /* Adiciona um espaçamento interno de 15px para o formulário. */
}
```


Ao final das etapas acima, esse será o código do breakpoint `(max-width: 992px`:

```css
@media (max-width: 992px) {

    .container {
        width: 100%; /* Permite que o container ocupe a largura total */
        padding: 0 15px; /* Reduz padding lateral para telas menores */
    }

    /* Header: Alinha a navegação verticalmente se não couber */
    header .container {
        flex-direction: column;
        gap: 15px;
    }
    header nav ul {
        justify-content: center; /* Centraliza itens do menu */
        flex-wrap: wrap; /* Permite quebrar linha se o menu for muito grande */
        gap: 15px; /* Espaçamento entre itens */
    }
    header nav ul li {
        margin-left: 0; /* Remove margem lateral quebrava o layout */
    }

    /* Hero Section: Ajustes de fonte */
    .hero h2 {
        font-size: 2.5em;
    }
    .hero p {
        font-size: 1.1em;
    }

    /* Seção "Sobre": Empilha texto e imagem */
    .sobre-content {
        flex-direction: column; /* Empilha texto e imagem verticalmente */
        gap: 30px;
        text-align: center; /* Centraliza o texto */
    }
    .sobre-texto, .sobre-imagem {
        flex: none; /* Remove a flexibilidade de 50% */
        width: 100%; /* Ocupa a largura total */
    }
    .sobre-imagem img {
        height: auto; /* Garante que a imagem mantenha sua proporção */
    }

    /* Cards de Ajuda: 2 colunas */
    .cards-ajuda {
        flex-wrap: wrap; /* Permite que os cards quebrem para a próxima linha */
        justify-content: center; /* Centraliza os cards */
        gap: 20px; /* Reduz o espaçamento */
    }
    .card {
        width: calc(50% - 10px); /* 2 colunas, subtraindo metade do gap */
        max-width: 300px; /* Mantém um max-width para não esticar demais */
    }

    /* Grid de Ajuda: 2 colunas */
    .grid-ajuda {
        grid-template-columns: repeat(2, 1fr); /* 2 colunas */
        gap: 20px;
    }
    .item-ajuda {
        padding: 20px;
    }

    /* Títulos de Seção */
    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 2em;
    }

    /* Formulário */
    .form-contato {
        padding: 15px;
    }

}
```


### Etapa 2: Breakpoint para Celulares (`max-width: 768px`)

Este bloco de código é ativado quando a largura da tela é de `768` pixels ou menos. Pense em celulares maiores ou tablets em modo retrato. Os estilos aqui sobrescrevem os estilos definidos para `992px` e os estilos padrão de desktop.

Vamos adicionar mais um breakpoint ao final de `style.css` e adaptar o que for necessário para esse tamanho de tela (`max-width: 768px`):

```css
@media (max-width: 768px) {
    /* 1. Ajustes do Header (Logo e Ícone) */
    .logo-text {
        font-size: 1.2em; /* Reduz o tamanho da fonte do texto do logo */
    }
    .logo-icon {
        font-size: 1.8em; /* Reduz o tamanho da fonte do ícone do logo */
    }

    header nav ul {
        flex-direction: column; /* Altera a navegação para uma lista empilhada verticalmente */
        align-items: center; /* Centraliza os itens do menu horizontalmente */
        gap: 10px; /* Reduz o espaçamento entre os itens do menu */
        margin-top: 10px; /* Adiciona um pequeno espaçamento no topo do menu */
    }

    /* 2. Ajustes da Seção Hero */
    .hero {
        padding: 80px 0; /* Reduz o padding vertical da seção hero */
    }
    .hero h2 {
        font-size: 2em; /* Reduz ainda mais o tamanho da fonte do título principal */
        margin-bottom: 15px; /* Reduz o espaçamento abaixo do título */
    }
    .hero-hashtag {
        font-size: 1.1em; /* Ajusta o tamanho da fonte da hashtag */
        margin-bottom: 20px; /* Ajusta o espaçamento abaixo da hashtag */
    }
    .hero p {
        font-size: 1em; /* Reduz o tamanho da fonte do parágrafo */
        margin-bottom: 25px; /* Ajusta o espaçamento abaixo do parágrafo */
    }
    .btn-cta {
        padding: 12px 25px; /* Reduz o padding do botão de CTA */
        font-size: 1em; /* Reduz o tamanho da fonte do botão */
    }

    /* 3. Ajustes de Seções de Conteúdo Geral */
    .info-section, .call-to-action, .resources-section {
        padding: 60px 0; /* Reduz o padding vertical das seções de conteúdo */
    }

    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 1.8em; /* Reduz ainda mais o tamanho da fonte dos títulos das seções */
        margin-bottom: 30px; /* Reduz o espaçamento abaixo dos títulos */
    }

    /* 4. Ajustes da Seção "Cards de Ajuda" */
    .cards-ajuda {
        /* Se você não tem o menu hambúrguer, esta seção aqui pode ter `grid-template-columns: 1fr;`
           para os cards ficarem em coluna. Se tiver o hambúrguer, este bloco será diferente. */
        grid-template-columns: 1fr; /* Altera para apenas 1 coluna, cada card ocupará a largura total */
    }
    .card {
        width: 100%; /* Faz com que cada card ocupe a largura total disponível */
        max-width: none; /* Remove qualquer limitação de largura máxima, permitindo que o card se estique */
    }

    /* 5. Ajustes da Seção "Grid de Ajuda" */
    .grid-ajuda {
        grid-template-columns: 1fr; /* Altera para apenas 1 coluna, cada item ocupará a largura total */
    }
    .item-ajuda {
        padding: 15px; /* Reduz o padding interno dos itens do grid */
    }

    /* 6. Ajustes do Formulário de Contato */
    .form-contato {
        margin-top: 20px; /* Reduz o espaçamento superior do formulário */
        padding: 10px; /* Reduz o padding interno do formulário */
    }

    /* 7. Ajustes do Footer (Rodapé) */
    footer p, .social-media a {
        font-size: 0.85em; /* Reduz o tamanho da fonte do texto do rodapé e links de mídia social */
    }
}

```

### Etapa 3: Breakpoint para celulares pequenos (`max-width: 480px`)

Este bloco de código é ativado para telas muito pequenas, como celulares de modelos mais antigos ou quando o navegador está muito compactado.

Vamos adicionar mais um breakpoint ao final de `style.css` e adaptar o que for necessário para esse tamanho de tela (`max-width: 480px`):

```css
@media (max-width: 480px) {
    /* 1. Ajustes da Seção Hero */
    .hero h2 {
        font-size: 1.8em; /* Reduz o tamanho da fonte do título principal para telas muito pequenas */
    }
    .hero-hashtag {
        font-size: 1em; /* Ajusta o tamanho da fonte da hashtag */
    }
    .hero p {
        font-size: 0.9em; /* Reduz o tamanho da fonte do parágrafo */
    }
    .btn-cta {
        padding: 10px 20px; /* Reduz o padding do botão de CTA */
        font-size: 0.95em; /* Reduz o tamanho da fonte do botão */
    }

    /* 2. Ajustes de Títulos Gerais de Seções */
    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 1.6em; /* Reduz ainda mais o tamanho da fonte dos títulos das seções */
    }

    /* 3. Ajustes de Textos em Geral */
    .info-section p, .card p, .item-ajuda p, .resources-section ul li a, .form-group label {
        font-size: 0.9em; /* Reduz o tamanho da fonte de vários parágrafos e labels para otimizar o espaço */
    }
}
```


### Código CSS completo: 

Após adicionar os breakpoints e media query que aprendemos neste tutorial, esse será seu código CSS completo: 


```css
/* Importação de fontes - Exemplo do Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@700&family=Open+Sans:wght@400;600&display=swap');

/* Variáveis CSS (bom para iniciantes entenderem a organização de cores) */
:root {
    --primary-color: #F7C948; /* Amarelo principal */
    --secondary-color: #333;
    --text-color: #555;
    --light-bg: #f9f9f9;
    --white: #fff;
    --dark-violet: #3d3dcd; /* Roxo escuro para contraste */
    --hero-light-yellow: #fbecbb;   /* NOVO! Amarelo muito claro, mas com mais cor que #FFFDE7 */
    --hero-lighter-yellow: #FFFFFF; /* Branco puro, mas pode ser um toque de amarelo mais claro ainda, ex: #FFFFF0 */
}

/* Reset básico para remover margens e paddings padrão do navegador */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box; /* Fundamental para o controle de layout */
}

body {
    font-family: 'Open Sans', sans-serif;
    line-height: 1.6; /* Espaçamento entre linhas para melhor leitura */
    color: var(--text-color);
    background-color: var(--white);
}

/* Container para centralizar o conteúdo e limitar a largura */
.container {
    max-width: 960px; /* Alterado para max-width para ser responsivo */
    margin: 0 auto;   /* Centraliza o container na página */
    padding: 0 20px;  /* Padding lateral para não grudar nas bordas em telas menores */
}


/* Wrapper que agrupa o ícone e o texto do logo */
.logo-wrapper {
    display: flex;           /* Alinha o ícone e o texto na mesma linha */
    align-items: center;     /* Centraliza-os verticalmente um em relação ao outro */
    gap: 8px;                /* Controla o ESPAÇO entre o ícone e o texto. Ajuste este valor! */
}

/* Estilização específica do ÍCONE (emoji) */
.logo-icon {
    font-size: 2em;          /* Tamanho do emoji */
    color: var(--primary-color); /* Cor do emoji (amarelo) */
    line-height: 1;          /* Ajuda a centralizar verticalmente */
}

/* Estilização específica do TEXTO do logo */
.logo-text {
    font-family: 'Open Sans', sans-serif; /* Use 'Open Sans' ou 'Montserrat' para os títulos, como sugerido antes */
    font-size: 1.3em;        /* Tamanho do texto */
    color: var(--primary-color); /* Cor do texto (amarelo) */
    margin: 0;               /* Remove margem padrão do h1 */
}

/* Header - Cabeçalho do site */
header {
    background-color: #242474;
    color: var(--white);
    padding: 10px 0;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra sutil */
}

header .container {
    display: flex; /* Usa Flexbox para alinhar logo e navegação na mesma linha */
    justify-content: space-between; /* Espaço entre o logo e a navegação */
    align-items: center; /* Alinha verticalmente no centro */
}

/* Navegação */
header nav ul {
    list-style: none; /* Remove os marcadores de lista */
    display: flex; /* Alinha os itens da navegação na mesma linha */
}

header nav ul li {
    margin-left: 25px; /* Espaçamento entre os itens da navegação */
    font-size: 15px;

}

header nav ul li a {
    color: var(--white);
    text-decoration: none; /* Remove o sublinhado dos links */
    font-weight: bold;
    transition: color 0.3s ease; /* Transição suave na cor ao passar o mouse */
}

header nav ul li a:hover {
    color: var(--primary-color); /* Altera a cor do link ao passar o mouse */
}


.hero-hashtag {
    font-family: 'Open Sans', sans-serif;
    font-size: 1.3em; /* Tamanho bom para destaque, não tão pequeno */
    font-weight: bold; /* Negrito forte para chamar atenção */
    color: var(--secondary-blue); /* Use o AZUL VIBRANTE para a hashtag */
    margin-bottom: 30px; /* Espaçamento maior para separá-la da descrição */
    margin-top: -10px; /* Puxa um pouco para perto do título, sem grudar */
    letter-spacing: 0.5px; /* Adiciona um pouco de espaço entre as letras */
}

/* Hero Section - Seção principal de destaque */
.hero {
    background: linear-gradient(0deg, rgb(0 0 0 / 65%), rgb(4 1 1 / 35%)), url(https://blog.unoeste.br/wp-content/uploads/2025/09/setembro-amarelo.jpg) center / cover no-repeat, linear-gradient(46deg, #e9d18b, #f7f3e7);
    color: var(--dark-violet); /* Cor do texto para contraste com o amarelo */
    text-align: center;
    padding: 100px 0;
}

.hero h2 {
    font-family: 'Montserrat', sans-serif;
    font-size: 3em;
    margin-bottom: 20px;
    color: var(--white);
}

.hero p {
    font-size: 1.2em;
    margin-bottom: 30px;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    color: var(--white);
}

.btn-cta {
    display: inline-block;
    background-color: var(--hero-light-yellow); /* Fundo com o amarelo claro da seção Hero */
    color: var(--secondary-blue); /* Texto em azul vibrante */
    padding: 15px 30px;
    text-decoration: none;
    border: 2px solid var(--secondary-blue); /* Borda sutil no azul */
    border-radius: 8px; /* Cantos mais arredondados para suavidade */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 0.3s ease; /* Transição para todas as propriedades */
    box-shadow: 0 2px 5px rgba(0,0,0,0.1); /* Sombra suave para dar profundidade */
}



.btn-cta:hover {
    background-color: var(--primary-color); /* Inverte as cores no hover */
    color: var(--primary-yellow); /* Texto amarelo no hover */
    transform: translateY(-2px); /* Efeito sutil de levantar */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Sombra um pouco mais forte no hover */
}


/* Seções de Conteúdo Geral */
.info-section, .call-to-action, .resources-section {
    padding: 80px 0;
    text-align: center;
}

.info-section h3, .call-to-action h3, .resources-section h3 {
    font-family: 'Montserrat', sans-serif;
    font-size: 2.2em;
    color: var(--dark-violet);
    margin-bottom: 40px;
}

.info-section p {
    max-width: 800px;
    margin: 0 auto 20px auto;
    font-size: 1em;
    color: var(--secondary-color);
}

.light-bg {
    background-color: var(--light-bg);
}

/* Seção "Onde Buscar Ajuda?" (Cards) */
.cards-ajuda {
    display: flex; /* Usa Flexbox para os cards */
    justify-content: center; /* Centraliza os cards */
    gap: 30px; /* Espaçamento entre os cards */
    margin-top: 40px;
}

.card {
    background-color: var(--white);
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    padding: 30px;
    width: 300px; /* Largura fixa para cada card */
    text-align: center;
    transition: transform 0.3s ease;
}

.card:hover {
    transform: translateY(-5px); /* Efeito sutil de levantar ao passar o mouse */
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
    display: block; /* Cada botão ocupa uma linha */
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
    background-color: #e6c200;
}

/* Seção "Como Posso Ajudar?" (Grid) */
.grid-ajuda {
    display: grid; /* Usa Grid para os itens de ajuda */
    grid-template-columns: repeat(4, 1fr); /* 4 colunas de tamanho igual */
    gap: 30px; /* Espaçamento entre os itens do grid */
    margin-top: 40px;
}

.item-ajuda {
    background-color: var(--white);
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    padding: 25px;
    text-align: center;
}

.item-ajuda h4 {
    font-family: 'Montserrat', sans-serif;
    color: var(--dark-violet);
    margin-bottom: 10px;
    font-size: 1.2em;
}

.item-ajuda p {
    font-size: 0.9em;
    color: var(--text-color);
}

/* Seção Recursos */
.resources-section ul {
    list-style: none; /* Remove marcadores de lista */
    padding: 0;
    margin-top: 30px;
    max-width: 600px; /* Limita a largura da lista */
    margin-left: auto;
    margin-right: auto;
}

.resources-section ul li {
    margin-bottom: 15px;
}

.resources-section ul li a {
    color: var(--dark-blue);
    text-decoration: none;
    font-size: 1.1em;
    font-weight: 600;
    transition: color 0.3s ease;
}

.resources-section ul li a:hover {
    color: var(--primary-color);
}

/* Estilo da Seção Sobre com Imagem */
.sobre-content {
    display: flex;
    align-items: center; /* Alinha verticalmente */
    gap: 40px; /* Espaço entre texto e imagem */
    text-align: left; /* Alinha o texto à esquerda */
    margin-top: 40px;
}

.sobre-texto, .sobre-imagem {
    flex: 1; /* Faz com que ambos ocupem 50% do espaço */
}

.sobre-imagem img {
    width: 100%;
    border-radius: 8px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
}

/* Estilo do Vídeo Responsivo */
.resources-section h4 {
    font-size: 1.5em;
    color: var(--dark-violet);
    margin-top: 40px;
}

.resources-section p {
    max-width: 600px;
    margin: 10px auto 30px auto;
}

.video-container {
    position: relative;
    padding-bottom: 56.25%; /* Proporção 16:9 (9 / 16 * 100) */
    height: 0;
    overflow: hidden;
    max-width: 100%;
    background: #000;
    margin: 0 auto;
    border-radius: 8px;
}

.video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}


form .btn-form { 
    display: inline-block;
    background-color: var(--primary-color); /* Fundo com o amarelo claro da seção Hero */
    color: var(--dark-violet);
    padding: 15px 30px;
    text-decoration: none;
    border: 2px solid var(--secondary-blue); /* Borda sutil no azul */
    border-radius: 8px; /* Cantos mais arredondados para suavidade */
    font-weight: bold;
    font-size: 1.1em;
    transition: all 
}

form .btn-form:hover {
    background-color: var(--dark-violet); /* Inverte as cores no hover */
    color: var(--white); /* Texto amarelo no hover */
    transform: translateY(-2px); /* Efeito sutil de levantar */
    box-shadow: 0 4px 8px rgba(0,0,0,0.15); /* Sombra um pouco mais forte no hover */
}

/* Estilo do Formulário de contato */
.form-contato {
    max-width: 600px;
    margin: 40px auto 0 auto;
    text-align: left;
}

.form-group {
    margin-bottom: 20px;
}

.form-group label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: var(--secondary-color);
}

.form-group input,
.form-group textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-family: 'Open Sans', sans-serif;
    font-size: 1em;
}

.form-group input:focus,
.form-group textarea:focus {
    outline: none;
    border-color: var(--primary-color);
    box-shadow: 0 0 5px rgba(247, 201, 72, 0.5);
}

/* Footer - Rodapé do site */
footer {
    background-color: var(--secondary-color);
    color: var(--white);
    padding: 30px 0;
    text-align: center;
    font-size: 0.9em;
}

footer .container {
    display: flex; /* Usa Flexbox para alinhar conteúdo do footer */
    flex-direction: column; /* Coloca os itens um abaixo do outro */
    align-items: center; /* Centraliza horizontalmente */
    gap: 15px; /* Espaçamento entre os itens */
}

.social-media a {
    color: var(--white);
    text-decoration: none;
    margin: 0 10px;
    transition: color 0.3s ease;
}

.social-media a:hover {
    color: var(--primary-color);
}


@media (max-width: 992px) {

    .container {
        width: 100%; /* Permite que o container ocupe a largura total */
        padding: 0 15px; /* Reduz padding lateral para telas menores */
    }

    /* Header: Alinha a navegação verticalmente se não couber */
    header .container {
        flex-direction: column;
        gap: 15px;
    }
    header nav ul {
        justify-content: center; /* Centraliza itens do menu */
        flex-wrap: wrap; /* Permite quebrar linha se o menu for muito grande */
        gap: 15px; /* Espaçamento entre itens */
    }
    header nav ul li {
        margin-left: 0; /* Remove margem lateral quebrava o layout */
    }

    /* Hero Section: Ajustes de fonte */
    .hero h2 {
        font-size: 2.5em;
    }
    .hero p {
        font-size: 1.1em;
    }

    /* Seção "Sobre": Empilha texto e imagem */
    .sobre-content {
        flex-direction: column; /* Empilha texto e imagem verticalmente */
        gap: 30px;
        text-align: center; /* Centraliza o texto */
    }
    .sobre-texto, .sobre-imagem {
        flex: none; /* Remove a flexibilidade de 50% */
        width: 100%; /* Ocupa a largura total */
    }
    .sobre-imagem img {
        height: auto; /* Garante que a imagem mantenha sua proporção */
    }

    /* Cards de Ajuda: 2 colunas */
    .cards-ajuda {
        flex-wrap: wrap; /* Permite que os cards quebrem para a próxima linha */
        justify-content: center; /* Centraliza os cards */
        gap: 20px; /* Reduz o espaçamento */
    }
    .card {
        width: calc(50% - 10px); /* 2 colunas, subtraindo metade do gap */
        max-width: 300px; /* Mantém um max-width para não esticar demais */
    }

    /* Grid de Ajuda: 2 colunas */
    .grid-ajuda {
        grid-template-columns: repeat(2, 1fr); /* 2 colunas */
        gap: 20px;
    }
    .item-ajuda {
        padding: 20px;
    }

    /* Títulos de Seção */
    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 2em;
    }

    /* Formulário */
    .form-contato {
        padding: 15px;
    }

}

@media (max-width: 768px) {
    /* 1. Ajustes do Header (Logo e Ícone) */
    .logo-text {
        font-size: 1.2em; /* Reduz o tamanho da fonte do texto do logo */
    }
    .logo-icon {
        font-size: 1.8em; /* Reduz o tamanho da fonte do ícone do logo */
    }

    header nav ul {
        flex-direction: column; /* Altera a navegação para uma lista empilhada verticalmente */
        align-items: center; /* Centraliza os itens do menu horizontalmente */
        gap: 10px; /* Reduz o espaçamento entre os itens do menu */
        margin-top: 10px; /* Adiciona um pequeno espaçamento no topo do menu */
    }

    /* 2. Ajustes da Seção Hero */
    .hero {
        padding: 80px 0; /* Reduz o padding vertical da seção hero */
    }
    .hero h2 {
        font-size: 2em; /* Reduz ainda mais o tamanho da fonte do título principal */
        margin-bottom: 15px; /* Reduz o espaçamento abaixo do título */
    }
    .hero-hashtag {
        font-size: 1.1em; /* Ajusta o tamanho da fonte da hashtag */
        margin-bottom: 20px; /* Ajusta o espaçamento abaixo da hashtag */
    }
    .hero p {
        font-size: 1em; /* Reduz o tamanho da fonte do parágrafo */
        margin-bottom: 25px; /* Ajusta o espaçamento abaixo do parágrafo */
    }
    .btn-cta {
        padding: 12px 25px; /* Reduz o padding do botão de CTA */
        font-size: 1em; /* Reduz o tamanho da fonte do botão */
    }

    /* 3. Ajustes de Seções de Conteúdo Geral */
    .info-section, .call-to-action, .resources-section {
        padding: 60px 0; /* Reduz o padding vertical das seções de conteúdo */
    }

    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 1.8em; /* Reduz ainda mais o tamanho da fonte dos títulos das seções */
        margin-bottom: 30px; /* Reduz o espaçamento abaixo dos títulos */
    }

    /* 4. Ajustes da Seção "Cards de Ajuda" */
    .cards-ajuda {
        /* Se você não tem o menu hambúrguer, esta seção aqui pode ter `grid-template-columns: 1fr;`
           para os cards ficarem em coluna. Se tiver o hambúrguer, este bloco será diferente. */
        grid-template-columns: 1fr; /* Altera para apenas 1 coluna, cada card ocupará a largura total */
    }
    .card {
        width: 100%; /* Faz com que cada card ocupe a largura total disponível */
        max-width: none; /* Remove qualquer limitação de largura máxima, permitindo que o card se estique */
    }

    /* 5. Ajustes da Seção "Grid de Ajuda" */
    .grid-ajuda {
        grid-template-columns: 1fr; /* Altera para apenas 1 coluna, cada item ocupará a largura total */
    }
    .item-ajuda {
        padding: 15px; /* Reduz o padding interno dos itens do grid */
    }

    /* 6. Ajustes do Formulário de Contato */
    .form-contato {
        margin-top: 20px; /* Reduz o espaçamento superior do formulário */
        padding: 10px; /* Reduz o padding interno do formulário */
    }

    /* 7. Ajustes do Footer (Rodapé) */
    footer p, .social-media a {
        font-size: 0.85em; /* Reduz o tamanho da fonte do texto do rodapé e links de mídia social */
    }
}

@media (max-width: 480px) {
    /* 1. Ajustes da Seção Hero */
    .hero h2 {
        font-size: 1.8em; /* Reduz o tamanho da fonte do título principal para telas muito pequenas */
    }
    .hero-hashtag {
        font-size: 1em; /* Ajusta o tamanho da fonte da hashtag */
    }
    .hero p {
        font-size: 0.9em; /* Reduz o tamanho da fonte do parágrafo */
    }
    .btn-cta {
        padding: 10px 20px; /* Reduz o padding do botão de CTA */
        font-size: 0.95em; /* Reduz o tamanho da fonte do botão */
    }

    /* 2. Ajustes de Títulos Gerais de Seções */
    .info-section h3, .call-to-action h3, .resources-section h3 {
        font-size: 1.6em; /* Reduz ainda mais o tamanho da fonte dos títulos das seções */
    }

    /* 3. Ajustes de Textos em Geral */
    .info-section p, .card p, .item-ajuda p, .resources-section ul li a, .form-group label {
        font-size: 0.9em; /* Reduz o tamanho da fonte de vários parágrafos e labels para otimizar o espaço */
    }
}

```

Lembre-se de testar e conferir no navegador o resultado, selecionando diferentes telas na área de ferramenta do desenvolvedor.  Não lembra como faz? Verifique as orientações do início do tutorial (Clique aqui). 



## Observação: Responsividade do Menu

Nosso site está responsivo e funcionando bem. Porém, faltou um detalhe muito importante. O menu em dispositivos menores não está tão legal. O ideal é que ele fique agregado em um ícone e ao clicar ele seja aberto. Vamos aprender a fazer isso nas próximas aulas melhorando o CSS e aplicando Javascript para fazer essa interatividade. 



## Passo 3: Publicação da primeira versão para feedback

Com as principais seções do site já adaptadas para diferentes telas, é hora de disponibilizar nossa primeira versão online. O cliente já está ciente de que o menu será finalizado em breve e deseja acompanhar o progresso e fornecer um feedback inicial.

Vamos fazer o deploy (publicar) o site na internet e compartilhar o link. Isso permitirá que o cliente explore o design responsivo, navegue pelo conteúdo e sugira quaisquer melhorias, validando a direção do nosso trabalho.


### Etapa 1: Crie uma conta no Netlify

O Netlify é uma plataforma excelente e gratuita para publicar sites estáticos de forma muito fácil.

- Acesse: https://www.netlify.com/

- Preencha com seus dados para criar sua conta. Você pode usar seu e-mail ou conectar com sua conta do GitHub/GitLab/Bitbucket para um processo ainda mais rápido.


**Explicação: O que são sites estáticos?** 
Imagine um livro ou um documento em PDF. Quando você abre, o conteúdo que você vê é exatamente o mesmo toda vez que alguém o abre, e para todos que o leem, a não ser que o livro seja reescrito e uma nova versão seja impressa.

Um site estático funciona de forma muito parecida. Ele é uma coleção de arquivos prontos (principalmente HTML, CSS e JavaScript, além de imagens) que são entregues ao navegador do usuário exatamente como foram salvos no servidor.


### Etapa 2: Prepare a pasta do seu projeto

Antes de publicarmos, é fundamental garantir que a pasta do seu projeto esteja organizada e contenha apenas os arquivos necessários para o site.

Estrutura Essencial: Confirme que sua pasta principal do projeto contém:

- O arquivo principal: `index.html`

- A pasta `css` (com seu arquivo de estilo, como `style.css`)

- A pasta `images` (com todas as imagens usadas no site)


**Exemplo de como fiz no meu computador**: 
- Nome da pasta do projeto: `setembro-amarelo-site`
- Conteúdo da pasta: 
<img width="892" height="204" alt="Captura de Tela 2025-10-13 às 01 41 44" src="https://github.com/user-attachments/assets/14cbe24e-0440-4bec-9eed-6df52cd1e5f4" />

**Mantenha Limpo:** É muito importante que não haja nenhum outro arquivo ou pasta que não faça parte diretamente do site. Evite incluir rascunhos, arquivos temporários, downloads ou qualquer coisa que não seja exibida no seu navegador. O que você enviar para o servidor deve ser apenas o que compõe o seu site.

Esta organização garante que o processo de publicação seja suave, que seu site carregue de forma mais eficiente e, crucialmente, contribui para a segurança. Ao enviar apenas os arquivos essenciais, você reduz a chance de expor acidentalmente informações sensíveis ou de criar "portas" desnecessárias que poderiam ser exploradas. É uma boa prática de segurança para qualquer projeto web.


### Etapa 3: Deploy - Colocando o site no servidor


Agora que sua conta no Netlify está criada e a pasta do seu projeto está organizada, é hora de colocar seu site no ar! É surpreendentemente fácil.

Após fazer login na Netlify você estará nessa página que fica na aba "projetos" ou "projects. 1) Clique na área de deploy manual para selecionar a pasta do seu computador onde está o seu projeto e 2) fazer o deploy: 

<img width="1920" height="1080" alt="1" src="https://github.com/user-attachments/assets/a3f8c62d-b9ba-46d7-aa1d-f9d25c5cec29" />

<img width="1920" height="1080" alt="2" src="https://github.com/user-attachments/assets/739baf09-bc21-4a40-a65e-f5a16d2227c5" />

Em seguida, confira a quantidade de arquivos da mensagem. 

*Tenha atenção a quantidade de arquivos que aparece na mensagem. Se você tiver mais que 5 arquivos sendo enviados você pode estar com a pasta com arquivos desnecessários ou ter selecionado a pasta de projeto errada. Afinal, temos 1 arquivo html, 1 arquivo css e 2 fotos.*

Se tudo estiver ok, confirme clicando em fazer upload. 

<img width="1920" height="1080" alt="3" src="https://github.com/user-attachments/assets/47ae6933-1334-4176-ada8-0f5176d25bbb" />

Assim que o processo terminar, o Netlify irá gerar um link público (com um nome aleatório, como happy-panda-12345.netlify.app). O endereço do seu site sempre termina com .netlify.app.

<img width="1920" height="1080" alt="4" src="https://github.com/user-attachments/assets/62422a8f-d638-4c61-9341-c31bc8c90eb3" />


#### Envio para o cliente: 

1. Testes manuais:
   
- Clique no link/endereço do seu site para abrir no navegador.

- Navegue por todas as seções, clique nos links e verifique as imagens.

- Redimensione a janela do navegador para diferentes tamanhos (como se fosse um celular ou tablet) e confira se a responsividade está funcionando perfeitamente como planejamos.

- Certifique-se de que não há nenhum erro de digitação ou problema visual.

2. Envie o Link para o Cliente:
- Somente após você ter certeza de que está tudo em ordem, copie este link e envie-o para seu cliente. Envie o link pelo Teams na área de entrega dessa atividade. 


### Parabéns!

O primeiro deploy a gente nunca esquece! Você não só publicou seu site, mas também desenvolveu o hábito importante de testar seu trabalho online.
