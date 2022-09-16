
# Intro

Quando começarmos a digitar algum código em js, a primeira palavra (que é uma palavra chave) geralmente é uma função, seguida
de uma mensagem dentro e um final (;). Exemplo, alert("hello world");. Neste caso, o alert é a função, ("hello world") é a menssagem e ";" é o que finaliza o nosso código.

A palavra-chave é uma função pq adiciona uma função a ser executada pelo site, adiciona um comportamento para ser executado. No caso do alert, seria executar uma caixa de mensagem com a frase "hello world". Essa mensagem entre "" é dado como uma string.

O computador pega essa string dentro do "" e interpreta como texto. Que nada mais é uma forma de classificar um dado, string é um dado, que neste caso vai ser executado como uma mensagem.

Além da string, temos numbers (1,2,3) e também temos o Boolean (que descreve se os dados são false or true). Também temos o
typeof (); que diz qual tipo dado está dentro do (). 

Outro elemento importante do JS, são as variáveis. Var é uma palavra-chave, assim como alert ou prompt. Isso diz que estamos criando uma nova variável ou um novo container de dados e esse container tem o nome (e podemos colocar qualquer coisa), vamos chamar de myName. 

Agora, colocamos essa variável para ser = (igual) a um valor. Neste exemplo, pode ser o seu nome "Breno" (uma string). Sendo assim, a variável ficaria assim var myName = "Breno"; e guardaria a string "Breno" dentro da "memória". Var é chamado de variável pq podemos variar o tipo de dado a ser armazenado nela (a partir do ES6, temos const e let como alternativas ao var).

Lembrar que não precisamos ficar repetindo "var" toda hora. Ele só é usado quando você está construindo uma nova caixa ou container para conter os seus dados ou quando está construindo uma variável. Quando você decidir uma variável ou mudar a variável, não é necessário usar a palavra-chave "var" de novo.

Para nomear uma variável, não se pode colocar "var" isolado de novo, não pode colocar myname is (tudo junto, não pode espaçar), não pode colocar número como 123 (mas pode colocar my123, por exemplo) e pode colocar qualquer um desses caracteres, abc123$_, como caracteres (nenhum outro tipo é válido).

Um exemplo seria, posso chamar uma variável de $mynme ou my_name (mas nunca usar "-", como vemos nos IDs ou Classes de HTML). Uma boa prática é sempre usar o "modo camelo"(camel-case), onde você começa o nome da sua variável com letra minuscula e todo o resto depois vai com as iniciais maiúscula. Exemplo: userScoreFinal = 12; ou myNameIs = "Breno";




# Abordando melhor as strings 

Com strings, é possível somar objetos, como 1+2 ou a+b. Criando novas strings como 3 ou ab. Chama-se concatenation, onde ele
vai concatenar (juntar) duas strings em uma só. É possível fazer isso com o exemplo básico de alert("hello" + " world");

É possível concatenar duas variáveis e uma string, para emitir um alert(var + " " + var);

Agora, sobre length (para saber o comprimento de uma string ou o número de caracteres dentro da string). É possível criar um prompt (tela para escrever), com prompt("texto");

Um exemplo de contador de caracteres, estilo o do twitter antigo, é esse:

var tweet = prompt("Tell me more: ");
var tweetCount = tweet.length;
alert("You have written " + tweetCount + ". Now you have only " + (140 - tweetCount) + " left.");


A próxima função se chama .Slice (fatiar). Primeiro, tem que lembrar que programas começam contando a partir do zero. Para cortar um letra dentro do nome "Breno", seria necessário usar:

```
var name = "Breno";
name.slice(0,1);
```

Dessa forma, o slice cortaria apenas o "B" do nome, já que você está especificando que é o 0 e o 1 é, continue até mas não inclua, no caso, do "r" para frente.

Caso fosse:

```
var name = "Breno";
name.slice(0,3);
```

Ele iria cortar o "BRE" e deixar o "NO". Pois, iria começar do 0 (B) até o 3 (N), mas sem incluir ele. Uma forma bem interessante de entender, é pegar o número da direita e diminuir do dá esquerda. Exemplo:

```
var name = "Breno";
name.slice(1,3);
```

3 - 1 = 2. logo, pegaria "RE" apenas para cortar.

Um exemplo para colocar o máximo de caracteres para ser usar em uma caixa de texto, é assim:

```
var tweet = prompt("Tell me more: ");
var tweetSlice = tweet.slice(0,140);
alert(tweetSlice);
```

