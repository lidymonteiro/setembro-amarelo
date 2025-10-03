## Desafio: Construindo a seção de recursos (id="recursos")

Chegamos à nossa última seção de conteúdo principal! Aqui, vamos adicionar uma lista de links para recursos externos.

Desta vez, o desafio é com vocês! A proposta é que vocês construam toda a seção, do HTML ao CSS, usando tudo o que aprendemos até agora. Este é o momento de conectar os pontos e mostrar o que vocês aprenderam.

Você precisa construir é uma seção simples e limpa com um fundo claro, um título centralizado e uma lista de links de recursos logo abaixo.

Não se preocupem, não vou deixá-los no escuro. Abaixo está um guia com dicas e um passo a passo do que precisa ser feito.

## Dica:

Olhe para o código que você já desenvolveu! Muitas das propriedades e técnicas que você precisa para este desafio já foram usadas nas seções anteriores (nos cards, botões, títulos, etc.). Um bom desenvolvedor(a) não reinventa a roda, ele reutiliza e adapta soluções que já funcionaram.

Este desafio testa sua capacidade de aplicar o que aprendeu de forma independente. Não tenha medo de errar, pesquisar e experimentar. Boa sorte!


## Desafio HTML: Crie a estrutura da seção recursos

Seu primeiro desafio é criar a estrutura HTML completa para esta seção.


### 1. Onde posicionar a nova seção?

- **Dica:** A nova seção recursos deve ser a última "irmã" dentro da "casa" <main>. Use o método "Antes e Depois" que aprendemos para encontraro lugar exato no seu `index.html`. Ou analise o código atual do HTML e verifique que todas as seções que criamos antes estão dentro de `<main>`. Precisamos criar uma nova sessão e colocada antes do fechamento da tag main `<\main>`. 

### 2. Crie a estrutura da seção recursos:

- **Dica:** Comece com a tag `<section>`. Qual id você deve dar a ela para que o menu funcione? Não esqueça de fechar a tag section. Sempre que abrir uma tag, feche imediatamente. 
  
```html
<section id="<ADICIONE O ID CORRETO>"> 

</section>
```

- **Dica:** Pense nas classes que já criamos. Quais delas você poderia reutilizar aqui para já dar à seção um fundo claro e o estilo de espaçamento padrão? (`light-bg` e `info-section` são ótimas candidatas).


```html
<section id="<ADICIONE O ID CORRETO>" class="<ADICIONE CLASSES"> 

</section>
```

### 3. Adicione o conteúdo principal:

- **Dica:** Dentro da seção, não se esqueça do nosso velho amigo `<div class="container">` para manter o alinhamento.

- **Dica:** A seção precisa de um título. Qual tag de título (`h1`, `h2`, `h3`, etc.) faz mais sentido usar aqui, seguindo a hierarquia da página? Analise como foi feito nas outras seções. 


### 4. Construa a lista de links:

- **Dica:** Qual é a forma semanticamente correta de criar uma lista de itens em HTML? Lembre-se do trio de tags `<ul>`, `<li>` e `<a>`.

- **Dica Bônus**: Os links desta seção apontam para sites externos. Qual atributo você deve adicionar na tag `<a>` para que o link abra em uma nova aba do navegador e não feche o seu site? (Se não lembrar, é uma ótima oportunidade para pesquisar!).


## Desafio CSS: Estilize a seção recursos

Com o HTML pronto, sua segunda missão é estilizar a seção no arquivo `style.css`.

### 1. Limpe a aparência da lista (`ul`):

- **Desafio:** Por padrão, a lista `<ul>` vem com bolinhas (marcadores) e um recuo à esquerda. Como você pode remover esses estilos para ter uma lista limpa?

- **Dica**: Explore as propriedades `list-style` (para os marcadores) e `padding` (para o recuo).

### 2. Centralize a lista na página:

- **Desafio:** Nossa lista de links deve ter uma largura máxima (por exemplo, `600px`) e ficar centralizada horizontalmente.

- **Dica:** Lembre-se do truque que usamos para centralizar o `.container`. Envolve aplicar `max-width` e configurar a `margin` para `auto` nas laterais.

### 3. Dê espaço entre os itens da lista (`li`):

- **Desafio:** Os links não devem ficar colados uns nos outros. Crie um espaçamento vertical entre eles.

- **Dica:** A propriedade `margin-bottom` aplicada ao `<li>` é perfeita para isso.


### 4. Estilize os links (`a`):

- **Desafio**: Faça os links terem uma aparência profissional: sem sublinhado, com uma fonte maior e mais forte, e com uma cor que combine com nosso site.

- **Dica:** Você precisará usar `text-decoration`, `font-size`, `font-weight` e, claro, nossas variáveis de cor, como `var(--dark-violet)`.

### 5. Adicione a interatividade (:hover):

- **Desafio:** O link deve mudar de cor quando o mouse passar por cima, de forma suave.

- **Dica:** Use a pseudo-classe `:hover` para definir a nova cor (que tal `var(--primary-color)`?). Não se esqueça da propriedade `transition` na regra principal do link para que a animação seja elegante.

