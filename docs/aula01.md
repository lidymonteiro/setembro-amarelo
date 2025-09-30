# Tutorial: Construindo o menu de navegação

Neste guia, vamos criar o menu de navegação do site "Setembro Amarelo". Mais do que apenas escrever o código, vamos entender por que uma estrutura bem organizada com HTML e classes no CSS é a melhor forma de trabalhar.


## Deixando o HTML mais "inteligente" 

Vamos começar refatorando o "esqueleto"/estrutura do nosso menu. Usaremos tags e divs de forma estratégica para nos dar total controle no CSS mais tarde.


### Passo 1: A Base com `<header>` e o `.container`

Todo site precisa de um cabeçalho. Mas, para que o conteúdo não fique "esparramado" em telas grandes, nós o colocamos dentro de uma "caixa" centralizada.

1. No seu arquivo `index.html`, dentro de `<body>`, adicione a tag `<header>`.

2. Dentro dela da tag `<header>`, crie uma `<div class="container">`.


```html
<header>
    <div class="container">

    </div>
</header>
````


#### Explicação: 
- `<header>`: Informa ao navegador que este é o bloco do cabeçalho.

- `<div class="container">`: Esta é a nossa "caixa de conteúdo". No CSS, vamos definir que ela tenha uma largura máxima (ex: `960px`) e fique sempre no centro da tela. Usaremos essa mesma classe `.container` em outras seções para manter todo o site perfeitamente alinhado.



### Passo 2: Agrupando o Logo com um "Wrapper"

Nosso logo tem duas partes: um ícone (🎗️) e o texto. Para que eles andem sempre juntos como um bloco só, vamos "embrulhá-los" (agrupar) em uma `div`. Para isso criaremos `<div class="logo-wrapper">`. 

1. Dentro da `<div class="container">`, adicione o código abaixo:

```html
<div class="logo-wrapper">
    <span class="logo-icon" aria-hidden="true">🎗️</span>
    <h1 class="logo-text">Setembro Amarelo</h1>
</div>
````

#### Explicação: 

- `<div class="logo-wrapper">`: Funciona como um "agrupador". Agora, podemos mover e alinhar o logo inteiro apenas manipulando essa `<div class="logo-wrapper">`. Fica muito mais fácil posicionar o logo à esquerda e o menu à direita.

- Classes `.logo-icon` e `.logo-text`: Damos "nomes" específicos para o ícone e para o texto para que, no CSS, possamos estilizar exatamente eles, sem afetar outros `<span>` ou `<h1>` que possam existir na página.



### Código parcial:

Após realizar o **passo 1 e 2**, relacionado ao cabeçalho (`<header>`) deve estar assim: 

```html
<header>
    <div class="container">
        <div class="logo-wrapper">  
            <span class="logo-icon" aria-hidden="true">🎗️</span>
            <h1 class="logo-text">Setembro Amarelo</h1>
        </div>
    </div>
</header>
```



### Passo 3: Criando a lista de navegação

Por fim, vamos adicionar os links do menu. A forma semanticamente correta de fazer isso é com uma lista dentro de uma tag `<nav>`.

Ainda dentro da `<div class="container">`, logo após a div do `logo-wrapper`, adicione a navegação:

```html
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
```


### Revisão do HTML: 

Ao final dos **passos 1, 2 e 3**, a estrutura completa do seu `<header>` deve ser esta:


```html
<header>
    <div class="container">
        <div class="logo-wrapper">  
            <span class="logo-icon" aria-hidden="true">🎗️</span>
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
````

E seu código HTML completo: Revisado até o `<header>`

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Setembro Amarelo - Abrace a Vida</title>
</head>
<body>

    <!--- Inicio do HEADER que revisamos --->
    <header>
        <div class="container">
            <div class="logo-wrapper">  
                <span class="logo-icon" aria-hidden="true">🎗️</span>
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
    <!--- FIM do HEADER que revisamos --->

    <!-- .... Os códigos das outras áreas continuam abaixo ... -->

</body>
</html>
```

Agora temos o HTML do `<header>` (cabeçalho) pronto para estilização. Ao final teremos esse resultado: 



## Estilizando o menu com CSS

Agora que nosso esqueleto/estrutura HTML está montado, vamos começar a parte mais divertida: dar cor, forma e vida à nossa página com o CSS. Com o HTML bem organizado, você verá como a estilização se torna muito mais fácil e lógica.


### Preparação: Conectando os Arquivos
Antes de escrever qualquer estilo, precisamos garantir que nosso arquivo `s`tyle.css exista e que o `index.html` saiba onde encontrá-lo.

#### 1. Crie o arquivo e a pasta:
Como uma boa prática de organização, vamos manter nossos estilos em um arquivo separado.
- Dentro da pasta principal do seu projeto, crie uma nova pasta chamada `css`.

