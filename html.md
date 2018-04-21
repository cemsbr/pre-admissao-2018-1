# HTML

Tipo: `lectura`

* Formato: `self-paced`
* Duração: `1h`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

* Conheça os elementos HTML mais comuns
* Entenda o conceito de aninhamento de HTML
* Conheça as diferenças no comportamento de blocos e online de elementos HTML

### O que é HTML? {#¿qué-es-html}

No decorrer da `Introducción a la Programación`criação do seu primeiro site. Você aprendeu a criar um arquivo HTML e vinculá-lo ao seu arquivo JavaScript. Nesta lição, nos aprofundaremos no HTML.

Analisando diretamente a [documentação](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/iniciar) da [Mozilla Developer Network](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/iniciar) , temos o seguinte:

> HTML \(HyperText Markup Language\) **não** é uma linguagem de programação, é uma linguagem de marcação, usada para dizer ao seu navegador como estruturar as páginas que você visita. Pode ser tão complexo ou tão simples quanto o desenvolvedor da web desejar.
>
> HTML consiste em uma série de elementos, que você pode usar para delimitar, agrupar ou marcar diferentes partes do conteúdo para fazê-las aparecer de uma certa maneira ou agir de uma determinada maneira. Os rótulos que envolvem uma parte do conteúdo podem fazer com que o conteúdo seja vinculado a outra página, colocar uma palavra em itálico e assim por diante.

### Anatomia de um elemento HTML {#anatomía-de-un-elemento-html}

Lembre-se de que, com algumas exceções \(por exemplo `<!DOCTYPE html>`\), os elementos html começam com um `etiqueta de apertura (o inicio)`e terminam com um `etiqueta de cierre (o fin)`. Por exemplo, o elemento `p`começa com o rótulo inicial `<p>`e termina com o rótulo final `</p>`. O texto entre as tags de abertura e fechamento é o _conteúdo_ do elemento.

