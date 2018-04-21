# Aula prática

## Modelo de Objeto de Documento \(DOM\) {#document-object-model-dom}

* Tipo: `Aula Prática`
* Duração: `30min`

### Objetivos de Aprendizagem {#objetivos-de-aprendizaje}

Nesta unidade, suas professoras ensinarão a você:

* O que é o DOM e para que serve?
* Conhecer os seguintes métodos:
  * `document.getElementById()`
  * `document.getElementsByTagName()`
  * `document.getElementsByClassName()`

## Estruturas condicionais e repetitivas

* Tipo: `Aula Prática`
* Duração: `2h`

### Objetivos

* Entender o que é o controle de fluxo de um programa
* Entender o que são `estruturas condicionais`e como eles afetam o fluxo do programa

O texto abaixo é baseado em grande parte, com alguns ajustes, no capítulo 2 do [Eloquent JavaScript](http://eloquentjavascript.net/) , por Marijn Haverbeke, 2014. Tradução em [espanhol](http://hectorip.github.io/Eloquent-JavaScript-ES-online/chapters/01_values.html) disponível graças ao [hectorip](http://hectorip.github.io/) e capítulo 6 do [JavaScript para crianças](http://pepa.holla.cz/wp-content/uploads/2015/11/JavaScript-for-Kids.pdf) , Nick Morgan, 2015;

## Controle de fluxo

A razão pela qual criamos programas de computador é **resolver problemas** . Um programa, como vimos, é simplesmente um conjunto de "instruções" que os computadores seguem. Esse conjunto de instruções resolve um problema. Até agora, aprendemos a obter, representar, manipular e armazenar dados em`variáveis`. Com isso, conseguimos criar programas que resolvem problemas muito simples. Este é o caso, por exemplo, do programa que fizemos para transformar a temperatura em graus Celsius \(°C\) em Farenheit \(°F\). No entanto, para criar programas mais complexos, é necessário expandir nosso conhecimento sobre o _controle de fluxo de um programa_ e as estruturas existentes para modificar esse fluxo.

Para usar a terminologia JavaScript correta, a partir de agora, substituiremos a palavra "instruções" pela palavra "sentenças". Uma instrução JavaScript é o equivalente de uma sentença em uma linguagem humana. Entendemos, portanto, que um programa em JavaScript é uma lista de "instruções JavaScript"; isto é, um conjunto de sentenças que informa ao computador o que fazer.

### 1. Fluxo em linha reta

Quando um programa contém mais de uma frase, elas são executadas de cima para baixo, uma por uma. Por exemplo, o programa a seguir tem três sentenças: a primeira declara uma variável chamada `name`com o valor da string 'Michelle'; o segundo, exibie no terminal uma mensagem de saudação personalizada: "Olá Michelle"; e o terceiro, exibido no terminal, uma mensagem que diz "Que nome longo você tem!".

```text
var name = 'Michelle';
console.log('Olá ' + name);
console.log('Que nome longo você tem!');
// returns > Olá Michelle
//           Que nome longo você tem!
```

Uma representação trivial esquemática de um fluxo de controle direto seria:

![Fluxo direto](http://eloquentjavascript.net/img/controlflow-straight.svg)

### 2. Fluxo condicional

A execução de frases em linha reta não é a única opção que temos. Uma alternativa é a _execução condicional_ , em que escolhemos entre duas rotas diferentes com base em um valor `Boolean`, como este:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-if.svg)

A execução condicional é escrita com a palavra-chave `if`em JavaScript. A instrução `if`é a mais simples das estruturas de controle JavaScript. Ela é usada para executar código _se e somente se_ uma condição for verdadeira. Uma condicional diz: _"Se algo é verdade, faça isso"_ . Por exemplo, se você fez sua lição de casa, você recebe um sorvete, mas se você não fez sua lição de casa, você não recebe sorvete.

Como o exemplo abaixo mostra, uma sentença `if`tem duas partes principais: a condição e o corpo. A condição deve ser um valor `Boolean` entre parênteses. O corpo consiste em uma ou mais instruções JavaScript que serão executadas se, e somente se, a condição for verdadeira \( `Boolean`igual a `true`\).

```text
if (condição) {
  // Conjunto de sentenças para execução
}
```

Quando precisamos executar várias instruções, podemos colocá-las entre chaves \({e}\). As chaves agrupam as sentenças, fazendo com que valham apenas uma. Uma seqüência de sentenças entre chaves é chamada de **bloco** \(de código\). Muitos programadores JavaScript incluem cada corpo de um `if`\(e nos _loops_, como você verá mais adiante\), em chaves. Eles fazem isso em nome da consistência e evitam ter que adicionar ou remover as chaves quando o número de sentenças no corpo muda. Outros, valorizam a brevidade e no caso do `if`não utilizam as chaves. Neste curso, sempre usaremos as chaves para nos ajudar a organizar nosso código.

Vamos voltar ao exemplo anterior e adicionar uma condição antes da frase que imprime a segunda mensagem:

```text
var name = 'Michelle';
console.log('Olá ' + name);
if (name.length > 7) {
  console.log('Que nome longo você tem!');
}
// returns > Olá Michelle
//           Que nome longo você tem!
```

Com esta modificação, antes de imprimir no terminal a segunda mensagem \('Que nome longo você tem!'\), O programa verifica se o tamanho da string `name`é maior que 7. Se sim, a segunda mensagem é impressa. Caso contrário, essa sentença não é executada. Neste caso, como _Michelle_ tem 8 caracteres, a condição é `true`. Portanto, a segunda mensagem é impressa.

Vamos mudar um pouco este exemplo, modificando o valor de `name`para 'Ana'.

```text
var name = 'Ana';
console.log('Olá ' + name);
if (name.length > 7) {
  console.log('Que nome longo você tem!');
}
// returns > Olá Ana
```

Neste caso, a condição **não** é `true`\(é `false`\) porque o comprimento do nome é 3, que **não** é maior que 7. Portanto, o corpo do `if` **não** é executado. Desta forma, apenas a primeira mensagem 'Olá Ana' é executada.

### **Sentença **_**if... else**_

Muitas vezes, você não só terá o código que é executado quando uma condição é verdadeira, mas também quando acontece o outro caso. Esse caminho alternativo é representado pela segunda seta no diagrama de fluxo. A palavra-chave `else`pode ser usada, juntamente com `if`, para criar dois caminhos de execução separados e alternativos.

Adicionamos uma sentença`else`ao nosso exemplo:

```text
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

Como você pode ver, o resultado deste caso é similar ao anterior, somente que se `name` **não** tiver um comprimento maior que 7, existe uma "mensagem alternativa" que é executada.

Como o exemplo abaixo mostra, as sentenças `if ... else`são semelhantes às sentenças `if`, mas incluem dois corpos. Se a condição é `true`, as sentenças do primeiro corpo são executadas; caso contrário, as sentenças do segundo corpo são executadas.

```text
if (condição) {
  Sentenças para execução se a condição for VERDADEIRA
} else {
  Sentenças para execição se a condição é FALSA
}
```

Se tivermos mais de dois caminhos para escolher, vários pares `if...else`podem ser "encadeados". Aqui está um exemplo:

```text
var num = parseInt(prompt('Digite um número', '0'));

if (num < 10){
  alert('Você digitou un número pequeno');
}
else if (num < 100){
  alert('Você digitou um número médio');
}
else {
  alert('Você digitou um número grande');
}
```

O programa primeiro verificará se  `num`é menor que 10. Se for, escolha esse caminho, mostra "Você digitou um número pequeno" em uma caixa de alerta e ele terminará. Se não for, toma o caminho de `else`, que em si mesmo contém um segundo `if`. Se a segunda condição \(&lt;100\) for atendida, significa que o número está entre 10 e 100, e 'Você digitou um número médio' é exibido em uma caixa de alerta. Se não for, o segundo e o último `else`são escolhidos, mostrando "Você digitou um número grande".

O fluxograma deste programa é algo assim:

![Fluxo condicional](http://eloquentjavascript.net/img/controlflow-nested-if.svg)

Vamos ver outro exemplo da aplicação da sentença `if...else`. Desta vez, com um vídeo de outra professora estrela da Laboratoria, Alexandra :\)

![exerc&#xED;cio orientado se ... mais JS for Kids pg 94](https://img.youtube.com/vi/-rNwUIEQJnc/0.jpg)

### **Usando o **_**Switch**_

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

Existe uma estrutura chamada `switch`que é feita para "decidir" de maneira mais direta. Infelizmente, a sintaxe que o JavaScript usa para isso \(que é herdada da linha da linguagem de programação C/Java\) é um pouco estranha. Uma sequência de frases `if`geralmente parece melhor. Aqui está um exemplo:

```text
switch (prompt('Como está o tempo?')) {
  case 'chuvose':
    console.log('Lembre-se de levar um guarda-chuva.');
    break;
  case 'ensolarado':
    console.log('Vista roupas leves.');
  case 'nublado':
    console.log('Saia para a rua.');
    break;
  default:
    console.log('Tipo de Tempo desconhecido.');
    break;
}
```

Você pode colocar qualquer número de etiquetas `case`dentro do bloco `switch`. O programa irá pular para o rótulo que corresponde ao valor que foi dado ao `switch`padrão se não houver nenhum valor correspondente. Eles começam a executar as sentenças de lá, mesmo se estiverem sob outro rótulo, até que uma sentença seja alcançada `break`\(o que em português significa "parar"\).

Em alguns casos, como no caso de 'ensolarado' no exemplo, é possível compartilhar o código entre os casos \(é recomendado ir ao ar livre tanto para tempo ensolarado quanto nublado\). Mas cuidado: é fácil esquecer o `break`, o que fará com que o programa execute um código que você não deseja executar.

Michelle então ajuda você a entender este caso um pouco melhor:

![Exemplo de comutador](https://img.youtube.com/vi/Aa0JhU6KZXs/0.jpg) 

