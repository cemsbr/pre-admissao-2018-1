# Modelo de Caixa

## Modelo de caixa e exibição {#box-model--display}

* Tipo: `lectura`
* Formato: `self-paced`
* Duração: `1h`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

* Aprenda o `modelo de caja`e suas propriedades
* Entenda a diferença entre _preenchimento_ , _borda_ e _margem_ ; e suas propriedades
* Use a propriedade corretamente `box-sizing`
* Aprenda os diferentes tipos de `display`
* Conheça a diferença entre `display: none`e`visibility: hidden`

### O modelo da caixa {#el-modelo-de-la-caja}

É hora de conhecer um dos fundamentos mais importantes do CSS: `box model` \(modelo em dinheiro\). É muito fácil, mas entendê-lo bem é vital para poder fazer um bom layout da web.

![modelo de caixa](https://fotos.subefotos.com/e1001df7d218a9a8a8670d88628f0cc5o.png)

#### Qual é o modelo da caixa? {#¿qué-es-el-modelo-de-cajas}

Voltando ao nosso MDN de origem, no capítulo tutorial [do modelo de caixa,](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Modelo_cajas) explica o seguinte:

> O modelo de caixa é a base do design da web - cada elemento é representado como uma caixa retangular, com seu conteúdo, preenchimento \(espaço interno\), borda e margem construídas umas sobre as outras, como as camadas de uma cebola. O navegador, para interpretar o design de uma página, processa os estilos que serão aplicados a cada caixa, o tamanho das camadas da cebola e a localização de algumas caixas em relação a outras. Antes de entender como criar designs CSS, precisamos entender o modelo de caixa - que é o que veremos neste artigo.

Em outras palavras, o modelo de caixa CSS é essencialmente uma caixa retangular que envolve cada elemento HTML. Cada vez que uma tag HTML é inserida, é criada uma nova caixa, que inclui o conteúdo desse elemento.

Como um exemplo, temos o seguinte quadro, que mostra três caixas retangulares que são criados pelos três tags HTML usados: `<p>`, `<strong>` e novamente `<p>`.

![modelo de caixa](https://fotos.subefotos.com/bf683e9aa7e08dcc951b9b9e529ae627o.gif)

#### Elementos que compõem o modelo de caixa {#elementos-que-componen-el-modelo-de-cajas}

As partes que compõem cada caixa consistem no **conteúdo real** , o **preenchimento** , as **bordas** e as **margens** ; podemos ver a imagem abaixo que ilustra o modelo de caixa:

![modelo de caixa](http://image.ibb.co/cQZxTw/modelo_De_Caja.png)

Explicação de cada parte que compõe cada caixa:

* **Conteúdo \( **_**conteúdo**_** \):** Este é o conteúdo HTML do elemento \(as palavras de um parágrafo, uma imagem, o texto de uma lista de elementos, etc.\)
* **Estofamento \( **_**preenchimento**_** \):** espaço livre opcional entre conteúdo e fronteira existente.
* **Borda \( **_**borda**_** \):** Linha que inclui o conteúdo e o preenchimento.
* **Margem \( **_**margem**_** \):** Separação opcional existente entre a caixa e o restante das caixas adjacentes.

#### Propriedades dos elementos da caixa {#propiedades-de-los-elementos-de-la-caja}

CSS define 4 propriedades para controlar os elementos da caixa \(com exceção de _largura_ e _altura_ \).

* **Parte** superior: lado superior
* **Direita** : lado direito
* **Inferior** : lado inferior
* **Esquerda** : lado esquerdo

![modelo de caixa](https://fotos.subefotos.com/46cd99b85adea7f3106700cd9ffa473fo.png)

### Preenchimento, borda e margem {#padding-border--margin}

#### Preenchimento {#padding}

É o **preenchimento** , ou seja, o espaço livre opcional entre o _conteúdo_ e a _borda_ .

![preenchimento](https://fotos.subefotos.com/179d7bd111acebc38e6b29ed62a5522eo.png)

Seu valor pode ser definido em: **unidades de medida** , **porcentagem** ou valor `inherit`\(especifica que o _preenchimento_ deve ser herdado do elemento pai\).

O CSS define quatro propriedades para controlar cada um dos espaços de preenchimento horizontal e vertical de um elemento:

* `padding-top`: enchimento superior
* `padding-right`: recheio direito
* `padding-bottom`: enchimento de fundo
* `padding-left`: enchimento esquerdo

Também podemos usar a propriedade de chamada "abreviada" de tipo `padding`para definir os quatro preenchimentos de um elemento simultaneamente.

Isso significa que ele suporta entre um e quatro valores, com o seguinte significado:

* Se apenas **um valor** for indicado :

  * **Todos os** recheios têm esse valor

  ```text
  div {
    padding: 2em;
  }

  /* Todos los rellenos valen 2em */
  ```

* Se **dois valores** forem indicados :

  * O **primeiro** é atribuído ao preenchimento **superior e inferior**
  * O **segundo** é atribuído à **direita e esquerda**

  ```text
  div {
    padding: 1em 2em;
  }

  /*
   *  Superior e inferior = 1em,
   *  Izquierdo y derecho = 2em
   */
  ```

* Se **três valores** são indicados :

  * O **primeiro** é atribuído ao preenchimento **superior**
  * O **segundo** valor é atribuído à **direita e esquerda**
  * O **terceiro** é atribuído ao preenchimento **inferior**

  ```text
  div {
    padding: 1em 2em 3em;
  }

  /*
   * Superior = 1em, Derecho = 2em,
   * Inferior = 3em, Izquierdo = 2em
   */
  ```

* Se os **quatro valores** forem indicados :

  * Enchimentos são alocados em **ordem de tempo** , como segue: superior esquerda, direita, e inferior.

  ```text
  div {
    padding: 1em 2em 3em 4em;
  }

  /*
   * Superior = 1em, Derecho = 2em,
   * Inferior = 3em, Izquierdo = 4em
   */
  ```

#### Fronteira {#border}

É a **linha** que contém o _conteúdo_ e o _preenchimento_ . É aplicável a todos os elementos.

![fronteira](http://image.ibb.co/nKwpab/border_Anchos.png)

Para cada aresta você pode definir sua largura ou espessura, sua cor e seu estilo, portanto, no CSS total, define diferentes propriedades relacionadas às arestas.

**Largura ou espessura**

Defina a **espessura** de cada uma das quatro arestas dos elementos.

A largura das bordas é indicada por uma **unidade de medida** ; por palavras-chave `thin`\(borda fina\), `medium`\(borda normal\) e `thick` \(borda larga\); ou o valor `inherit`.

**Estilo**

O **estilo** das bordas só pode ser indicado por algumas das palavras reservadas definidas pelo CSS. Como o valor padrão dessa propriedade é `none`\(sem borda\), os elementos não mostram nenhuma borda visível, a menos que um estilo de borda seja definido explicitamente.

Na imagem a seguir podemos ver os diferentes estilos de aresta e a _palavra reservada_ para cada um deles:

![border\_styles](https://lenguajecss.com/p/css/propiedades/border-styles.png)

**Cor**

Defina a **cor** de cada uma das quatro arestas dos elementos.

Os valores que podem tomar são: [**valores de cor**](http://librosweb.es/referencia/css/colores.html) , `transparent`ou `inherit`.

**Propriedade abreviada "fronteira"**

CSS define a propriedade de tipo global para definir o valor de todos os atributos de todas as bordas diretamente "taquigrafia" `border`.

Seu valor pode ser definido em: **largura da borda + estilo da borda + cor da borda** ou `inherit`\(especifica que a borda deve ser herdada do elemento pai\). Vamos ver o seguinte exemplo:

```text
div {
  border: 1px solid blue;
}
```

> Desta forma, com a propriedade `border`, atribuímos a **largura** , **estilo** e **cor da** borda para todos os quatro lados da caixa do elemento `div`.

Além disso, temos a possibilidade de atribuir os valores \(largura, estilo e cor\) a um determinado lado da seguinte maneira:

```text
div {
  border-top: 1px solid blue;
  border-right: 1px solid blue;
  border-bottom: 1px solid blue;
  border-left: 1px solid blue;
}
```

> [Saiba mais sobre `border`.](http://librosweb.es/libro/css/capitulo_4/bordes.html)

#### Margem \( _**margem**_ \) {#margin-margen}

É a **separação opcional** existente entre a caixa e o resto das caixas adjacentes.

![margem](http://image.ibb.co/hH9LgG/margin.png)

Seu valor pode ser definido em: **Unidades de medida** , **porcentagem** ou `inherit` \(especifica que a margem deve ser herdada do elemento pai\).

O CSS define quatro propriedades para controlar cada um dos espaços de margem horizontal e vertical de um elemento:

* `margin-top`: margem superior
* `margin-right`: margem direita
* `margin-bottom`: margem mais baixa
* `margin-left`: margem esquerda

Também podemos usar a propriedade de chamada "abreviada" de tipo `margin`para definir as quatro margens de um elemento simultaneamente. Isso significa que ele admite entre um e quatro valores, assim como a propriedade `padding`, que vimos anteriormente.

```text
div {
  margin: 5em 4em 3em 2em;
}

/*
 * Superior = 5em, Derecho = 4em,
 * Inferior = 3em, Izquierdo = 2em
 */
```

#### Outras propriedades {#otras-propiedades}

**Imagem de fundo \( imagem de fundo \)**

É a imagem que é exibida por trás do _conteúdo_ e _preenche o_ espaço .

**Cor de fundo \( cor de fundo \)**

É a cor que é exibida atrás do _conteúdo_ e _preenche o_ espaço .

> Preenchimento e Margem são transparentes, o espaço ocupado pelo preenchimento mostra a imagem ou a cor de fundo \(se elas estiverem definidas\) e no espaço ocupado pela margem a imagem ou a cor de fundo de seu elemento pai é exibida \(se forem definido\). Se uma caixa define uma cor e uma imagem de fundo, a imagem tem mais prioridade e é a que é exibida.

### Largura e Altura {#anchura-y-altura}

#### Largura \( _largura_ \) {#width-ancho}

Controla a largura da caixa ou um elemento.

![largura](https://fotos.subefotos.com/ad307ef682632ca28282a778c74610b0o.png)

O seu valor pode ser definido em: **unidades de medição** , **percentagem** , `auto`ou `inherit`. Sendo como valor inicial `auto`. A propriedade **width** não suporta valores negativos e os valores percentuais são calculados a partir da largura de seu elemento pai.

```text
div {
  width: 200px;
}
```

#### Altura \( _alta_ \) {#height-alto}

Controla a altura da caixa ou um elemento.

![altura](https://fotos.subefotos.com/4395164aa663621f860b4d12c2d8fcd5o.png)

Seu valor pode ser definido em: **Unidades de Medida** , **porcentagem** , `auto`ou `inherit`. Sendo como valor inicial `auto`. Como na _largura_ , a propriedade **height** não suporta valores negativos. Se uma **porcentagem** for indicada , a altura do elemento pai será tomada como referência.

```text
div {
  height: 400px;
}
```

### Dimensionamento de caixa {#box-sizing}

A propriedade `box-sizing`é usada para informar ao navegador quais devem ser as propriedades de tamanho \(largura e altura\).

Também indicamos se queremos incluir o preenchimento, a borda e / ou a margem.

#### Valores {#valores}

**Valor "caixa de conteúdo"**

Para o valor, `content-box`as _propriedades width_ e _height_ incluem apenas o conteúdo, elas não incluem o _preenchimento_ , a _borda_ ou a _margem_ . Este é o valor padrão.

```text
div {
  box-sizing: content-box;
}
```

![content-box](https://fotos.subefotos.com/9958eea0026f6d90ae1cd9be0f47f2ebo.png)

**Valor "border-box"**

Para o valor, `border-box`as _propriedades width_ e _height_ incluem o _preenchimento_ e a _borda_ , mas não a _margem_ .

```text
div {
  box-sizing: border-box;
}
```

![caixa de borda](http://image.ibb.co/nAbcTw/border_box.png)

> Também podemos usar o valor `inherit`, que é o valor que herda essa propriedade de seu elemento pai.

### Display {#display}

#### Qual é a propriedade de exibição? {#¿qué-es-la-propiedad-display}

Estabelece o tipo de caixa gerada por um elemento. ![exibir](https://fotos.subefotos.com/7ffd4c0c33fafb4d898a16a8935a0697o.png)

#### Valores {#valores}

**Valor "Inline"**

A propriedade `display: inline`faz com que o elemento tenha como natureza se posicionar online, ou seja, um elemento é colocado ao lado do outro e, portanto, ocupa apenas o espaço necessário para mostrar seu conteúdo:

![inline](https://fotos.subefotos.com/46ddc8db6addcac25aaf5d1b79275232o.png)

Suas características são:

* Ajusta-se ao fluxo do texto
* Não pule para a próxima linha
* Você pode aplicar a propriedade de `white-space`
* Ignorar as margens _superior_ e _inferior_ , você só pode colocar à _esquerda_ e à _direita_ e qualquer preenchimento
* Se a propriedade flutuante for usada, elas se tornarão `block`
* Você pode aplicar a propriedade `vertical-align`

**Valor "bloco"**

A propriedade `display: block`faz com que o elemento tenha uma natureza posicionada em blocos, para que sempre inicie em uma nova linha e ocupe todo o espaço disponível na linha, mesmo que seu conteúdo não ocupe todo o site:

![bloquear](https://fotos.subefotos.com/0a7b2184ae765750e3929af6482473bfo.png)

Suas características são:

* Se não houver largura definida, eles se expandem para preencher o espaço do contêiner pai
* Eles podem ter margens e recheios
* Se a altura não for definida, elas crescerão para conter seus filhos
* Por padrão, faz uma quebra de linha
* Eles ignoram a propriedade `vertical-align`

**Valor "inline-block"**

A propriedade `display: inline-block`mistura o melhor dos dois mundos, fazendo com que os elementos se posicionem em linha, mas mantendo sua natureza de bloco, ou seja, eles podem ser alinhados:

![inline-block](https://fotos.subefotos.com/7892f0763915a586528d36559d76a451o.png)

**Valor "nenhum"**

A propriedade `display: none`remove o elemento para que ele não seja exibido na tela.

**Qual é a diferença entre "display: none" e "visibility: hidden"?**

Ambos os atributos permitem "ocultar" um elemento no navegador. No entanto, há uma diferença muito importante:

* `display: none` remove o elemento definitivamente do espaço ocupado e é substituído pelos elementos adjacentes, como se o elemento não existisse mais.

  ![nenhum](https://fotos.subefotos.com/54885d2a934503abd48eb254549f099fo.png)

* `visibility: hidden` ela oculta o elemento, mas ainda mantém o espaço ocupado, enquanto os elementos adjacentes mantêm sua localização.

  ![oculto](https://fotos.subefotos.com/22776b343dd0dde50cf523b9544ad7d2o.png)

**Resumo do recurso**

![Exibi&#xE7;&#xE3;o de resumo](https://fotos.subefotos.com/5bddcb7ef810c7290e982d0ad17e4941o.png)

### Leituras complementares {#lecturas-complementarias}

Continue lendo e aprendendo sobre o modelo de caixa com os seguintes recursos:

* [Modelo da caixa - MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Modelo_cajas)
* [Modelo da Caixa - Web Books](http://librosweb.es/libro/css/capitulo_4.html)
* [Exibir - Web Books](http://librosweb.es/referencia/css/display.html)

 

