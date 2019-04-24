---
layout: default
title: Simple Values
permalink: /outline/simple_values.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/simple_values.html

{% endcomment %}

<section>
Valores simples
----------------------------------------
{: .slide-title .chapter}

* Strings
* Booleanos e nil
* Palavras-chaves
* Números
  - Aritimética

* Atribuições: `def`
</section>

<section>
## Valores simples

#### <button class="link" ng-model="block71" ng-click="block71=!block71">Introdução</button>

> Para poder fazer qualquer coisa numa linguagem de programação, precisamos
> ter valores para poder fazer algo interessante. Em Clojure, valores simples
> são números, texto, booleanos, nil e chaves.
> In order to do anything in a programming language, you need to have
> values to do stuff with. In Clojure, simple values are numbers,
> strings, booleans, nil and keywords.
{: ng-show="block71" .description}
</section>

<section ng-controller="NarrativeController">
### Strings
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> O que é uma string? É só um pedaço de texto. Para criar uma string,
> você coloca algum texto entre aspas. 
> Olhe o último exemplo. Uma barra invertida é como a gente consegue
> colocar uma aspa dentro de uma string. Não tente usar aspas simples para
> criar a string.
{: ng-show="block21" .description}

> Referência: [String](http://clojurebridgesp.github.io/community-docs/docs/clojure/string/)
{: ng-show="block21" .description}

```clojure
"Hello, World!"
"Essa é uma string maior que eu escrevi só pra ter um exemplo legal."
"Maria disse: \"Acho que a gente deveria ir no Mica.\""
```
</section>

<section ng-controller="NarrativeController">
### Booleanos e nil
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> Um booleano é um valor que é verdadeiro ou falso, e você pode usar esses
> valores com esses nomes em inglês: `true` e `false`, respectivamente.
> É bastante comum em programação termos a necessidade de fazer uma pergunta
> de verdadeiro ou falso ou "sim ou não", como "Esse curso é no semestre atual?" ou 
> "O aniversário desta pessoa é hoje?". Quando fazemos estas perguntas, temos
> uma resposta que é booleana.
{: ng-show="block31" .description}

> Existe um outro valor `nil`, que se comporta como se fosse `false` quando o usamos
> num contexto booleano. Mas `nil` significa que não existe valor e não é um boolean.
{: ng-show="block31" .description}

> Referência: [Verdade](http://clojurebridge.github.io/community-docs/docs/clojure/truthiness/)
{: ng-show="block31" .description}


```clojure
true
false
nil
```
</section>

<section ng-controller="NarrativeController">
### Palavras-chaves
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block41" ng-click="block41=!block41"></button>

> Palavras-chaves, ou _keywords_ são o tipo básico mais estranho dos valores. Algumas linguagens de programação
> possuem um conceito similar. No entanto, palavras-chaves não tem um correspondente análogo do mundo real, como
> números, strings ou booleanos. Você pode pensar que elas são um tipo especial de string, um que é 
> usado para dar nomes. Em geral são usadas como a chave de um par chave-valor para mapas (uma estrutura
> de dados; vamos aprender isso depois).
{: ng-show="block41" .description}


```clojure
:trinta
:primeiro
:ultimo
```
</section>

<section ng-controller="NarrativeController">
### Números

#### Inteiros <button class="link" ng-bind-html="details" ng-model="block81" ng-click="block81=!block81"></button>

> Clojure tem vários tipos de número.
{: ng-show="block81" .description}

> Primeiramente existem os inteiros. Inteiros (ou integer) incluem o zero, todos os números 
> inteiros positivos e todos os inteiros negativos. E você escreve do mesmo jeito que escreveria
> normalmente num texto.
{: ng-show="block81" .description}

```clojure
0
12
-42
```
</section>

<section ng-controller="NarrativeController">
#### Números decimais <button class="link" ng-bind-html="details" ng-model="block91" ng-click="block91=!block91"></button>

> Também temos os números decimais, que às vezes também são chamados de _floats_ ou números
> de ponto flutuante. Separamos a parte inteira da parte decimal usando o `.`, e o Clojure
> já considera aquele número como decimal.
{: ng-show="block91" .description}

```clojure
0.0000072725
10.5
-99.9
```
</section>

<section ng-controller="NarrativeController">
#### Frações <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> Finalmente temos frações, também chamadas de `ratios` ou razões. Computadores
> não conseguem representar perfeitamente todos os floats, dízimas periódicas por exemplo,
> mas frações são sempre exatas. Usamos uma barra junto aos números para escrevê-las:
{: ng-show="block101" .description}

> Note que, assim como na matemática, o [denominador](https://pt.wikipedia.org/wiki/Fra%C3%A7%C3%A3o)
> da fração nunca pode ser `0`.
{: ng-show="block101" .description}

```clojure
1/2
-7/3
```
</section>

<section>
### Aritimética
{: .slide_title .slide}

#### <button class="link" ng-model="block111" ng-click="block111=!block111">Introdução</button>

> Você pode somar, subtrair, multiplicar e dividir números. Em Clojure,
> aritimética é um pouquinho diferente do jeito que você escreve normalmente
> num caderno. Olhe esses exemplos:
{: ng-show="block111" .description}

```clojure
(+ 1 1)  ;=> 1 + 1 = 2
(- 12 4) ;=> 12 - 4 = 8
(* 13 2) ;=> 13 * 2 = 26
(/ 27 9) ;=> 27 / 9 = 3
```
</section>

<section ng-controller="NarrativeController">
### Notação infixa vs prefixa
{: .slide-title .slide}

<button class="link" ng-bind-html="details1" ng-model="block121" ng-click="block121=!block121"></button>
<button class="link" ng-bind-html="details2" ng-model="block122" ng-click="block122=!block122"></button>

> Em Clojure, `+`, `-`, `*` e `/` aparecem antes dos dois números. Isso é chamado
> de _notação prefixa_. O que estamos acostumados a ver é chamado de 
> _notação infixa_, onde a operação aritimética está entre os dois operandos.
{: ng-show="block121" .description}

> Linguagens como **JavaScript** usam notação **infixa**, enquanto 
> **Clojure** usa apenas notação **prefixa**. Notação **prefixa** é 
> útil em vários casos. Veja esse exemplo de uma expressão infixa e o seu 
> equivalente em prefixa:
{: ng-show="block122" .description}

```clojure
Infixa:  1 + 2 * 3 / 4 + 5 - 6 * 7 / 8 + 9

Prefixa: (+ (- (+ (+ 1 (/ (* 2 3) 4)) 5) (/ (* 6 7) 8)) 9)
```
</section>

<section ng-controller="NarrativeController">
### Por que prefixa é melhor?

#### Precedência explicita <button class="link" ng-bind-html="details" ng-model="block131" ng-click="block131=!block131"></button>

> Na expressão anterior as duas versões são um pouco confusas,
> mas perceba que na versão prefixa você não precisa nem pensar na 
> ordem de precedência dos operadores. Como cada expressão começa com 
> o operador antes de qualquer operando e toda a expressão está entre
> parênteses, todas as precedências estão explícitas.
{: ng-show="block131" .description}

```clojure
Infixa:  1 + 2 / 3
Prefixa: (+ 1 (/ 2 3))
```

#### Menos repetição <button class="link" ng-bind-html="details" ng-model="block132" ng-click="block132=!block132"></button>

> Outra razão pela qual a notação prefixa pode ser legal é que ela pode
> tornar expressões grandes menos repetitivas. Com notação prefixa, se 
> precisamos usar o mesmo operador com vários operandos, não precisamos
> repetir o operador entre eles.
{: ng-show="block132" .description}

```clojure
Infixa:  1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9
Prefixa: (+ 1 2 3 4 5 6 7 8 9)
```
</section>

<section ng-controller="NarrativeController">
### Aritimética com todos os tipos de número

<button class="link" ng-bind-html="details" ng-model="block141" ng-click="block141=!block141"></button>

> Até agora só fizemos operações aritiméticas com inteiros. No entanto
> podemos usar decimais ou frações também nessas operações, ou mesmo misturar
> os tipos. Veja estes exemplos:
{: ng-show="block141" .description}

```clojure
(+ 4/3 7/8)   ;=> 53/24
(- 9 4.2 1/2) ;=> 4.3
(/ 27/2 1.5)  ;=> 9.0
```
</section>


<section ng-controller="NarrativeController">
## Atribuições: `def`

#### <button class="link" ng-model="block161" ng-click="block161=!block161">Introdução</button>

> Se tivéssemos que digitar os mesmos valores várias e várias vezes, seria
> bastante difícil escrever um programa. O que precisamos é poder dar nomes
> a esses valores, assim podemos apenas nos referir a eles de uma maneira fácil
> de lembrar. Isso é chamado de atribuição.
{: ng-show="block161" .description}
</section>

<section ng-controller="NarrativeController">
#### Dar nomes a valores: `def`

#### <button class="link" ng-bind-html="details" ng-model="block171" ng-click="block171=!block171"></button>

> Podemos dar um nome a um valor usando `def`. Quando um nome é 
> atribuído a um valor, esse nome é chamado de *símbolo*.
{: ng-show="block171" .description}

> Referência: [Atribuição def](http://clojurebridge.github.io/community-docs/docs/clojure/def/)
{: ng-show="block171" .description}

```clojure
(def mangas 3)
(def laranjas 5)
(+ mangas laranjas)
;=> 8
```
</section>

<section ng-controller="NarrativeController">
#### Atribuindo resultados a símbolos <button class="link" ng-bind-html="details" ng-model="block181" ng-click="block181=!block181"></button>

> Podemos atribuir mais do que valores simples a símbolos. Tente o seguinte.
> Olhe a última linha e veja como podemos usar os símbolos sozinhos para se referir
> ao seu valor.
{: ng-show="block181" .description}

```clojure
(def fruta (+ mangas laranjas))
(def valor-medio-das-frutas (/ fruta 2))
valor-medio-das-frutas
;=> 4
```
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Voltar ao <a href="javascript:;" onClick="Reveal.slide(1);">primeiro slide</a>,
ou ir para o [índice do currículo](/curriculum/#/1).
</section>
