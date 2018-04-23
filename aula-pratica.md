# Aula prática

## Modelo de Objeto de Documento \(DOM\) {#document-object-model-dom}

* Tipo: `Aula Prática`
* Duração: `30min`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

Nesta unidade, suas professoras ensinarão a você:

* O que é o DOM e para que serve?
* Os seguintes métodos:
  * `document.getElementById()`
  * `document.getElementsByTagName()`
  * `document.getElementsByClassName()`

## Estruturas condicionais e repetitivas

* Tipo: `Aula Prática`
* Duração: `2h`

### Objetivos

* Entender o que é o controle de fluxo de um programa
* Entender o que são _estruturas condicionais _e como eles afetam o fluxo do programa

O texto abaixo é baseado em grande parte, com alguns ajustes, no capítulo 2 do [Eloquent JavaScript](http://eloquentjavascript.net/), por Marijn Haverbeke, 2014. Tradução em [espanhol](http://hectorip.github.io/Eloquent-JavaScript-ES-online/chapters/01_values.html) disponível graças ao [hectorip](http://hectorip.github.io/) e capítulo 6 do [JavaScript para crianças](http://pepa.holla.cz/wp-content/uploads/2015/11/JavaScript-for-Kids.pdf), Nick Morgan, 2015.

## Controle de fluxo

A razão pela qual criamos programas de computador é para **resolver problemas**. Um programa, como vimos, é simplesmente um conjunto de "instruções" que os computadores seguem. Esse conjunto de instruções resolve um problema. Até agora, aprendemos a obter, representar, manipular e armazenar dados em`variáveis`. Com isso, conseguimos criar programas que resolvem problemas muito simples. Este é o caso, por exemplo, do programa que fizemos para transformar a temperatura de graus Celsius \(°C\) para Farenheit \(°F\). No entanto, para criar programas mais complexos, é necessário expandir nosso conhecimento sobre o _controle de fluxo de um programa_ e as estruturas existentes para modificar esse fluxo.

Para usar a terminologia correta de JavaScript, a partir de agora, substituiremos a palavra "instruções" pela palavra "sentenças". Uma instrução JavaScript é o equivalente a uma sentença em linguagem humana. Entendemos, portanto, que um programa em JavaScript é uma lista de "instruções JavaScript", isto é, um conjunto de sentenças que informa ao computador o que fazer.

### 1. Fluxo em linha reta

Quando um programa contém mais de uma frase, elas são executadas de cima para baixo, uma por uma. Por exemplo, o programa a seguir tem três sentenças: a primeira declara uma variável chamada `name`com o valor de _string_ `'Michelle'`; a segunda exibe no terminal uma mensagem de saudação personalizada: "Olá Michelle"; e a terceira exibe "Que nome longo você tem!".

```javascript
var name = 'Michelle';
console.log('Olá ' + name);
console.log('Que nome longo você tem!');
// returns > Olá Michelle
//           Que nome longo você tem!
```

Uma representação trivial esquemática de um fluxo de controle direto seria:

![Fluxo direto](http://eloquentjavascript.net/img/controlflow-straight.svg)

### 2. Fluxo condicional

A execução de frases em linha reta não é a única opção que temos. Uma alternativa é a _execução condicional_, em que escolhemos entre duas rotas diferentes com base em um valor `Boolean`, como abaixo:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-if.svg)

A execução condicional é escrita com a palavra-chave `if`em JavaScript. A instrução `if`é a mais simples das estruturas de controle dessa linguagem. Ela é usada para executar código _se e somente se_ uma condição for verdadeira. Uma condicional diz: _"Se algo é verdade, faça isso"_. Por exemplo, se você fez sua lição de casa, recebe um sorvete, mas se você não fez sua lição, não o recebe.

Como o exemplo abaixo mostra, uma sentença `if`tem duas partes principais: a condição e o corpo. A condição deve ser um valor `Boolean` entre parênteses. O corpo consiste em uma ou mais instruções JavaScript que serão executadas se, e somente se, a condição for verdadeira \(`Boolean`igual a `true`\).

```javascript
if (condição) {
  // Conjunto de sentenças para execução
}
```

Quando precisamos executar várias instruções, podemos colocá-las entre chaves \(`{` e `}`\). As chaves agrupam as sentenças, tornando-as apenas uma. Uma sequência de sentenças entre chaves é chamada de **bloco** \(de código\). Muitos programadores JavaScript incluem chaves em todo corpo de `if`\(e nos _loops_, como você verá mais adiante\). Eles fazem isso em nome da consistência e para não ter que adicionar ou remover as chaves quando o número de sentenças no corpo mudar. Outros, valorizam a brevidade e no caso do `if`não utilizam as chaves. Neste curso, sempre usaremos as chaves para nos ajudar a organizar nosso código.

Vamos voltar ao exemplo anterior e adicionar uma condição antes da frase que imprime a segunda mensagem:

```javascript
var name = 'Michelle';
console.log('Olá ' + name);
if (name.length > 7) {
  console.log('Que nome longo você tem!');
}
// returns > Olá Michelle
//           Que nome longo você tem!
```

Com esta modificação, antes de imprimir no terminal a segunda mensagem \(_'Que nome longo você tem!'_\), o programa verifica se o tamanho da _string_ `name`é maior que 7. Se sim, a segunda mensagem é impressa. Caso contrário, essa sentença não é executada. Neste caso, como _Michelle_ tem 8 caracteres, a condição é `true`. Portanto, a segunda mensagem é impressa.

Vamos mudar um pouco este exemplo, modificando o valor de `name`para 'Ana'.

```javascript
var name = 'Ana';
console.log('Olá ' + name);
if (name.length > 7) {
  console.log('Que nome longo você tem!');
}
// returns > Olá Ana
```

Neste caso, a condição **não** é `true`\(é `false`\) porque o comprimento do nome é 3, que **não** é maior que 7. Portanto, o corpo do `if` **não** é executado. Desta forma, apenas a primeira mensagem _'Olá Ana'_  é executada.

### **Sentença **_**if... else**_

Muitas vezes, você não só terá o código que é executado quando uma condição é verdadeira, mas também quando acontece o outro caso. Esse caminho alternativo é representado pela segunda seta no diagrama de fluxo. A palavra-chave `else`pode ser usada juntamente com `if` para criar dois caminhos de execução separados e alternativos.

Adicionemos uma sentença`else`ao nosso exemplo:

```javascript
var name = 'Ana';
console.log('Olá ' + name);
if (name.length > 7) {
  console.log('Que nome longo você tem!');
} else {
  console.log('Seu nome não é longo.');
}

// returns > Olá Ana
//           Seu nome não é longo.
```

Como você pode ver, o resultado deste caso é similar ao anterior, mas se `name` **não** tiver um comprimento maior que 7, existe uma "mensagem alternativa" que é executada.

Como o exemplo abaixo mostra, as sentenças `if... else`são semelhantes às sentenças `if`, mas incluem dois corpos. Se a condição é `true`, as sentenças do primeiro corpo são executadas; caso contrário, as sentenças do segundo corpo são executadas.

```javascript
if (condição) {
  // Sentenças para execução se a condição for VERDADEIRA
} else {
  // Sentenças para execução se a condição for FALSA
}
```

Se tivermos mais de dois caminhos para escolher, vários pares `if... else`podem ser "encadeados". Aqui está um exemplo:

```javascript
var num = parseInt(prompt('Digite um número', '0'));

if (num < 10){
  alert('Você digitou um número pequeno');
}
else if (num < 100){
  alert('Você digitou um número médio');
}
else {
  alert('Você digitou um número grande');
}
```

O programa primeiro verificará se  `num` é menor que 10. Se for, escolhe esse caminho, mostra _"Você digitou um número pequeno"_ em uma caixa de alerta e ele termina. Se não for, toma o caminho do `else`, que em si mesmo contém um segundo `if`. Se a segunda condição \(`< 100`\) for atendida, significa que o número está entre 10 e 100, e _"Você digitou um número médio"_ é exibido em uma caixa de alerta. Se não for, o segundo e último `else` é escolhido, mostrando _"Você digitou um número grande"_.

O fluxograma deste programa é algo assim:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-nested-if.svg)

