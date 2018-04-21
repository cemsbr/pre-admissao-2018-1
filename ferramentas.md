# Ferramentas

## Ferramentas {#herramientas}

Aqui você encontrará links para ferramentas que acreditamos que podem ajudá-lo a enfrentar o desafio que propusemos para essa semana de pré-lançamento. Essas ferramentas ajudarão você a organizar a maneira como trabalha com seus parceiros / trios e a maneira como eles mantêm e apresentam seu código. As ferramentas que queremos que você explore são:

1. github
2. Trello
3. Revisão de código
4. Caneta de código \(seu professor explicará como essa ferramenta funciona\)
5. Um guia de estilo JavaScript

| \# | Ferramenta | Link |
| --- | --- | --- | --- | --- | --- | --- |
| 1,1 | Github | [Vídeo](https://www.youtube.com/watch?v=GDFr8j_ZHwY) . |
| 1,2 | Github | [Lendo](https://laboratoria1.gitbooks.io/manual-git/) . |
| 2,1 | Trello | [Lendo](https://trello.com/guide/getting-started.html) . |
| 2,2 | Trello | [Vídeo](https://help.trello.com/article/899-getting-started-video-demo) . |
| 03 | Revisão de Código | Ver abaixo |
| 04 | Caneta de código | Ver abaixo |

### Revisão de código: {#code-review}

Quando eles estiverem mais avançados em seu desafio, teremos um espaço especial no qual você terá a possibilidade de fazer comentários e observações sobre o código de outro grupo de trabalho. Esta atividade objetivo é ser capaz de colaborar com outros colegas: Você terá a oportunidade de aprender com o trabalho dos outros e também para dar-lhes idéias para eles para que eles possam melhorar o seu código. A dínamca é a seguinte:

Cada par / trio expõe seu código ao resto do elenco. Todos comentam / discutem o código que está sendo apresentado. Todos esses comentários ajudarão você e seu grupo a melhorar o código deles. Neste exercício **melhora** emnós chamamos isso de _refatoração_ .

O importante é tentar entender o código do meu parceiro, ou seja, o que ele fez, como ele pensou sobre o problema, como ele construiu a solução, etc. Você tem que tentar dar soluções baseadas na lógica da outra pessoa, ao invés de dizer "faça assim", "mude", "isso está errado", "eu fiz aquilo".

Você deve considerar que:

1. **Todas as soluções são válidos** : muitos códigos podem alcançar a solução, uma vez que a nossa forma de escrever e acho que o código é pessoal, portanto, cada código é único Melhor ajuste: a idéia de revisão do código é para achar que o código é mais preciso, isto é, é autoexplicativo, refatorado, tem comentários, tem boas práticas, etc. Ser capaz de aprender e integrá-lo na aprendizagem.
2. **Aproveite o aprendizado** : não importa que você não atinja a solução perfeita, o importante é aproveitar a instância de aprendizado para buscar melhorias ou soluções para o que não encontramos.
3. **Irmandade** : a visão de outras companheiras pode me ajudar. Se eu não tiver a solução, meu time provavelmente tem isso.

Você pode considerar:

1. **Documentação** : O código é devidamente documentado e comentado? \(Possíveis respostas: Precisa de mais trabalho / Algo / Sim, é ótimo\). Onde a documentação deveria melhorar?
2. **Tratamento de erros** : o código manipula erros corretamente? \(Possíveis respostas: Precisa de mais trabalho / Algo / Sim, é ótimo\). Onde o tratamento de erros deve ser melhor?
3. **Sugestões** : Forneça duas sugestões para o autor do código sobre como melhorar o código.
4. **LEMBRE-SE ...** A qualidade do código raramente é em preto e branco. Haverá discordâncias, diferentes soluções corretas e preferências pessoais.

### Um guia de estilo JavaScript {#una-guía-de-estilo-de-javascript}

[Versão em inglês](https://danielasarzosa.gitbooks.io/preadmision-20181/content/README-EN.md)

#### Regras Básicas {#reglas-básicas}

**Termine cada instrução com um ponto e vírgula.**

_**Termine cada afirmação com um ponto e vírgula.**_

eslint: [semi](http://eslint.org/docs/rules/semi)

```text
var x = 5   // ✗ evitar
var x = 5;  // ✓ ok
```

**Use 2 espaços como recuo.**

_**Use 2 espaços para recuo.**_

eslint: [recuo](http://eslint.org/docs/rules/indent)

```text
// ✗ evitar
function hello(name) {
console.log('hi', name);
}

// ✓ ok
function hello(name) {
  console.log('hi', name);
}
```

**Nomes de variáveis ​​e funções**

**Use nomes descritivos em inglês e no formato camelCase.**

_**Use nomes descritivos, em inglês, usando o camelCase.**_

eslint: [id-length](http://eslint.org/docs/rules/id-length)   
eslint: [camelcase](http://eslint.org/docs/rules/camelcase)

```text
// ✗ evitar
const OBJEcttsssss = {};
const this_is_my_object = {};`
const miObjecto = {};
function c() {}

// ✓ ok
const thisIsMyObject = {};
function thisIsMyFunction() {}
```

#### Uso de espaços em branco {#uso-de-espacios-en-blanco}

**Onde adicionar espaços**

**Adicione um espaço após as palavras-chave.**

eslint: [espaçamento de palavra-chave](http://eslint.org/docs/rules/keyword-spacing)

```text
if (condition) { ... }   // ✓ ok
if(condition) { ... }    // ✗ evitar
```

**Adicione espaços em cada lado dos operadores.**

Com exceção dos operadores de incremento e decremento \(por exemplo, `i++`o `i--`\).   


eslint: [space-infix-ops](http://eslint.org/docs/rules/space-infix-ops)

```text
// ✗ evitar
var x=2;
var message = 'hello, '+name+'!';

// ✓ ok
var x = 2;
var message = 'hello, ' + name + '!';
```

**Adicione um espaço após as vírgulas.**

Exceto se for o último símbolo na linha.   


eslint: [espaçamento entre vírgulas](http://eslint.org/docs/rules/comma-spacing)

```text
// ✓ ok
var list = [1, 2, 3, 4];
function greet(name, options) { ... }

// ✗ evitar
var list = [1,2,3,4];
function greet(name,options) { ... }
```

**Adicione um espaço antes dos blocos.**

eslint: [space-before-blocks](http://eslint.org/docs/rules/space-before-blocks)

```text
if (admin){...}     // ✗ evitar
if (admin) {...}    // ✓ ok
```

**Use espaços nos comentários.**

eslint: [espaçado-comentário](http://eslint.org/docs/rules/spaced-comment)

```text
//comment           // ✗ evitar
// comment          // ✓ ok

/*comment*/         // ✗ evitar
/* comment */       // ✓ ok
```

**Adicione um espaço entre dois pontos e pares de chaves de valor.**

eslint: [espaçamento entre chaves](http://eslint.org/docs/rules/key-spacing)

```text
var obj = { 'key' : 'value' };    // ✗ evitar
var obj = { 'key' :'value' };     // ✗ evitar
var obj = { 'key':'value' };      // ✗ evitar

var obj = { 'key': 'value' };     // ✓ ok
```

**Onde não adicionar espaços**

**Evite o uso de vários espaços em branco, exceto o recuo.**

eslint: [não-multi-espaços](http://eslint.org/docs/rules/no-multi-spaces)

```text
const id =    1234;    // ✗ evitar

const id = 1234;       // ✓ ok
```

**Evite espaços em branco entre parênteses.**

eslint: [espaço-em-parens](http://eslint.org/docs/rules/space-in-parens)

```text
getName( name )     // ✗ evitar

getName(name)       // ✓ ok
```

**Evite usar espaços antes dos parênteses da função declarada.**

eslint: [space-before-function-paren](http://eslint.org/docs/rules/space-before-function-paren)

```text
function name (arg) { ... }   // ✗ evitar
function name(arg) { ... }    // ✓ ok

run(function () { ... })      // ✗ evitar
run(function() { ... })       // ✓ ok
```

**Evite usar espaços entre o identificador da função e sua chamada.**

eslint: [func-call-espaçamento](http://eslint.org/docs/rules/func-call-spacing)

```text
console.log ('hello'); // ✗ evitar

console.log('hello');  // ✓ ok
```

#### **Como usar linhas em branco** {#cómo-usar-líneas-en-blanco}

**Não use várias linhas em branco.**

eslint: [no-multiple-empty-lines](http://eslint.org/docs/rules/no-multiple-empty-lines)

```text
// ✗ evitar
var value = 'hello world';


console.log(value);

// ✓ ok

var value = 'hello world';
console.log(value);
```

**Não usa linhas de preenchimento em branco entre os blocos.**

eslint: [blocos acolchoados](http://eslint.org/docs/rules/padded-blocks)

```text
if (user) {
                           // ✗ evitar
  const name = getName();

}

if (user) {
  const name = getName();    // ✓ ok
}
```

#### **Outras dicas de formatação** {#otros-consejos-de-formato}

**Use aspas simples nas cadeias de texto.**

Com a exceção para evitar texto com escape.   
_Exceto quando você precisa usar aspas simples em sua string._

eslint: [citações](https://eslint.org/docs/rules/quotes)

```text
var str = "hi";   // ✗ evitar

var str = 'hi';   // ✓ ok
```

**Evite pontos decimais flutuantes.**

eslint: [sem-decimal-flutuante](http://eslint.org/docs/rules/no-floating-decimal)

```text
const discount = .5;      // ✗ evitar

const discount = 0.5;     // ✓ ok
```

**Manter a consistência de declarar propriedades de um objeto por linha.**

eslint: [object-property-newline](http://eslint.org/docs/rules/object-property-newline)

```text
const user = {
  name: 'Jane Doe', age: 30,
  username: 'jdoe86'            // ✗ evitar
};

const user = { name: 'Jane Doe', age: 30, username: 'jdoe86' };    // ✗ evitar

const user = {
  name: 'Jane Doe',  
  age: 30,
  username: 'jdoe86' // ✓ ok
};
```

**Mantenha a declaração else na mesma linha das suas chaves.**

eslint: [brace-style](http://eslint.org/docs/rules/brace-style)

```text
// ✗ evitar
if (condition) {
 // ...
}
else {
 // ...
}

// ✓ ok
if (condition) {
 // ...
} else {
 // ...
}
```

#### Boas práticas {#buenas-prácticas}

**Sempre use === em vez de ==.**

Com exceção de obj == null para verificar se o objeto é nulo \|\| indefinido   


eslint: [eqeqeq](http://eslint.org/docs/rules/eqeqeq)

```text
if (name == 'John')    // ✗ evitar
if (name === 'John')   // ✓ ok

if (name != 'John')    // ✗ evitar
if (name !== 'John')   // ✓ ok
```

**Use array literal em vez de construtores de array.**

eslint: [no-array-construtor](http://eslint.org/docs/rules/no-array-constructor)

```text
var nums = new Array(1, 2, 3);   // ✗ evitar

var nums = [1, 2, 3];            // ✓ ok
```



