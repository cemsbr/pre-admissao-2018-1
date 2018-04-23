# Modelo de Caixa

## Modelo de caixa e exibição {#box-model--display}

* Tipo: `leitura`
* Formato: `ritmo próprio`
* Duração: `1h`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

* Aprender o _modelo de caixa _e suas propriedades
* Entender a diferença entre _padding_, _border _e _margin_; e suas propriedades
* Usar corretamente a propriedade `box-sizing`
* Aprender os diferentes tipos de `display`
* Conhecer a diferença entre `display: none`e`visibility: hidden`

## O modelo de caixa

É hora de conhecer um dos fundamentos mais importantes do CSS: `box model` \(modelo de caixa\). É muito fácil, mas entendê-lo bem é vital para poder fazer uma boa diagramação da página.

![modelo de caixa](https://fotos.subefotos.com/e1001df7d218a9a8a8670d88628f0cc5o.png)

### O que é o modelo de caixa?

Voltando à nossa fonte MDN, no capítulo tutorial [do modelo de caixa](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Modelo_cajas) explica-se o seguinte:

> O modelo de caixa é a base da diagramação da web — cada elemento é representado como uma caixa retangular, com seu conteúdo, preenchimento \(espaço interno\), borda e margem construídas umas sobre as outras, como as camadas de uma cebola. O navegador, para interpretar o design de uma página, processa os estilos que serão aplicados à cada caixa, o tamanho das camadas da cebola e a localização de algumas caixas em relação a outras. Antes de entender como criar diagramações CSS, precisamos entender o modelo de caixa — o que veremos neste artigo.

Em outras palavras, o modelo de caixa CSS é essencialmente uma caixa retangular que envolve cada elemento HTML. Cada vez que um marcador \(_tag_\) HTML é inserido, é criada uma nova caixa, que inclui o conteúdo desse elemento.

Como um exemplo, temos o seguinte quadro, que mostra três caixas retangulares que são criados pelos três marcadores HTML usados: `<p>`, `<strong>` e novamente `<p>`.

![modelo de caixa](https://fotos.subefotos.com/bf683e9aa7e08dcc951b9b9e529ae627o.gif)

## Elementos que compõem o modelo de caixa

As partes que compõem cada caixa consistem no **conteúdo real**, **preenchimento**, **bordas** e **margens**; podemos ver a imagem abaixo que ilustra o modelo de caixa:

![modelo de caixa](http://image.ibb.co/cQZxTw/modelo_De_Caja.png)

Explicação de cada parte que compõe cada caixa:

* **Content \(**_**conteúdo**_**\):** este é o conteúdo HTML do elemento \(as palavras de um parágrafo, uma imagem, o texto de uma lista de elementos, etc.\)
* **Padding \(**_**preenchimento**_**\):** espaço livre opcional entre conteúdo e a borda.
* **Border \(**_**borda**_**\):** Linha que inclui o conteúdo e preenchimento.
* **Margin \(**_**margem**_**\):** Separação opcional existente entre a caixa e suas vizinhas.

## Propriedades dos elementos da caixa

CSS define 4 propriedades para controlar os elementos da caixa \(com exceção de _width _e _height_\):

* **Top**: lado superior
* **Right**: lado direito
* **Bottom**: lado inferior
* **Left**: lado esquerdo

![modelo de caixa](https://fotos.subefotos.com/46cd99b85adea7f3106700cd9ffa473fo.png)

## Preenchimento, borda e margem

### Preenchimento

É o **preenchimento**, ou seja, o espaço livre opcional entre o _conteúdo_ e a _borda_.

![preenchimento](https://fotos.subefotos.com/179d7bd111acebc38e6b29ed62a5522eo.png)

Seu valor pode ser definido em: **unidades de medida**, **porcentagem** ou o valor `inherit`\(especifica que o _preenchimento_ deve ser herdado do elemento pai\).

O CSS define quatro propriedades para controlar cada um dos espaços de preenchimento horizontal e vertical de um elemento:

* `padding-top`: preenchimento superior
* `padding-right`: preenchimento direito
* `padding-bottom`: preenchimento de fundo
* `padding-left`: preenchimento esquerdo

Também podemos usar a propriedade de tipo "shorthand" chamada `padding`para definir os quatro preenchimentos de um elemento simultaneamente.

Isso significa que ele suporta entre um e quatro valores, com o seguinte significado:

* Se apenas **um valor** for indicado:

  * **Todos os** preenchimentos têm esse valor

  ```css
  div {
    padding: 2em;
  }

  /* Todos os preenchimentos valem 2em */
  ```

* Se **dois valores** forem indicados:

  * O **primeiro** é atribuído ao preenchimento **superior e inferior**
  * O **segundo** é atribuído à **direita e esquerda**

  ```css
  div {
    padding: 1em 2em;
  }

  /*
   *  Superior e inferior = 1em,
   *  Esquerdo e direito = 2em
   */
  ```

* Se **três valores** são indicados :

  * O **primeiro** é atribuído ao preenchimento **superior**
  * O **segundo** valor é atribuído à **direita e esquerda**
  * O **terceiro** é atribuído ao preenchimento **inferior**

  ```css
  div {
    padding: 1em 2em 3em;
  }

  /*
   * Superior = 1em, Direito = 2em,
   * Inferior = 3em, Esquerdo = 2em
   */
  ```

* Se os **quatro valores** forem indicados :

  * Enchimentos são alocados em **ordem horária**, da seguinte maneira: superior esquerda, direita, inferior e esquerda.

  ```css
  div {
    padding: 1em 2em 3em 4em;
  }

  /*
   * Superior = 1em, Direito = 2em,
   * Inferior = 3em, Esquerdo = 4em
   */
  ```

### Borda

É a **linha** que contém o _conteúdo_ e o _preenchimento_. É aplicável a todos os elementos.

![fronteira](http://image.ibb.co/nKwpab/border_Anchos.png)

Para cada borda, você pode definir sua largura ou espessura, sua cor e seu estilo, porque a especificação do CSS define diferentes propriedades relacionadas às bordas.

### **Largura ou espessura**

Define a **espessura** de cada uma das quatro arestas dos elementos.

A largura das bordas é indicada por uma **unidade de medida**; pelas palavras-chave `thin`\(borda fina\), `medium`\(borda normal\) e `thick` \(borda larga\); ou o valor `inherit`.

### **Estilo**

O **estilo** das bordas só pode ser indicado por algumas das palavras reservadas definidas pelo CSS. Como o valor padrão dessa propriedade é `none`\(sem borda\), os elementos não mostram nenhuma borda visível, a menos que um estilo de borda seja definido explicitamente.

Na imagem a seguir, podemos ver os diferentes estilos de borda e a _palavra reservada_ para cada um deles:

![border\_styles](https://lenguajecss.com/p/css/propiedades/border-styles.png)

### **Cor**

Define a **cor** de cada uma das quatro bordas dos elementos.

Os valores que podem tomar são: [**valores de cor**](http://librosweb.es/referencia/css/colores.html) , `transparent`ou `inherit`.

**Propriedade shorthand "border"**

CSS define a propriedade de tipo "shorthand" global para definir o valor de todos os atributos de todas as bordas de forma direta:`border`.

Seu valor pode ser definido em: **largura da borda + estilo da borda + cor da borda** ou `inherit`\(especifica que a borda deve ser herdada do elemento pai\). Vamos ver o seguinte exemplo:

```css
div {
  border: 1px solid blue;
}
```

> Desta forma, com a propriedade `border`, atribuímos a **largura** , **estilo** e **cor da** borda para todos os quatro lados da caixa do elemento `div`.

Além disso, temos a possibilidade de atribuir os valores \(largura, estilo e cor\) a um determinado lado da seguinte maneira:

```css
div {
  border-top: 1px solid blue;
  border-right: 1px solid blue;
  border-bottom: 1px solid blue;
  border-left: 1px solid blue;
}
```

> [Saiba mais sobre `border`.](http://librosweb.es/libro/css/capitulo_4/bordes.html)

### Margin \(_**margem**_\)

É a **separação opcional** existente entre a caixa e o caixas adjacentes.

![margem](http://image.ibb.co/hH9LgG/margin.png)

Seu valor pode ser definido em: **unidades de medida**, **porcentagem** ou `inherit` \(especifica que a configuração da margem deve ser herdada do elemento pai\).

O CSS define quatro propriedades para controlar cada um dos espaços de margem horizontal e vertical de um elemento:

* `margin-top`: margem superior
* `margin-right`: margem direita
* `margin-bottom`: margem inferior
* `margin-left`: margem esquerda

Também podemos usar a propriedade "shorthand" `margin`para definir as quatro margens de um elemento simultaneamente. Ela admite entre um e quatro valores, assim como a propriedade `padding` que vimos anteriormente.

```css
div {
  margin: 5em 4em 3em 2em;
}

/*
 * Superior = 5em, Direito = 4em,
 * Inferior = 3em, Esquerdo = 2em
 */
```

## Outras propriedades

### _**Background Image**_** \(imagem de fundo\)**

É a imagem exibida por trás do _conteúdo_ e espaços de _preenchimento_.

### _**Background color**_** \(cor de fundo\)**

É a cor exibida atrás do _conteúdo_ e _preenche o_ espaço .

> _Padding _e _Margin_ são transparentes. O espaço ocupado pelo preenchimento mostra a imagem ou a cor de fundo \(se elas estiverem definidas\) e o espaço ocupado pela margem, a imagem ou a cor de fundo de seu elemento pai \(quando definidos\). Se uma caixa define tanto uma cor quanto uma imagem de fundo, a imagem tem maior prioridade e é exibida.

## Largura e Altura

### _Width_ \(largura\)

Controla a largura da caixa ou de um elemento.

![largura](https://fotos.subefotos.com/ad307ef682632ca28282a778c74610b0o.png)

O seu valor pode ser definido em: **unidades de medida**, **percentagem**, `auto`ou `inherit` , tendo como valor inicial `auto`. A propriedade **width** não suporta valores negativos e os valores percentuais são calculados a partir da largura de seu elemento pai.

```css
div {
  width: 200px;
}
```

#### _Height_ \(altura\) {#height-alto}

Controla a altura da caixa ou de um elemento.

![altura](https://fotos.subefotos.com/4395164aa663621f860b4d12c2d8fcd5o.png)

Seu valor pode ser definido em: **unidades de Medida**, **porcentagem**, `auto`ou `inherit`, tendo como valor inicial `auto`. Como na _largura_, a propriedade **height** não suporta valores negativos. Se uma **porcentagem** for indicada, a altura do elemento pai será tomada como referência.

```css
div {
  height: 400px;
}
```

## Dimensionamento da caixa

A propriedade `box-sizing`é usada para informar ao navegador quais devem ser as propriedades de tamanho \(largura e altura\).

Também indicamos se queremos incluir o preenchimento, a borda e/ou margem.

### Valores

**Valor "content-box"**

Para o valor `content-box`, as propriedades _width_ e _height_ incluem apenas o conteúdo, não incluem _padding_, _border_ ou _margin_. Este é o valor padrão.

```css
div {
  box-sizing: content-box;
}
```

![content-box](https://fotos.subefotos.com/9958eea0026f6d90ae1cd9be0f47f2ebo.png)

**Valor "border-box"**

Para o valor `border-box`, as propriedades _width_ e _height_ incluem _padding_ e _border_, mas não _margin_.

```css
div {
  box-sizing: border-box;
}
```

![caixa de borda](http://image.ibb.co/nAbcTw/border_box.png)

> Também podemos usar o valor `inherit` que herda essa propriedade de seu elemento pai.

## _Display_

### O que é a propriedade _display_?

Estabelece o tipo de caixa gerada por um elemento. ![exibir](https://fotos.subefotos.com/7ffd4c0c33fafb4d898a16a8935a0697o.png)

### Valores

**Valor "Inline"**

A propriedade `display: inline`faz com que o elemento tenha como natureza posicionar-se em linha, ou seja, um elemento é colocado ao lado do outro e, dessa forma, ocupa apenas o espaço necessário para mostrar seu conteúdo:

![&quot;inline&quot; display](https://fotos.subefotos.com/46ddc8db6addcac25aaf5d1b79275232o.png)

Suas características são:

* Ajusta-se ao fluxo do texto
* Não pula para a próxima linha
* Pode-se aplicar a propriedade`white-space`
* Ignorará as margens _top_ e _bottom_, sendo somente possível colocar _left_ e _right_ e qualquer _padding_
* Se a propriedade _floating_ for usada, ela se tornará `block`
* Pode-se aplicar a propriedade `vertical-align`

**Valor "bloco"**

A propriedade `display: block`faz com que o elemento tenha uma natureza de posicionamento em blocos, para que sempre inicie em uma nova linha e ocupe todo o espaço disponível na linha, mesmo que seu conteúdo não ocupe todo o local:

![&quot;block&quot; display](https://fotos.subefotos.com/0a7b2184ae765750e3929af6482473bfo.png)

Suas características são:

* Se não houver largura definida, expandem-se até preencher o espaço do contêiner pai
* Podem ter margens e preenchimentos
* Se a altura não for definida, crescerão para conter seus filhos
* Por padrão, fazem quebra de linha
* Ignoram a propriedade `vertical-align`

**Valor "inline-block"**

A propriedade `display: inline-block`mistura o melhor dos dois mundos, fazendo com que os elementos se posicionem em linha, mas mantendo sua natureza de bloco, ou seja, eles podem ser alinhados:

![&quot;inline-block&quot; display](https://fotos.subefotos.com/7892f0763915a586528d36559d76a451o.png)

**Valor "**_**none**_**"**

A propriedade `display: none`remove o elemento para que ele não seja exibido na tela.

**Qual é a diferença entre "display: none" e "visibility: hidden"?**

Ambos os atributos permitem "ocultar" um elemento no navegador. No entanto, há uma diferença muito importante:

* `display: none` remove o elemento definitivamente do espaço ocupado e é substituído pelos elementos adjacentes, como se o elemento não existisse mais;

  ![&quot;none&quot; display](https://fotos.subefotos.com/54885d2a934503abd48eb254549f099fo.png)

* `visibility: hidden` oculta o elemento, mas ainda mantém o espaço ocupado, enquanto que os elementos adjacentes mantêm sua localização.

  ![oculto](https://fotos.subefotos.com/22776b343dd0dde50cf523b9544ad7d2o.png)

## **Resumo de propriedades **_**Display**_

![Propriedades de &quot;display&quot;](https://fotos.subefotos.com/5bddcb7ef810c7290e982d0ad17e4941o.png)

## Leituras complementares

Continue lendo e aprendendo sobre o modelo de caixa com os seguintes recursos:

* [Modelo da caixa - MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Modelo_cajas)
* [Modelo da Caixa - Web Books](http://librosweb.es/libro/css/capitulo_4.html)
* [Exibir - Web Books](http://librosweb.es/referencia/css/display.html)

 

