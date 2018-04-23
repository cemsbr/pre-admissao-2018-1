# HTML

Tipo: `leitura`

* Formato: `ritmo próprio`
* Duração: `1h`

## Objetivos de Aprendizagem

* Conhecer os elementos HTML mais comuns
* Entenda o conceito de aninhamento em HTML
* Conhecer as diferenças no comportamento em bloco e em linha de elementos HTML

## O que é HTML?

No decorrer da _Introdução à Programação_,_ _você criou seu primeiro site. Você aprendeu a criar um arquivo HTML e vinculá-lo ao seu arquivo JavaScript. Nesta lição, nos aprofundaremos em HTML.

Analisando diretamente a documentação da [Mozilla Developer Network](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/Getting_started) , temos o seguinte:

> HTML \(HyperText Markup Language\) **não** é uma linguagem de programação, é uma _linguagem de marcação_ utilizada para dizer ao seu navegador como estruturar a página web que você visita. A página pode ser tanto complicada como simples quanto o desenvolvedor web desejar que seja.
>
> O HTML consiste em uma série de elementos que você usa para anexar, envolver ou marcar diferentes partes do conteúdo para que apareça ou aja de uma certa maneira. O fechamento das tags pode transformar uma parte do conteúdo dentro do elemento em um link para direcionar à uma outra página web, colocar as palavras em itálico, e assim por diante.

## Anatomia de um elemento HTML

Lembre-se de que, com algumas exceções \(por exemplo `<!DOCTYPE html>`\), os elementos html começam com um _marcador de abertura _e terminam com um _marcador de fechamento_. Por exemplo, o elemento `p`começa com um marcador de abertura `<p>`e termina com um marcador de fechamento `</p>`. O texto entre as marcações \(_tags_\) de abertura e fechamento é o _conteúdo_ do elemento.