- Dentro desta pasta `css`, crie um novo arquivo chamado `style.css`

#### 2. Conecte o CSS ao HTML:
Para que o `index.html` possa usar os estilos do `style.css`, você precisa "avisar" a ele onde o arquivo está. Fazemos isso com uma única linha de código na seção `<head>` do seu HTML.

Abra o arquivo `index.html` e, dentro da tag `<head>`, adicione a seguinte linha:

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Setembro Amarelo - Abrace a Vida</title>
    <link rel="stylesheet" href="css/style.css">
</head>
```


#### Explicação: 

-`<link>`: É a tag usada para conectar recursos externos.

- `rel="stylesheet"`: rel significa "relação". Estamos dizendo ao HTML que a relação deste arquivo com a página é de uma folha de estilos (stylesheet).

- `href="css/style.css"`: href é o caminho para o arquivo. Estamos dizendo: "O arquivo que você precisa carregar está na pasta `css` e se chama `style.css"`.


#### Revisão do Código HTML

Seu código index.html após a inclusão: 

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="css/style.css">
    <title>Setembro Amarelo - Abrace a Vida</title>
</head>
<body>

    <header>
        <div class="container">
            <div class="logo-wrapper">  
                <span class="logo-icon" aria-hidden="true">🎗️</span>
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

    <!-- .... Os códigos das outras áreas continuam abaixo ... -->

</body>
</html>
```

Pronto! Seus arquivos agora estão conectados. Tudo que escrevermos em `style.css` será aplicado ao `index.html`. Vamos começar!


### Passo 0: A Base do nosso CSS (fontes, cores e padrões)

Antes de estilizar partes específicas como o cabeçalho, um pessoa desenvolvedora de software prepara o "terreno". Vamos configurar fontes, cores e regras globais que serão usadas em todo o site. Isso garante consistência e facilita a manutenção.


Adicione os seguintes códigos ao arquivo `style.css`: 

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


/* Container para centralizar o conteúdo. 
   Será aplucado a qualquer elemento que tenha a class="container" no HTML
*/
.container { 
    width: 960px;                         /* Define uma largura máxima fixa para a área de conteúdo. */
    margin: 0 auto;                       /* Centraliza o container na página (0 de margem em cima/baixo, 'auto' nas laterais). */
    padding: 0 20px;                      /* Adiciona um espaçamento interno de 20px nas laterais, para o conteúdo não colar nas bordas. */
}

```

Teste você mesmo: Salve o arquivo `style.css` e atualize a página no navegador. Você notará que a fonte do texto já mudou e os espaçamentos estão diferentes, mesmo antes de adicionarmos o estilo do header. Isso mostra que nossa base já está funcionando!


Com nossa base pronta, agora podemos começar a estilizar as partes específicas do nosso site de forma consistente.


### Passo 1: Estilizando a barra do cabeçalho (`header`)

Agora, no seu arquivo `style.css`, logo abaixo do código base que acabamos de adicionar, vamos começar a estilizar o header.



```css
header {
    background-color: #242474;
    padding: 10px 0;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
```



### Passo 2: Alinhando os blocos (logo e menu)

Aqui a mágica acontece! Vamos dizer ao `.container` para alinhar seus filhos `(.logo-wrapper` e `<nav>`) um de cada lado.

```css
header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
```

#### Explicação: 

- `display: flex`: Ativa o layout flexível.

- `justify-content: space-between`: Coloca o máximo de espaço possível entre o primeiro item (logo) e o último (menu).

- `align-items: center`: Alinha os dois verticalmente no centro da barra.


### Parte 3: Estilizando as partes do logo

Agora usamos as classes que criamos para estilizar o logo. Primeiro, alinhamos o ícone e o texto dentro do `.logo-wrapper`.


```css
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
```


### Parte 4:  Transformando a lista em menu horizontal

Por padrão, uma lista `<ul>` tem bolinhas e fica na vertical. Vamos mudar isso.

```css
header nav ul {
    list-style: none; /* Remove as bolinhas */
    display: flex;    /* Coloca os itens um ao lado do outro no menu */
}

header nav ul li {
    margin-left: 25px; /* Cria um respiro entre cada item do menu */
}
```

### Parte 5: O toque final nos links


Por fim, vamos estilizar os links e adicionar um efeito visual para quando o mouse passar por cima (`:hover`).

```css
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
```

### Revisão do CSS: 

Ao final das etapas, o código completo do CSS ficará assim: 


```css

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

```


Carregue a página para ver o resultado. Seu menu estará como o da página: https://inspiradanacomputacao.com/setembro-amarelo/


## Conclusão

Parabéns! Você não apenas construiu um menu, mas aprendeu a usar uma estrutura HTML que facilita a estilização e a manutenção. Entender o papel dos `containers`, `div` e `classes` é o que diferencia um código amador de um código profissional.








