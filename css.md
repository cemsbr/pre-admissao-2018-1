# CSS

## Introdução a CSS

* Tipo: `leitura`
* Formato: `ritmo próprio`
* Duração: `1h`

## Objetivos de Aprendizagem

* Entender o que é CSS e como funciona
* Conhecer as diferentes maneiras de adicionar estilos à sua página _web_
* Aprender a sintaxe CSS
* Aprender o que são seletores e quais são os seletores mais usados

## O que é CSS e como funciona?

CSS significa _Cascading Style Sheets_ \(em português: folhas de estilo em cascata\). É uma linguagem usada para definir e criar a apresentação de um documento escrito em HTML. CSS descreve como os elementos na estrutura do documento devem ser apresentados na tela. Com CSS, damos estilo e design a páginas da web. Nós mudamos cores, tamanhos, espaços, adicionamos animações, etc.

Existem três opções para incluir CSS em um documento HTML:

### 1. CSS Inline

Já vimos como adicionar estilos aos nossos elementos HTML com o atributo _style_. Por exemplo:

```text
<h1 style="color: blue;
background-color: yellow;
border: 1px solid black;">Olá, Mundo!</h1>
```

No navegador, o texto anterior ficaria assim:

![Estilo Inline](https://github.com/Laboratoria/curricula-js/blob/632783f957accef3442934c87cecd254a202f2db/03-interactive-site/00-html-and-css/02-css/img-inline-style.png?raw=true)

Essa maneira de adicionar CSS é chamada de CSS em linha, mas isso não é recomendado. Sua manutenção é complicada, já que poderíamos ter que atualizar as mesmas informações várias vezes ao longo do documento. Além disso, estamos misturando informações de estilo com informações HTML estruturais, tornando o CSS difícil de ler e entender. Manter os diferentes tipos de código separados e limpos facilitará a tarefa para aqueles que posteriormente trabalharão no código. Lembre-se de que você deve sempre pensar em organizar seu código de uma maneira que torne mais fácil para os outros entenderem o que você está fazendo.

### 2. CSS no cabeçalho

Outra opção é colocar os estilos dentro de um elemento html `<style>`que nós colocamos no`head`. Por exemplo, para representar os mesmos estilos do `h1`anterior, teríamos o seguinte:

```text
<!DOCTYPE html>
<html>
  <head>
    <title>Entendendo CSS</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }
    </style>
  </head>
  <body>
    <h1>Olá, Mundo!</h1>
  </body>
</html>
```

Este método continua a ser ineficiente. O que acontece se tivermos estilos semelhantes em outras páginas do meu site? Eu teria que repetir os estilos em cada página. E lembre-se que não gostamos de nos repetir: NSR! :\)

### 3. Folha de estilos externa CSS

A maneira ideal de adicionar estilos ao seu sítio da Web é ter um arquivo CSS separado do arquivo HTML. Todos os estilos são incluídos neste arquivo CSS externo, que as páginas HTML vinculam usando a marcação HTML `<link>`.

Vale ressaltar que este link externo pode ser um arquivo que está no seu computador ou um link para um arquivo externo da Internet. \(um endereço HTTP\)

No caso do nosso exemplo anterior com os estilos para ele `h1`, teríamos dois arquivos:

**Arquivo `index.html`**

```text
<!DOCTYPE html>
<html>
  <head>
    <title>Entendo CSS</title>
    <!--Link para arquivo que está na mesma máquina.-->
    <link rel="stylesheet" href="style.css">
    <!--Link para  arquivo que está na internet-->
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <h1>Olá, Mundo!</h1>
  </body>
</html>
```

**Arquivo `style.css`**

```text
h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}
```

A tag `<link>`tem o atributo `rel`para indicar o relacionamento do documento vinculado ao atual. O uso mais comum desse atributo é especificar o link para uma folha de estilos externa: o atributo `rel`é definido com valor `stylesheet`. O atributo `href`é definido com o caminho para a folha de estilo externa para formatar a página. No exemplo acima, uma vez que o arquivo para ligar está em nosso próprio ambiente, nós simplesmente colocamos o nome do arquivo: `style.css`.

### Sintaxe CSS {#sintaxis-css}

Como vimos na lição anterior, para especificar o estilo, usamos os pares `propiedades : valores`.

* Propriedades: são identificadores que indicam às pessoas qual recurso de estilo \(largura, cor de fundo, fonte\) queremos alterar.
* Valores: cada propriedade recebe um valor, que indica como queremos alterar essa característica \(por exemplo, qual fonte, qual largura ou qual cor usar\).

O par formado por uma propriedade e um valor é chamado de **declaração** CSS. Várias instruções juntas formam um **bloco de instruções** . Para definir para qual elemento da página web o estilo especificado pelo bloco de declaração deve ser aplicado, usamos um **seletor** . O seletor informa ao navegador para qual elemento \(ou elementos\) de uma Web deve aplicar um determinado estilo. Por exemplo, um seletor pode ser um título, um parágrafo, uma imagem etc. Blocos de declaração CSS pareados com seletores formam **regras CSS** .

Por exemplo, uma regra de css seria:

```text
selector
|
p { color: red; font-size: 15px; }
      |     |       |       |
      prop  valor  prop    valor
      ___________  ______________
           |              |
      declaração     declaração
      ___________________________
                  |
         bloco de declaração

/* Exemplo de uma regra css */
```

A convenção para representar o exemplo anterior é a seguinte \(é mais fácil ler quando colocamos as instruções uma abaixo da outra\):

```text
p {
  color: red;
  font-size: 15px;
}
```

Em resumo, o bloco de declaração indica o que precisa ser feito e o seletor indica a quem deve ser aplicado. Portanto, os seletores são essenciais para aplicar corretamente estilos CSS em uma página. Várias regras CSS podem ser aplicadas ao mesmo elemento HTML e cada regra CSS pode ser aplicada a um número ilimitado de elementos.

### Seletores {#selectores}

Existem vários seletores. Leia a documentação a seguir para aprender mais sobre seletores:

* [Seletores Simples - MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Selectores_simples)
* [Seletores Básicos - Livros da Web](http://librosweb.es/libro/css/capitulo_2/selectores_basicos.html)
* [Seletores de Atributos - MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Selectores_de_Atributos)
* [Pseudo Seletores - MDN](https://developer.mozilla.org/es/docs/Learn/CSS/Introduction_to_CSS/Pseudo-clases_y_pseudo-elementos)

No final da sua pesquisa, você deve saber o que é e como usar:

* Seletores de classe
* Seletores de ID