No caso, especificamos que até 140 caracteres, ele vai recortar. Todo o resto depois dos 140 caracteres, vão ser excluídos.




# Método toUpperCase() 

toUpperCase() altera todos os caracteres da sua string para maiúsculas. Então, como nos anteriores, tal como .slice ou .length,
basta usar uma variável, exemplo, name.toUpperCase(); para transformar cada caractere na string em sua versão maiúscula. 

Existe, também a versão contrária, com toLowerCase(); que coloca eles em minusculo. Um exemplo, seria:

```
var name = "Breno"
name = name.toUpperCase(); (para colocar em maisculo)
name = name.toLowerCase(); (para colocar em minusculo)
```

Outro bom exemplo, é criar um prompt onde a pessoa precisa entrar com o nome dela. Mas se ela entrar como nome de forma minuscula, o código vai ajustar a primeira letra do nome para maiúscula e emitir um alerta de boas vindas. Ficaria assim:

```
var name = prompt("What it is your name?");
var nameChar = name.slice(0,1);
var nameUpperCase = nameChar.toUpperCase();
var restOfName = name.slice(1,name.length);
var fullNameUpper = nameUpperCase + restOfName;
alert("Hello Mr. " + fullNameUpper);
```

Acabou que temos várias variáveis (var). Primeiro para criar o prompt, sendo para isolar a letra que começa o nome da pessoa, depois precisa colocar ela maiúscula com .toUpperCase(); e depois isolar o resto do nome com o .slice. Aqui tem um truque interessante, podemos usar name.length para que qualquer que seja o comprimento do nome, sempre pegue da segunda letra do nome em diante.

Após isso, basta criar outra variável para juntar a letra maiúscula e o resto do nome e emitir o alert de boas vindas concate
nando a string e a variável final.

Faltou só adicionar uma coisa, que é o restOfName para .toLowerCase(); caso alguém coloque as outras letras do nome em maiúsculo.

Logo ficaria assim:

```
var name = prompt("What it is your name?");
var nameChar = name.slice(0,1);
var nameUpperCase = nameChar.toUpperCase();
var restOfName = name.slice(1,name.length);
var restOfNameLowerCase = restOfName.toLowerCase();
var fullNameUpper = nameUpperCase + restOfNameLowerCase;
alert("Hello Mr. " + fullNameUpper);
```



# Entrando melhor em números (numbers) 

É possível criar variáveis (var) com números dentro e executar equações. Como, var a = 1+2; ou var b = 5-3; ou var c = 5*2 ou 
var d = 4/2. Além disso, temos o modulo, que te da o restante da divisão, exemplo: var f = 9 % 6 que daria 3. Ou seja, é o que
sobra da divisão.

Tem uma coisa que acontece só na programação. Por exemplo, uma var x = 5;, pode ser modificada com x = x + 1;. Ou seja, agora o 5 seria somado com mais 1, que daria 6. Mas isso pode ser escrito de outra forma:

```
var x = 5; 
x++; 
```

O x++; é a mesma coisa que falar x = x + 1;. Também dária 6 no resultado final. Isso é chamado de expressão de incremento 
(increment). Também temos o contrário (decremento ou decrement):

```
var x = 5;
x--;
```

que é equivalente a falar x = x - 1;. Resultando em 4 (5-1). Mas lembrar que sempre estamos aumentando ou diminuindo apenas um
valor. Agora, se quisermos aumentar mais de 1 valor, podemos usar:

```
var x = 5;
x += 2;
```

Dessa forma, é a mesma coisa de dizer x = x + 2;. Resultando em 7 (5+2). Isso também funciona com divisão /= ou multiplicação com *= ou subtração -=. Podemos usar com outras var também, tipo:

```
var x = 5;
var y = 3;
x += y;
```

Logo, o resultado da 8.




# Entrando em funções (functions) 

Funções ajudam a empacotar parte do código para que ele seja executado mais de uma vez. É basicamente da mesma forma que funcio
na outros elementos. Você tem uma palavra-chave (fuction), você dá a função um nome getMilk() {inserir os valores que você quer
que seja executado dentro das chaves}. 

Depois que criarmos a function, não a necessidade de colocar a palavra-chave de novo. Então basta usar getMilk(); que o sistema
vai buscar onde está a função e executa-la. Outro elemento importante é o console.log("inserir um valor"); que registra uma string dentro do console.