![R&#xF3;tulo de exemplo](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-tag-sample.png?raw=true)

## Aninhamento HTML

Um elemento pode conter outros elementos ou tags HTML em seu conteúdo. Isso é chamado de _aninhamento_.

Lembre-se da estrutura básica de um documento HTML que estamos usando na maioria dos nossos exercícios e acrescentemos um par de elementos:

```markup
<!DOCTYPE html>
<html>
  <head>
    <title>HTML Aninhado</title>
  </head>
  <body>
    <h1>Laboratoria</h1>
    <p>Código <em>que</em> <strong>transforma</strong></p>
  </body>
</html>
```

Observe como certos elementos "aninham" outros. Ou seja, alguns elementos estão "contidos" em outros. Por exemplo, o elemento `body` tem dois elementos aninhados \(ou filhos\): o título `h1`e o parágrafo `p`. Por sua vez, o parágrafo `p`contém dois elementos adicionais \(outros filhos\): `em`e `strong`.

Podemos visualizar esse conceito de _aninhamento_ html da seguinte maneira:

![Nesting html](http://www.mrinitialman.com/Library/HTML/Pictures/HTML-Markup_Basics/html_nesting.png)

Neste exemplo, vemos elementos que já devem ser familiares para você. Você já conhece o marcador `DOCTYPE`,  os elementos `head`, `body`, `title`, `h1`e `p`\(se você precisa de uma revisão sobre eles, sugerimos que leia novamente a lição sobre [criar seu primeiro site](https://github.com/Laboratoria/curricula-js/blob/master/01-intro/01-introduction/03-your-first-website.md) do curso _Introdução à Programação_\). Os dois elementos adicionais que aninhamos são: o `em`que faz com que seu conteúdo seja exibido como texto em _itálico_ e `strong`que faz com que seu conteúdo seja exibido como texto em **negrito**.

Ao abrir este documento no navegador, veremos o seguinte:

![HTML aninhado](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-nested-html.png?raw=true)

## Elementos em Bloco vs em Linha

Vamos voltar para a leitura HTML da [Mozilla Developer Network](https://developer.mozilla.org/pt-BR/docs/Learn/HTML/Introduction_to_HTML/Getting_started):

> Há duas categorias importantes no HTML, que você precisa conhecer — elementos em bloco e elementos inline.
>
> **Elementos em bloco** formam um bloco visível na página. Eles aparecerão em uma nova linha logo após qualquer elemento que venha antes dele, e qualquer conteúdo depois de um elemento em bloco também aparecerá em uma nova linha. Elementos em bloco geralmente são elementos estruturais na página que representam, por exemplo: parágrafos, listas, menus de navegação, rodapés etc. Um elemento em bloco não seria aninhado dentro de um elemento inline, mas pode ser aninhado dentro de outro elemento em bloco.
>
> **Elementos inline \(na linha\)** são aqueles que estão contidos dentro de elementos em bloco, envolvem apenas pequenas partes do conteúdo do documento e não parágrafos inteiros ou agrupamentos de conteúdo. Um elemento inline não fará com que uma nova linha apareça no documento: os elementos inline geralmente aparecem dentro de um parágrafo de texto, por exemplo: um elemento `<a>`  \(hyperlink\) ou elementos de ênfase como `<em>` ou `<strong>`.

Veja um exemplo:

```markup
<!DOCTYPE html>
<html>
  <head>
    <title>HTML Aninhado</title>
  </head>
  <body>
    <em>Primeiro</em><strong>segundo</strong><em>terceiro</em>
    <p>quarto</p><p>quinto</p><p>sexto</p>
  </body>
</html>
```

Ao visualizar o documento anterior no navegador, teremos:

![](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-block-inline.png?raw=true)

Tanto `em`quanto `strong`são elementos na linha. Portanto, os primeiros três elementos são colocados na mesma linha, um após o outro, sem espaço entre eles. Por outro lado, `p`é um elemento em nível de bloco, então cada elemento aparece em uma nova linha, com espaço acima e abaixo de cada `p`.

## Comentários em HTML

Assim como podemos comentar nosso código `javascript`para torná-lo mais compreensível, também podemos adicionar comentários ao nosso código HTML. Para definir um comentário em um arquivo HTML, usamos os marcadores `<!--`para abrir o comentário e `-->` para fechá-lo.

```markup
<!-- Isto é um comentário. Não será visto na página, mas sim em meu código. -->
```

## Replicando a página de Grace Hopper da Wikipedia

Agora que você tem uma ideia dos elementos HTML mais comuns, seu comportamento \(_inline_ vc _block_\) e seus principais atributos, Michelle explicará como construir uma réplica da [página da Wikipédia de Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper) :

![Grace Hopper](https://img.youtube.com/vi/9w5ITAr2hlQ/0.jpg)

## Os elementos `div`e`span`

Muitas vezes, ao criar nossa estrutura HTML, torna-se necessário "agrupar" elementos para dividir nossa página em seções ou partes lógicas. Por exemplo, se no _footer_ \(o rodapé da página\) do nosso site queremos mostrar os ícones de nossas redes sociais ao lado de links de contato, é útil agrupar todos os ícones em uma seção e os links em outra seção, e que ambos os grupos estejam contidos no _footer_ .

Para fazer esses agrupamentos, podemos usar os elementos `div`e `span`. Os elementos `div`e `span`são como "contêineres" vazios que preenchemos com outros elementos e conteúdos.

* O elemento `div`define uma divisão ou uma seção em um documento HTML. É usado para agrupar elementos em **bloco**. É frequentemente usado como um contêiner para outros elementos. Um `div`é um bloco, o que significa que há uma quebra de linha antes e depois.
* O elemento `span`é usado como um contêiner para textos. É do tipo **inline**, isto é, aparece nas linhas, como parte de um parágrafo.

Vamos ver um exemplo:

```markup
<!DOCTYPE html>
<html>
  <body>
    <div style="background-color: green; color: white">
      <h2>Cidade do México</h2>
      <p>A Cidade do México, anteriormente conhecida como Distrito Federal,
        é uma das 32 unidades federativas do México, assim como a capital
        dos <span style="color: yellow">Estados Unidos Mexicanos</span>.
      </p>
    </div>
    <div style="background-color: red; color: white">
      <h2>Lima</h2>
      <p>Lima é a capital da <span style="color: yellow">República do
        Perú</span> e da província homônima. Situa-se na costa central do país, 
        às magens do Oceano Pacífico, contendo uma extensa e populosa
        área urbana conhecida como Lima Metropolitana, cercada pelo
        deserto costeiro e extendida sobre os vales dos rios Chillón,
        Rímac e Lurín.
      </p>
    </div>
    <div style="background-color: blue; color: white">
      <h2>Santiago</h2>
      <p>Santiago, chamada também de Santiago do Chile, é a capidal do 
        <span style="color: yellow">Chile</span> e da região Metropolitana
        de Santiago. É o principal núcleo urbano do país e sua área 
        metropolitana também é conhecida pelo nome de Grande Santiago.
      </p>
    </div>
  </body>
</html>
```

Ao visualizar o exemplo anterior no navegador, temos:

![&quot;div&quot; e &quot;span&quot;](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-div-and-span.png?raw=true)

Veja como agrupamos tudo relacionado a um país em um `div`. Isso é útil porque ele cria seções que seguem uma ordem lógica. Mas, mais importante, ter essas seções separadas permite que você forneça estilos diferentes para cada seção: a cor do plano de fundo e a cor da fonte variam para cada país. O mesmo acontece com as palavras que mostramos em amarelo. Graças a `span` nós podemos fazer com que certas partes do texto tenham um estilo diferente. 