![R&#xF3;tulo de exemplo](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-tag-sample.png?raw=true)

### Aninhamento de HTML {#anidamiento-html}

Um elemento pode conter outros elementos ou tags HTML em seu conteúdo. Isso é chamado de _aninhamento_ .

Lembre-se da estrutura básica de um documento HTML que estamos usando na maioria dos nossos exercícios e inclua alguns elementos adicionais:

```text
<!DOCTYPE html>
<html>
  <head>
    <title>HTML anidado</title>
  </head>
  <body>
    <h1>Laboratoria</h1>
    <p>Código <em>que</em> <strong>transforma</strong></p>
  </body>
</html>
```

Observe como certos elementos "aninham" outros. Ou seja, alguns elementos estão "contidos" nos outros. Por exemplo, o elemento `body` tem dois elementos aninhados \(ou filhos\) que são o título `h1`e o parágrafo `p`. Por sua vez, o parágrafo `p`contém dois elementos adicionais \(outras crianças\): `em`y `strong`.

Podemos visualizar esse conceito de _aninhamento_ de html da seguinte maneira:

![Nesting html](http://www.mrinitialman.com/Library/HTML/Pictures/HTML-Markup_Basics/html_nesting.png)

Neste exemplo, vemos elementos que já devem ser familiares para você. Você sabe sobre o rótulo `DOCTYPE`, elementos `head`, `body`, `title`, `h1`e `p`\(se você precisa de uma revisão deste, sugerimos que você leia a lição novamente [criar seu primeiro site](https://github.com/Laboratoria/curricula-js/blob/master/01-intro/01-introduction/03-your-first-website.md) , é claro `Introducción a la Programación`\). Alguns elementos adicionais que adicionamos são: o `em`que faz com que seu conteúdo seja exibido como texto em _itálico_ e `strong`que faz com que seu conteúdo seja exibido como texto em _negrito_ .

Ao abrir este documento no navegador, teremos o seguinte:

![HTML aninhado](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-nested-html.png?raw=true)

### Elementos vs. bloco em linha {#elementos-bloque-vs-en-línea}

Vamos voltar para a leitura HTML da [Mozilla Developer Network](https://developer.mozilla.org/es/docs/Learn/HTML/Introduccion_a_HTML/iniciar) . Nos disse:

> Existem duas categorias importantes de elementos em HTML: elementos no nível de bloco e elementos em linha.
>
> **Os elementos no nível do** bloco formam um bloco visível em uma página. Eles aparecerão em uma nova linha de qualquer conteúdo que veio antes e qualquer conteúdo que vier depois também aparecerá em uma nova linha. Elementos de nível de bloco tendem a ser elementos estruturais na página que representam, por exemplo, parágrafos, listas, menus de navegação, rodapés, etc. Um elemento no nível de bloco não seria aninhado em um elemento in-line, mas poderia ser aninhado em outro elemento no nível de bloco.
>
> **Elementos embutidos** são aqueles que estão contidos em elementos de nível de bloco e envolvem apenas pequenas partes do conteúdo do documento, não parágrafos inteiros ou agrupamentos de conteúdo. Um elemento online não fará com que uma nova linha apareça no documento: elas geralmente aparecem em um parágrafo ou texto, por exemplo, elementos de ênfase como `em`ou `strong`.

Vamos ver um exemplo:

```text
<!DOCTYPE html>
<html>
  <head>
    <title>HTML anidado</title>
  </head>
  <body>
    <em>primero</em><strong>segundo</strong><em>tercero</em>
    <p>cuarto</p><p>quinto</p><p>sexto</p>
  </body>
</html>
```

Ao visualizar o documento anterior no navegador, teremos:

![Bloquear vs na fila](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-block-inline.png?raw=true)

Tanto `em`quanto eles `strong`são elementos online. Portanto, os primeiros três elementos são colocados na mesma linha, um após o outro, sem espaço entre eles. Por outro lado, `p`é um elemento no nível do bloco, então cada elemento aparece em uma nova linha, com espaço acima e abaixo de cada um `p`.

### Comentários em HTML {#comentarios-en-html}

Como podemos discutir nosso código `javascript`para torná-lo mais compreensível, também podemos adicionar comentários ao nosso código `html`. Para definir um comentário em um arquivo html, usamos as tags `<!--`para abrir o comentário e `-->`fechá-lo.

```text
<!-- Esto es un comentario. No se verá en la web, pero sí en mi código. -->
```

### Replicando a página do Grace Hopper da wikipedia {#replicando-la-página-de-grace-hopper-de-wikipedia}

Agora que você tem uma ideia dos elementos `html`mais comuns, seu comportamento \(inline vs block\) e seus principais atributos, Michelle explicará como construir uma réplica da [página da Wikipédia de Grace Hopper](https://en.wikipedia.org/wiki/Grace_Hopper) :

![Grace Hopper](https://img.youtube.com/vi/9w5ITAr2hlQ/0.jpg)

### Os elementos `div`e`span` {#los-elementos-div-y-span}

Muitas vezes, ao criar nossa estrutura HTML, torna-se necessário "agrupar" elementos para dividir nossa Web em seções ou partes lógicas. Por exemplo, se no _rodapé_ do nosso site queremos mostrar os ícones de nossas redes sociais ao lado de links de contato, é útil agrupar todos os ícones em uma seção e os links em outra seção, e que ambos os grupos estão contidos no _rodapé_ .

Para fazer esses agrupamentos, podemos usar os elementos `div`y `span`. Os elementos `div`e `span`são como "containers" vazios que preenchemos com outros elementos e conteúdos.

* O elemento `div`define uma divisão ou uma seção em um documento HTML. É usado para agrupar elementos de **bloco** . É frequentemente usado como um contêiner para outros elementos. A `div`é um bloco, o que significa que há uma quebra de linha antes e depois.
* O elemento `span`é usado como um contêiner para textos. É **um** tipo **inline** ; isto é, aparece entre as linhas, como parte de um parágrafo.

Vamos ver um exemplo:

```text
<!DOCTYPE html>
<html>
  <body>
    <div style="background-color: green; color: white">
      <h2>Ciudad de México</h2>
      <p>La Ciudad de México, anteriormente conocida como el Distrito Federal,
        es una de las 32 entidades federativas de México, así como la capital
        de los <span style ="color: yellow">Estados Unidos Mexicanos</span>.
      </p>
    </div>
    <div style="background-color: red; color: white">
      <h2>Lima</h2>
      <p>Lima es la capital de la <span style ="color: yellow">República del
        Perú</span> y de la provincia homónima. Se sitúa en la costa central
        del país, a orillas del océano Pacífico, conformando una extensa y
        populosa área urbana conocida como Lima Metropolitana, flanqueada por
        el desierto costero y extendida sobre los valles de los ríos Chillón,
        Rímac y Lurín.
      </p>
    </div>
    <div style="background-color: blue; color: white">
      <h2>Santiago</h2>
      <p>Santiago, llamada también Santiago de Chile, es la capital de
        <span style ="color: yellow">Chile</span> y de la región Metropolitana
        de Santiago. Es el principal núcleo urbano del país y su área
        metropolitana se conoce también con el nombre de Gran Santiago.
      </p>
    </div>
  </body>
</html>
```

Ao visualizar o exemplo anterior no navegador, temos:

![Div e Span](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/01-html/img-div-and-span.png?raw=true)

Veja como agrupamos tudo relacionado a um país em um `div`. Isso é útil porque cria seções que seguem uma ordem lógica. Mas, mais importante, ter essas seções separadas permite que você forneça estilos diferentes para cada seção: a cor do plano de fundo e a cor da fonte variam para cada país. O mesmo acontece com as palavras que mostramos em amarelo. Graças a `span` nós podemos fazer com que certas partes do texto tenham um estilo diferente. 