Logo, ao executar um código com console.log("");, os valores dentro da string serão exibidos no console. A principal diferença entre o console.log e o alert, é que o ALERT o usuário consegue ver, qualquer visitante consegue ver o alert. Vai aparecer para ele.

Mas no caso dos logs, apenas aparecem para o console e para o desenvolvedor. Muito usado para depurar o código ou ver se acha algum bug e imprimir parte do código no console. Mas voltando as funções. As funções são ótimas para deixar o código mais seco e evitar repetições desnecessárias. Tornando ele mais curto. 

Ainda sobre funções, é possível colocar um valor especifico dentro do function getMilk(bottles) {};. Para quando ele for executando as linhas de códigos e chegar em uma que tenha "bottles", saber quantas garrafas tem que comprar (isso é um exemplo). Podemos, colocar número dentro também. Por exemplo:

```
function getMilk(bottles) {
    var cost = bottles * 1.5;

}

getMilk(2);
```

Ou seja, a função chamada getMilk(2) vai procurar dentro da função "getMilk", que vai calcular o custo de 2 garrafas, que no caso, será de 3.

Um exemplo de como modificar dentro das funções, é esse:

```
function getMilk(money) {   
  console.log("leaveHouse");
  console.log("moveRight");
  console.log("moveRight");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveRight");
  console.log("moveRight");

  var numberOfBottles = Math.floor(money / 1.5);  
    
  console.log("buy " + numberOfBottles + " bottles of milk");
  console.log("moveLeft");
  console.log("moveLeft");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveLeft");
  console.log("moveLeft");
  console.log("enterHouse");
}

getMilk(5);

```

Dessa forma, é possível especificar quanto de dinheiro nós vamos dar ao robô, em ordem dele ter que calcular pelo custo da garrafa de leite, quanto ele pode comprar de fato. Usando Math.floor(), nos conseguimos estabelecer um arredondamento para quanto ele tem que comprar de caixa de leite.

Para saber quantos dias, semanas e meses lhe faltam até completar 90 anos, podemos fazer dessa forma:

```
function lifeInWeeks(age) {   

var years = 90 - age;
var daysLeft = years * 365;
var weeksLeft = years * 52;
var monthsLeft = years * 12;
console.log("You have " + daysLeft + " days, " + weeksLeft + " weeks and " + monthsLeft + " months left.");

}

lifeInWeeks(26); 

Basta colocar a sua idade dentro de lifeInWees(); que a função irá calcular quanto que falta e printar no console. Agora, a última das ferramentas das funções, é o "return". Essa ferramenta retorna um valor, uma saída (output). No exemplo do robô indo comprar leite, podemos colocar ele para nos dar o troco da compra, baseado em quantas caixas de leite ele comprou. Assim:

function getMilk(money) {   
  console.log("leaveHouse");
  console.log("moveRight");
  console.log("moveRight");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveUp");
  console.log("moveRight");
  console.log("moveRight");

  console.log("buy " + calcBottles(money, 1,5) + " bottles of milk");
  
  console.log("moveLeft");
  console.log("moveLeft");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveDown");
  console.log("moveLeft");
  console.log("moveLeft");
  console.log("enterHouse");

  return calcChange(money, 1.5);
  
}


function calcBottles(startingMoney, costPerBottle) {

  var numberOfBottles = Math.floor(startingMoney / costPerBottle);  

  return numberOfBottles
  
}


function calcChange(startingMoney, costPerBottle) {

    var change = startingMoney % costPerBottle
    return change;

}

console.log("hey master, here is your $" + getMilk(5) + " change.");
```

Criamos duas funções a mais. Uma calcBottles(startingMoney, costPerBottle); para calcular o dinheiro inicial que iriamos usar e o custo por caixa. Dessa forma, descobririamos quantas caixas conseguiriamos comprar. Depois, usamos o calcChange() da mesma forma.

Mas agora, usando o modulo (quanto que sobrou), para saber quanto que sobrou da nossa compra e usando o return (output) para 
retornar o valor da diferença.

Dessa forma, bastava a gente adicionar um return dentro da função principal baseado na função de troco e adicionar o calcBottles na hora da compra, para ele saber quanto que vai ter que comprar. Por fim, basta chamar a função principal, getMilk e colocar quanto de dinheiro usariamos para comprar.




# RNG em JavaScript

Começamos a entrar agora em RNG no JS. O primeiro exemplo, foi um rolador de dado de 1 a 6 de forma aleatório:

```
var n = Math.random();
n = n * 6;
n = Math.floor(n) + 1;

console.log(n);
```

Onde, o Math.random(); é uma função que retorna um número aleatório de 0 até 0.99 (nunca 1), com 16 casa decimais. Só que podemos adaptar, como foi o caso. Onde queriamos um dado de 6 lados, por isso n = n * 6; e depois usamos n = Math.floor(n) para arrendondar e deixar ele inteiro. 

Só que, só fazer isso, vai jogar o intervalo para 0-5.999999. Ainda precisamos que seja de 1 até 6, como um dado de 6 lados. Logo, notem que, precisamos adicionar "+ 1" depois de Math.floor(n), para termos o dado agora com casas 1 até 6.

Tem um exemplo bem bacana, que é love mates RNG:

```
function calcLove() {
var yourName = prompt("What's your name? ");
var yourLove = prompt("The name of your true love: ");
var n = Math.random();
n = n * 100;
n = Math.floor(n) + 1;

alert(n + "% chance that " + yourName + " and " + yourLove + " will live together 4 ever <3!");

}

calcLove();
```

Usei uma função para praticar, mas ele poderia muito mais simples. Como essa:

```
prompt("What's your name?");
prompt("What is their name?");

var loveScore = Math.random() * 100;
loveScore = Math.floor(loveScore) + 1;
alert("Your love score is " + loveScore + "%");
```

Usando prompt para aparecer na tela dois locais para inserir o nome e o Math.random() * 100; para gerar números aleatórios até 99. Só que como queriamos até 100, primeiro arredondamos com Math.floor(loveScore) e depois adicionamos "+ 1;". Por fim, basta usar um alert para aparecer na tela qual foi o seu score.




# If and else (conditionals) 

No caso, o "if", é uma função em que testamos uma condição e isso é seguido imediatamente pelo bloco de código que será execu
tado, caso essa condição seja verdadeira. Então abrimos outra instrução, que é o "else", para especificar o que acontecer se essa
condição não for verdadeira. Por meio destes testes de condições, nós conseguimos controlar o fluxo do código.

Para falarmos, por exemplo, que uma variável (var) é igual a outro elemento usando "if", basta colocarmos "===". Para falarmos que
não é igual, basta usar "!==". Para falarmos, que algo é maior que o outro, basta usar ">" e menor "<". Além disso, podemos dizer
que algo é maior ou igual ">=" a alguma coisa ou menor ou igual "<=" a alguma coisa.

Também temos, outros comparativos, como o && (AND), || (OR) e o ! para (NOT).

Uma forma de usar o "if" e "else", é no exemplo da calculadora do amor:

```
prompt("What's your name?");
prompt("What is their name?");

var loveScore = Math.random() * 100;
loveScore = Math.floor(loveScore) + 1;

if (loveScore > 70) { 
alert("Your love score is " + loveScore + "%" + " and you both love each other like icecream and chocolate :)");
} else { alert("Your love score is " + loveScore + "%");
    
}
```

O que muda, é que se caso (if), o score der acima de 70%, a mensagem vai personalizada. Caso não (else), executa a mensagem normal.

Também temos, outros comparativos, como o && (AND), || (OR) e o ! para (NOT). No mesmo exemplo da calculadora:

```
prompt("What's your name?");
prompt("What is their name?");

var loveScore = Math.random() * 100;
loveScore = Math.floor(loveScore) + 1;

if (loveScore > 70) { 
alert("Your love score is " + loveScore + "%" + " and you both love each other like icecream and chocolate :)");

}

if (loveScore > 30 && loveScore < 70) {
  alert("Your love score is " + loveScore + "%" + "come back to me its almost easy");

} 

if (loveScore <= 30) {
  alert("Your love score is " + loveScore + "%" + "hakuna matata");
}

Outro exemplo sobre comparativos, é o de saber quanto tal ano é um ano bissexto ou não:

function isLeapYear(year) {

        if (year % 4 === 0) {
          if (year % 100 === 0) {
            if (year % 400 === 0) {
              return "Leap Year";
            } else {
              return "Not Leap Year."
            }
          } else {
            return "Leap Year.";
          }
        } else { 
          return "Not Leap Year.";}

  
}

isLeapYear(2100);
```




# Array JavaScript 

Uma ARRAY te permite colocar vários dados, ao invés de um como no "var();" padrão. Para colocarmos e indicarmos que estamos
tratando de uma array, basta colocar "var n = [];". 

