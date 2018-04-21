# Aula prática

## Modelo de Objeto de Documento \(DOM\) {#document-object-model-dom}

* Tipo: `Clase Práctica`
* Duração: `30min`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

Nesta unidade, seus professores ensinarão você:

* O que é o DOM e o que faz para nós?
* Conheça os seguintes métodos:
  * `document.getElementById()`
  * `document.getElementsByTagName()`
  * `document.getElementsByClassName()`

## Estruturas condicionais e repetitivas {#estructuras-condicionales-y-repetitivas}

* Tipo: `Clase Práctica`
* Duração: `2h`

### Objetivos {#objetivos}

* Entendendo o que é o controle de fluxo de um programa
* Entenda o que eles são `estructuras condicionales`e como eles afetam o fluxo do programa

O texto abaixo é baseado em grande medida, com alguns ajustes, no capítulo 2 do [Eloquent JavaScript](http://eloquentjavascript.net/) , por Marijn Haverbeke, 2014. Tradução em [espanhol](http://hectorip.github.io/Eloquent-JavaScript-ES-online/chapters/01_values.html) disponível graças ao [hectorip](http://hectorip.github.io/) e capítulo 6 do[JavaScript para crianças](http://pepa.holla.cz/wp-content/uploads/2015/11/JavaScript-for-Kids.pdf) , Nick Morgan, 2015;

### Controle de fluxo {#control-de-flujo}

A razão pela qual criamos programas de computador é **resolver problemas** . Um programa, como vimos, é simplesmente um conjunto de "instruções" que os computadores seguem. Esse conjunto de instruções resolve um problema. Até agora, aprendemos a obter, representar, manipular e armazenar dados `variables`. Com isso, conseguimos criar programas que resolvem problemas muito simples. Este é o caso, por exemplo, do programa que fizemos para transformar a temperatura em graus Celsius \(° C\) em Farenheit \(° F\). No entanto, para criar programas mais complexos, é necessário expandir nosso conhecimento sobre o _controle de fluxo de um programa_ e as estruturas existentes para modificar esse fluxo.

Para usar a terminologia JavaScript correta, a partir de agora, substituiremos a palavra "instruções" pela palavra "sentenças". Uma instrução JavaScript é o equivalente de uma sentença em uma linguagem humana. Entendemos, portanto, que um programa em JavaScript é uma lista de "instruções JavaScript"; isto é, um conjunto de sentenças que informa ao computador o que fazer.

#### 1. Fluxo em linha reta {#1-flujo-en-línea-recta}

Quando um programa contém mais de uma frase, elas são executadas de cima para baixo, uma por uma. Por exemplo, o programa a seguir tem três sentenças: a primeira declara uma variável chamada `name`com o valor da string 'Michelle'; o segundo, impresso no console, uma mensagem de saudação personalizada: "Olá Michelle"; e o terceiro, impresso no console, uma mensagem que diz "Que nome longo você tem!".

```text
var name = 'Michelle';
console.log('Hola ' + name);
console.log('Qué nombre tan largo tienes!');
// returns > Hola Michelle
//           Qué nombre tan largo tienes!
```

Uma representação trivial esquemática de um fluxo de controle direto seria:

![Fluxo direto](http://eloquentjavascript.net/img/controlflow-straight.svg)

#### 2. fluxo condicional {#2-flujo-condicional}

A execução de frases em linha reta não é a única opção que temos. Uma alternativa é a _execução condicional_ , em que escolhemos entre duas rotas diferentes com base em um valor `Boolean`, como este:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-if.svg)

A execução condicional é escrita com a palavra-chave `if`em JavaScript. A instrução `if`é a mais simples das estruturas de controle JavaScript. Ele é usado para executar código _se e somente se_ uma condição for verdadeira. Uma condicional diz: _"Se algo é verdade, faça isso"_ . Por exemplo, se você fez sua lição de casa, você recebe um sorvete, mas se você não fez sua lição de casa, você não recebe sorvete.

Como o exemplo abaixo mostra, uma sentença `if`tem duas partes principais: a condição e o corpo. A condição deve ser um valor `Boolean` entre parênteses. O corpo consiste em uma ou mais instruções JavaScript que serão executadas se, e somente se, a condição for verdadeira \( `Boolean`igual a `true`\).

```text
if (condición) {
  // Conjunto de sentencias a ejecutar
}
```

Quando precisamos executar várias instruções, podemos colocá-las entre chaves \({e}\). As chaves agrupam as sentenças, fazendo com que valham apenas uma. Uma seqüência de sentenças entre chaves é chamada de **bloco** \(de código\). Muitos programadores JavaScript incluem cada corpo de um `if`\(e nos loops, como você verá mais adiante\), em chaves. Eles fazem isso em nome da consistência e evitam ter que adicionar ou remover as chaves quando o número de sentenças no corpo muda. Outros, valorizam a brevidade e no caso de `if`não usar as chaves. Neste curso, sempre usaremos as chaves para nos ajudar a organizar nosso código.

Vamos voltar ao exemplo anterior e adicionar uma condição antes da frase que imprime a segunda mensagem:

```text
var name = 'Michelle';
console.log('Hola ' + name);
if (name.length > 7) {
  console.log('Qué nombre tan largo tienes!');
}
// returns > Hola Michelle
//           Qué nombre tan largo tienes!
```

Com esta modificação, antes de imprimir no console a segunda mensagem \('What a long name you have!'\), O programa verifica se o tamanho da string `name`é maior que 7. Se sim, a segunda mensagem é impressa. Caso contrário, essa sentença não é executada. Neste caso, como _Michelle_ tem 8 caracteres, a condição é `true`. Portanto, a segunda mensagem é impressa.

Vamos mudar um pouco este exemplo, modificando o valor de `name`uma 'Ana'.

```text
var name = 'Ana';
console.log('Hola ' + name);
if (name.length > 7) {
  console.log('Qué nombre tan largo tienes!');
}
// returns > Hola Ana
```

Nesta ocasião, a condição **não** é `true`\(é `false`\) porque o comprimento do nome é 3, que **não** é maior que 7. Portanto, o corpo do `if` **não** é executado. Desta forma, apenas a primeira mensagem 'Hello Ana' é executada.

**Frase if... else**

Muitas vezes, você não só terá o código que é executado quando uma condição é verdadeira, mas também que você manipula o outro caso. Esse caminho alternativo é representado pela segunda seta no diagrama de fluxo. A palavra-chave `else`pode ser usada, juntamente com `if`, para criar dois caminhos de execução separados e alternativos.

Adicionamos uma frase `else`ao nosso exemplo:

```text
var name = 'Ana';
console.log('Hola ' + name);
if (name.length > 7) {
  console.log('Qué nombre tan largo tienes!');
} else {
  console.log('Tu nombre no es muy largo');
}

// returns > Hola Ana
//           Tu nombre no es muy largo
```

Como você pode ver, o resultado deste caso é similar ao anterior, somente que se `name` **não** tiver um comprimento maior que 7, existe uma "mensagem alternativa" que é executada.

Como o exemplo abaixo mostra, as sentenças `if ... else`são semelhantes às sentenças `if`, mas incluem dois corpos. Se a condição é `true`, as sentenças do primeiro corpo são executadas; caso contrário, as sentenças do segundo corpo são executadas.

```text
if (condición) {
  Sentencias a ejecutar si condición es VERDADERA
} else {
  Sentencias a ejecutar si condición es FALSA
}
```

Se tivermos mais de dois caminhos para escolher, vários pares `if...else`podem ser "encadeados". Aqui está um exemplo:

```text
var num = parseInt(prompt('Dame un número', '0'));

if (num < 10){
  alert('Diste un número Pequeño');
}
else if (num < 100){
  alert('Diste un número Mediano');
}
else {
  alert('Diste un número Grande');
}
```

O programa primeiro verificará se ele `num`é menor que 10. Se estiver, escolha esse caminho, mostre "Você deu um número pequeno" em uma caixa de alerta e ele terminará. Se não for, tome o caminho de `else`, que em si contém um segundo `if`. Se a segunda condição \(&lt;100\) for atendida, significa que o número está entre 10 e 100, e 'Você indica um número Médio' é exibido em uma caixa de alerta. Se não for, o segundo e o último `else`são escolhidos, mostrando "Você deu um grande número".

O fluxograma deste programa é algo assim:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-nested-if.svg)

