# Tutorial: Construindo a seção "como ajudar" com CSS Grid


Nesta etapa, vamos criar a seção que apresenta dicas de como ajudar. Ao final deste tutorial, teremos construido mais uma seção do [site setembro amarelo](https://inspiradanacomputacao.com/setembro-amarelo/): 

Para organizar os quatro itens de forma alinhada e responsiva, vamos aprender a usar uma das ferramentas mais poderosas do CSS moderno: o Grid Layout.

**Nosso objetivo:** Construir uma seção com um layout em grade de quatro colunas.

**Conceitos que vamos aprender:** A estrutura HTML para itens em grade e, principalmente, como usar as propriedades do CSS Grid (`display: grid`, `grid-template-columns`) para criar layouts complexos de forma simples.

**Dica:** Lembre de conferir no navegador cada ajuste que você for fazendo. E ao final das etapas confira se está como no site de exemplo: [https://inspiradanacomputacao.com/setembro-amarelo/](https://inspiradanacomputacao.com/setembro-amarelo/)


**Onde adicionar o novo código?** Como sempre, a localização é fundamental. A nova seção `como-ajudar` deve ser adicionada depois da seção ajuda, mas ainda dentro da tag `<main>`. Ou seja, após `</section>` da sessão ajuda e antes de fechar `</main>`.

## A Estrutura HTML

Uma nova sessão para representar a área como ajudar: 

```html

    <!-- ...Acima vem os códigos HTML que fizemos nas outras etapas ... -->
    </section> <!-- Fechamento da seção ajuda -->
    
    <section id="como-ajudar" class="info-section">
        <div class="container">
            <h3>Como posso ajudar?</h3>
        </div>
    </section>


</main> <!-- Fechamento da tag main -->

</body>
</html>
```

Com a seção no lugar certo, vamos construir sua estrutura interna.

### Passo 1: O agrupador da grade (`.grid-ajuda`)

Assim como fizemos com Flexbox, precisamos de uma `div` "pai" para agrupar todos os nossos itens. Esta `div` será o nosso container Grid.
Dentro da `<div class="container">` da nova seção, logo após o `<h3>`, adicione o agrupador:

``` html
<div class="grid-ajuda">
    
</div>
```

O HTML da seção ficará assim: 


``` html
<section id="como-ajudar" class="info-section">
    <div class="container">
        <h3>Como posso ajudar?</h3>
        <div class="grid-ajuda">

        </div>
    </div>
</section>
```

### Passo 2: Construindo os itens da grade (`.item-ajuda`)

Agora, vamos criar os quatro itens que ficarão dentro da nossa grade. A estrutura deles é simples: um título e um parágrafo.

Exemplo do primeiro item: 

```html
<div class="item-ajuda">
    <h4>Ouça sem julgar</h4>
    <p>Ofereça um ouvido atento e sem preconceitos. Mostre que você se importa.</p>
</div>
```

Dentro da div `class="grid-ajuda"`, adicione os quatro itens:

```html
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
```

Após seguir os passos acima, o HTML completo da sessão ajuda ficará assim: 


```html
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
```

## Estilizando com CSS Grid

Agora, vamos ao arquivo `style.css` para aprender a usar o Grid Layout e criar nosso layout de quatro colunas.

### Passo 1: Criando o Layout em Grade (`.grid-ajuda`)

Este é o passo principal, onde a mágica do Grid acontece. Vamos aplicar as propriedades ao nosso container `.grid-ajuda`. Adicione o seguinte código ao seu `style.css`:

```css
.grid-ajuda {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
    margin-top: 40px;
}
```

**Explicação:**
- `display: grid;`: Assim como `display: flex`, este comando "ativa" as superpotências de layout. Ele informa ao container `.grid-ajuda` que seus filhos diretos (`.item-ajuda`) agora são itens de uma grade.
  
- `grid-template-columns: repeat(4, 1fr);`: Esta é a propriedade mais importante porque define como serão as colunas da nossa grade.
    - `repeat(4, 1fr)`: É um atalho que diz: "Quero que você repita a seguinte regra 4 vezes".
  
    - `1fr`: A unidade `fr (fração)` é a grande estrela do Grid. Ela representa uma fração do espaço disponível. Ao usarmos `1fr` quatro vezes, estamos dizendo ao navegador: *"Divida todo o espaço horizontal disponível em 4 colunas de tamanho perfeitamente igual"*.

- `gap: 30px;`: Similar ao Flexbox, esta propriedade cria um espaçamento de 30px entre cada item da grade, tanto nas colunas quanto nas linhas.


## Passo 2: Estilizando o item individual (`.item-ajuda`)

O estilo de cada item da grade é muito parecido com o do `.card` que fizemos na seção anterior. Vamos aplicar um fundo, bordas arredondadas, espaçamento e uma sombra.

Adicione o código abaixo:

```css
.item-ajuda {
    background-color: var(--white);
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.08);
    padding: 25px;
    text-align: center;
}
```

## Passo 3: Estilizando os textos (`.item-ajuda h4` e `.item-ajuda p`)

Para manter a consistência visual do site, vamos estilizar os textos dentro dos itens de forma parecida com os textos dos cards.

Adicione o estilo para o título dos itens da seção ajuda:

```css
.item-ajuda h4 {
    font-family: 'Montserrat', sans-serif;
    color: var(--dark-violet);
    margin-bottom: 10px;
    font-size: 1.2em;
}
```
E para os textos do parágrafo: 

```css
.item-ajuda p {
    font-size: 0.9em;
    color: var(--text-color);
}
```

Ao final você terá esse CSS para área "Como ajudar":

```css
.grid-ajuda {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
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
```



## Revisão do CSS:

Ao final da realização de todas as etapas deste tutorial, o código CSS completo do seu site será: 

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

.grid-ajuda {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 30px;
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
```

## Conclusão: 

Excelente! Você acaba de aprender a usar CSS Grid, uma das ferramentas de layout mais importantes e poderosas para um desenvolvedor web.

Enquanto o Flexbox é ideal para alinhar itens em uma única dimensão (uma linha ou uma coluna), o Grid é a ferramenta perfeita para layouts em duas dimensões (linhas e colunas), como a que acabamos de criar.

Atualize o navegador e veja como a página está ainda mais completa! Compare com o site de exemplo: [https://inspiradanacomputacao.com/setembro-amarelo/](https://inspiradanacomputacao.com/setembro-amarelo/)