Um exemplo, usando o array.includes (que mostra quem inclui dentro do array), é o de uma lista de convidados:

```
var guestName = prompt("Hello, tell me your name: ");

var myGuestList = ["Breno", "Felix", "Sodré", "Yan", "Leo", "João", "Cirilo"];

if (myGuestList.includes(guestName)) {
    alert("Welcome mate!");
} else {
    alert("Sorry, you are not invited.");
}
```

Primeiro, colocamos uma variável com um prompt para perguntar qual o nome do convidado. Depois, outra variável com os nomes dos
convidados dentro de uma array "[];" e por fim, colocamos os comparativos. Se (if), o seu nome estiver incluído na lista feita
(myGuestList.includes(guestName)), então ele retornara um aviso "Welcome Mate!". Caso não (else), vai retornar um aviso "You are not invited.".

É possível adicionar dados dentro do array com "push". Basta colocar a palavra-chave do array, por exemplo, temos uma variável
chamada var output = []; e para colocarmos dados dentro dessa array, basta colocar output.push(); que ele vai colocar o dado
no final da matriz (sempre no final, nunca no inicio ou de forma aleatória).

Temos o .pop também, que retira o último dado adicionado na array. Um exemplo de como usar o .push:

```
var output = [];
var count = 1; 

function fizbuzz() {
   
console.log(output);

if (count % 3 === 0 && count % 5 === 0) {
    output.push("fizbuzz");
 
}
 
if (count % 3 === 0) {
    output.push("fiz");
}
 
 else if (count % 5 === 0) {
    output.push("buzz");
 }

 else { 
  output.push(count);
      
      }
count++;


}

fizbuzz();
```

Nesse jogo de fizbuzz, todos os números perfeitamente divisiveis por 3 e 5 são substituidos por "fizz" ou "buzz", respectivamente.

Logo, usando a função fizbuzz para colocar números usando a variável var count = 1 e "count++" para continuar incrementando +1 
dentro do array. COnseguimos criar o jogo com os "if" testando se o número for, usar output.push para colocar dentro da array.

 


# Loops (while e for)

while loops, executa em modo loop (sem parar) um linha de código que seja uma verdade. Quando deixar de ser verdadeiro, ele 
para e pula para a próxima linha de código. O problema com while(){} é que se você esqueceu ou cometeu um erro, como esquecer
de aumentar uma variável e você pode acabar com um loop infinito que vai "crashar" o seu código.

Um exemplo de while, pode ser aplicado no jogo fizbuzz:

```
var output = [];
var count = 1; 


function fizbuzz() {

while (count <= 100) {
    

if (count % 3 === 0 && count % 5 === 0) {
    output.push("fizbuzz");
 
}
 
else if (count % 3 === 0) {
    output.push("fiz");
}
 
 else if (count % 5 === 0) {
    output.push("buzz");
 }

 else { 
  output.push(count);
      
      }

count++;

}

console.log(output);

}

fizbuzz();
```

Também temos o FOR (loop), sendo a palavra-chave "for", seguido de (). for(i=0; i<2; i++) {}. Sendo que o "i=0;" é o começo, o ponto de partida do loop. O próximo, "i<2;" é o final do loop. E o final do loop, o "i++", é qual a mudança estamos fazendo, para qual direção estamos indo.

```
for (var numberOfBottles = 99; numberOfBottles>=0; numberOfBottles--) {
    
    var bottleWord = "bottles";
    if (numberOfBottles === 1) {
        bottleWord = "bottle";
    } else if (numberOfBottles === 0) {
		bottleWord = "No more bottles";		
	} 
    console.log(numberOfBottles + " " + bottleWord + " of beer on the wall.");
    console.log(numberOfBottles + " " + bottleWord + " of beer,");
    console.log("Take one down, pass it around,");
    console.log(numberOfBottles + " " + bottleWord + " of beer on the wall.");
 
}
```

Diferente do while, no for loop, nos pegamos as variações e o ponto de start e end e colocamos dentro do for. O interessante do
while, é que ele busca por algo estatico. Como, enquanto um jogar estiver vivo, não acabe o jogo. É quando ele estar em um certo estado e vai depender disso. O for loop é quando você quer rodar o código muitas e muitas vezes e você vai definir um começo e um fim.




# Orientação a Objeto (POO) 