Vamos ver outro exemplo da aplicação da sentença `if...else`. Desta vez, com um vídeo de outra professora estrela da Laboratoria, Alexandra :\)

![exerc&#xED;cio orientado se ... mais JS for Kids pg 94](https://img.youtube.com/vi/-rNwUIEQJnc/0.jpg)

**Usando o Switch**

É comum ver código como este:

```text
if (variable == 'valor1') {
  accion1();
}
else if (variable == 'valor2') {
  accion2();
}
else if (variable == 'valor3') {
  accion3();
}
else {
  accionDefault();
}
```

Existe uma estrutura chamada `switch`que é feita para "despachar" de maneira mais direta. Infelizmente, a sintaxe que o JavaScript usa para isso \(que é herdada da linha da linguagem de programação C / Java\) é um pouco estranha; Uma sequência de frases `if`geralmente parece melhor. Aqui está um exemplo:

```text
switch (prompt('¿Cómo está el clima?')) {
  case 'lluvioso':
    console.log('Recuerda llevar un paraguas.');
    break;
  case 'soleado':
    console.log('Viste ligero.');
  case 'nublado':
    console.log('Sal a la calle.');
    break;
  default:
    console.log('Tipo de Clima desconocido.');
    break;
}
```

Você pode colocar qualquer número de etiquetas `case`dentro do bloco `switch`. O programa irá pular para o rótulo que corresponde ao valor que foi dado ao `switch`padrão se não houver nenhum valor correspondente. Eles começam a executar as sentenças de lá, mesmo se estiverem sob outro rótulo, até que uma sentença seja alcançada `break`\(o que em espanhol significa "parar"\).

Em alguns casos, como no caso de 'ensolarado' no exemplo, isso pode ser usado para compartilhar o código entre os casos \(é recomendado ir ao ar livre tanto para tempo ensolarado quanto nublado\). Mas cuidado: é fácil esquecer a quebra, o que fará com que o programa execute código que você não deseja executar.

Michelle então ajuda você a entender este caso um pouco melhor:

![Exemplo de comutador](https://img.youtube.com/vi/Aa0JhU6KZXs/0.jpg) 