Vamos ver outro exemplo da aplicação da sentença `if... else`. Desta vez, com um vídeo de outra excelente professora da Laboratoria, Alexandra :\)

![exerc&#xED;cio orientado se ... mais JS for Kids pg 94](https://img.youtube.com/vi/-rNwUIEQJnc/0.jpg)

### **Usando o **_**Switch**_

É comum ver código como este:

```javascript
if (variável == 'valor1') {
  ação1();
}
else if (variável == 'valor2') {
  ação2();
}
else if (variável == 'valor3') {
  ação3();
}
else {
  açãoDefault();
}
```

Existe uma estrutura chamada `switch`que é feita para "decidir" de maneira mais direta. Infelizmente, a sintaxe que o JavaScript usa para isso \(que é herdada da linha da linguagem de programação C/Java\) é um pouco estranha. Uma sequência de frases `if`geralmente parece melhor. Aqui está um exemplo:

```javascript
switch (prompt('Como está o tempo?')) {
  case 'chuvoso':
    console.log('Lembre-se de levar um guarda-chuva.');
    break;
  case 'ensolarado':
    console.log('Vista roupas leves.');
  case 'nublado':
    console.log('Saia para a rua.');
    break;
  default:
    console.log('Tipo de tempo desconhecido.');
    break;
}
```

Você pode colocar qualquer número de etiquetas `case`dentro do bloco `switch`. O programa irá pular para o rótulo correspondente ao valor que foi dado ao `switch` ou ao `default` se não houver nenhum valor igual. Daí, eles começam a executar as sentenças, incluindo os abaixo de outro rótulo, até que uma sentença `break`  seja alcançada \(o que em português significa "pare"\).

Em alguns casos, como no caso de "ensolarado" no exemplo, é possível compartilhar o código entre os casos \(é recomendado ir ao ar livre tanto para tempo ensolarado quanto nublado\). Mas cuidado: é fácil esquecer o `break`, o que fará com que o programa execute um código que você não deseja executar.

A seguir, Michelle ajuda você a entender esse caso um pouco melhor:

![Exemplo de comutador](https://img.youtube.com/vi/Aa0JhU6KZXs/0.jpg) 