Em linguagens orientadas a objeto como c#, c++ ou java, é muito comum ter POO. O JS acabou implementando também este conceito, e você pode usar tanto classes (uma categoria de objetos) e os constructors para instaciar objetos. No JS, qualquer função pode ser usada para instanciar um objeto por meio do operador new.

Um exemplo:

```
function retangulo(altura, largura) {
  this.altura = altura;
  this.largura = largura;
}

var r1 = new retangulo(4, 7);
```

Isso vai me retornar um objeto com o nome retangulo(altura: 4, largura: 7). Isso acontece, pq o this é uma referência especial que sempre se refere ao próprio objeto que está sendo construído. Como o JS podemos adicionar propriedades dinamicamentes a um obejto, eu adicionei usando o this, uma propriedade altura e uma propriedade largura. Atribuindo os valores que eu recebi como parametro do meu constructor. 

Com isso, a gente tem uma instância de um objeto. Se eu fizer de forma literal, não vai criar um objeto atrelado ao constructor retangulo.

Basta testar assim:

```
var r2 = {altura: 4, largura: 7};
```

e digitar r2 no console, vai me retornar apenas {altura: 4, largura: 7} como um objeto.

É possível também usar instanceof para saber se um determinado objeto foi instanciado com um constructor. Dessa forma:

```
r1 instanceof retangulo
```

vai retornar true.

```
r2 instanceof retangulo
```

vai retornar false.

Dá para criar uma função também, da mesma forma que eu criei propriedades com valores. Assim:

```
function retangulo(altura, largura) {
  this.altura = altura;
  this.largura = largura;
  this.area = calcularArea;
}

function calcularArea() {
  return this.altura * this.largura;
}
```

Se o meu r1 = new retangulo(4, 7) estava retornando um objeto com altura de 4 e largura de 7. Quando eu usar, r1.area(), ele vai me retornar 
28, que é a multiplicação entre 4 e 7. Lembrar de passar por meio de objeto!!!

Se eu passar calcularArea() ou atribuir um var areaTotal = r1.area, vai dar NaN (not a number) nos dois casos.



# Ternary Operator (Operador Ternário)

Avalia  uma  expressão  condicionalmente,  baseado  em  uma  expressão  de decisão. Tem  o  mesmo  comportamento  do comando if/else,  mas  trata-se  de  uma expressão, não um comando.

Um exemplo:

```
function maior(a, b) {
  return a > b ? a : b;
}
```

Ou seja, se a gente digitar maior(5, 4) no console, ele vai retornar 5. Isso acontece, pq a gente lê o return da seguinte forma. 5 (a) é maior que 4 (b) ?, se sim, me retorna "a" (que no caso, foi 5), se não (o se não, é os ":"), me retorna b. Ele iria me retornar b, caso eu entrasse com um número menor no que o b no a. Exemplo: maior(2, 4). Iria me retornar o 4.




# Funções map, filter e find

A função map transforma os elementos de um array com base em uma função de transformação recebida, devolvendo um novo array ao final do processo. Um exemplo:

```
// Transforma array de objetos para array de strings 
let names = usaPresidents.map((item) => item.name);
```

Já a função filter, filtra um array com base em uma função que é avaliada para cada elemento. Caso a função retorne true, o elemento é mantido, caso contrário o elemento é filtrado. Um novo array é devolvido ao final do processo. Exemplo:

```
// Obtém apenas presidentes do partido republicano 
let republicans = usaPresidents.filter((item) => item.party == "Republican");
```

Por fim, temos o find, a função  find  procura  o  primeiro  elemento  do  array  para  o  qual  a  função fornecida  retorna  true.  O  elemento  encontrado  é  devolvido  como  resultado,  ou  null caso não encontre. Exemplo:

```
// Encontra primeiro presidente do partido democrata 
let firstDemocratic = usaPresidents.find((item) => item.party == "Democratic");
```



# Template Literal

Template  string  (ou  template  literal)  oferece  uma  sintaxe  conveniente  para  montar uma string intercalada com variáveis, evitando uma sequência de operações de  concatenação.  Tais  templates  são  delimitados  pelo  caractere  crase  e  podem  interpolar expressões com a sintaxe ${}. Outra diferença com relação a strings literais é que elas podem conter quebras de linha.

Exemplo:

```
let a = 2, b = 3; 
let soma = a + b; 

// Template literal 
console.log(`${a} + ${b} = ${soma}`); 

// Equivale a 
console.log(a + " + " + b + " = " + soma);
```

Como é possível notar, é uma forma de concatenar as nossas variáveis com texto.