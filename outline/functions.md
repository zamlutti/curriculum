---
layout: default
title: Funções
permalink: /outline/functions.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/functions.html

{% endcomment %}

<section>
Funções
-------------------------------
{: .slide-title .chapter}

* O que são funções?
* Dando nomes a funções
* [seção bônus] Funções que recebem outras funções
    - `map` e `reduce`
* [seção bônus] Funções anônimas
* [seção bônus] Atribuição: `let`
</section>

<section ng-controller="NarrativeController">
### O que são funções?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> Você já viu algumas funções, como `count`, `conj`, `first` e `rest`.
> Toda a aritimética que fizemos usou funções também: `+`, `-`, `*`, e `/`. 
> O que significa ser uma função então?
{: ng-show="block11" .description}

> Uma *função* é um trecho distinto e independente de código que recebe alguns
> valores como entrada (chamados de *argumentos* ou *parâmetros*) e devolve um valor
> na saída.
{: ng-show="block11" .description}

> Referência: [Básicos de funções](http://clojurebridgesp.github.io/community-docs/docs/clojure/function-creation/)
{: ng-show="block11" .description}

* `count`, `conj`, `first`
* `+`, `-`, `*`, `/`
* Um trecho de código que recebe valores e devolve um valor
</section>

<section ng-controller="NarrativeController">
#### Uma função com múltiplos argumentos <button class="link" ng-bind-html="details" ng-model="block41" ng-click="block41=!block41"></button>

> Funções também podem receber mais de um argumento. Vamos fazer uma função
> `forward-right-with-len` que recebe uma distância para frente, 
> além da tartaruga.
{: ng-show="block41" .description}

```clojure
(defn forward-right-with-len
  "Dado uma tartaruga e uma distância, ande para frente com a tartaruga e vire a sua cabeça"
  [turtle len]
  (forward turtle len)
  (right turtle 135))

(forward-right-with-len :trinity 90) ;=> {:trinity {:angle 135}}
(forward-right-with-len :neo 80)  ;=> {:neo {:angle 135}}
```
</section>

<section ng-controller="NarrativeController">
### Dando nomes a funções
{: .slide_title .slide}

#### Nomes são símbolos <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> Nomes de função são símbolos, do mesmo jeito que os símbolos usados com o `def`
> quando atribuímos nomes a valores.
{: ng-show="block61" .description}

> Símbolos devem começar com um caractere não numérico e podem conter
> caracteres alfanuméricos, além de `*`, `+`, `!`, `-`, `_`, e `?`.
> Essa flexibilidade é importante para funções, pois existem alguns
> estilos de escrita que usamos.
{: ng-show="block61" .description}

#### Dois tipos de função <button class="link" ng-bind-html="details" ng-model="block62" ng-click="block62=!block62"></button>

> Clojure tem dois tipos de função:
> 1. função que retorna um valor,
> 2. função que retorna `true` ou `false`.
> O segundo tipo é chamado de *predicado*.
{: ng-show="block62" .description}


##### Exemplos de funções predicado <button class="link" ng-bind-html="details" ng-model="block63" ng-click="block63=!block63"></button>

> Em Clojure, `=` é uma função predicado, o que pode ser algo surpreendente.
> Além disso, como em muitas outras linguagens de programação, Clojure tem 
> funções predicado para testar maior que, menor que, etc. A maioria dos 
> predicados termina com `?`, se começam com palavras.
{: ng-show="block63" .description}

> * `=`, `not=`
> * `>`, `<`, `>=`, `<=`
> * `true?`, `false?`, `empty?`, `nil?`, `vector?`, `map?`

</section>

<section ng-controller="NarrativeController">
#### [Seção bônus]

### Funções que recebem outras funções
{: .slide_title .slide}

#### <button class="link" ng-model="block71" ng-click="block71=!block71">Introdução</button>

> Algumas das funções mais poderosas que você pode usar com coleções recebem outras
> funções como argumento. Essa é uma das coisas mais mágicas sobre Clojure -- e muitas
> outras linguagens de programação. É uma ideia complicada, e pode não fazer muito sentido
> à primeira vista. Vamos ver um exemplo e aprender mais sobre isso.
{: ng-show="block71" .description}

> Referência: [Funções de alta ordem](http://clojurebridgesp.github.io/community-docs/docs/clojure/higher-order-function/)
{: ng-show="block71" .description}
</section>

<section ng-controller="NarrativeController">
#### Função `map`

#### <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> `map` é uma função que recebe outra função junto com uma coleção. 
> Ela chama a função passada em cada um dos elementos da coleção, e 
> devolve uma nova coleção com os resultados destas chamadas de função.
> É um conceito estranho, mas é a essência de Clojure e de programação
> funcional em geral.
{: ng-show="block101" .description}

```clojure
(map inc [1 2 3]) ;=> (2 3 4)
(map (partial + 90) [0 30 60 90]) ;=> (90 120 150 180)
```

> Referência:
> [partial](http://clojuredocs.org/clojure.core/partial)
</section>

<section ng-controller="NarrativeController">
#### Função `reduce`

#### <button class="link" ng-bind-html="details" ng-model="block111" ng-click="block111=!block111"></button>

> Vamos ver outra função que recebe uma função. Essa é a `reduce`, e é
> usada para transformar coleções em um único valor.
{: ng-show="block111" .description}

> `reduce` recebe os dois primeiros elementos da coleção passada e 
> chama a função passada nesses dois elementos. Em seguida, chama
> a função novamente -- dessa vez usando o resultado da chamada anterior
> da função como primeiro argumento e o próximo elemento da coleção como segundo.
> `reduce` vai fazer isso repetidas vezes até percorrer todos os elementos e
> chegar no fim da coleção.
{: ng-show="block111" .description}

```clojure
(reduce + [30 60 90])       ;=> 180
```
</section>

<section ng-controller="NarrativeController">
#### [Seção bônus]

### Funções anônimas

#### Funções sem nome <button class="link" ng-bind-html="details" ng-model="block201" ng-click="block201=!block201"></button>

> Até agora todas as funções que vimos tinham nomes, como `+` e `str` e `reduce`.
> No entanto, funções não precisam ter nome, assim como valores não precisam ter nomes.
> Chamamos funções sem nome de *funções anônimas*.
> Uma função anônima é criada com `fn`, assim:
{: ng-show="block201" .description}

> Referência: [Função anônima](http://clojurebridgesp.github.io/community-docs/docs/clojure/anonymous-function/)
{: ng-show="block201" .description}


```clojure
(fn [s1 s2] (str s1 " " s2))
```

#### vs. funções que não são anônimas <button class="link" ng-bind-html="details" ng-model="block202" ng-click="block202=!block202"></button>

> Antes de prosseguir, você deve entender que você _sempre_ está livre
> para dar um nome às suas funções. Não há nada de errado em fazer isso.
> No entanto, você _vai_ ver código Clojure com funções anônimas, então 
> deveria entender como elas funcionam.
{: ng-show="block202" .description}

```clojure
(defn junta-com-espaco
  [s1 s2]
  (str s1 " " s2))
```
</section>

<section ng-controller="NarrativeController">
#### [Seção bônus]

### Atribuição: `let`
{: .slide_title .slide}

#### <button class="link" ng-model="block301" ng-click="block301=!block301">Intro</button>

> Quando você cria funções, você pode quere dar nomes a valores para poder
> reutilizá-los ou deixar o seu código mais legível. Dentro de uma função, no entanto,
> você _não deveria_ usar `def`, como você fez fora de uma função. Ao invés disso, você 
> deveria usar uma expressão especial chamada `let`.
{: ng-show="block301" .description}
</section>

<section ng-controller="NarrativeController">
#### Atribuindo nomes a valores: `let`
{: .slide_title .slide}

#### <button class="link" ng-bind-html="details" ng-model="block305" ng-click="block305=!block305"></button>

> Podemos atribuir um nome a um valor usando `let` da mesma forma que fizemos no `def`.
> Quando um nome está atribuído a um valor, esse nome é chamado de *símbolo*.
{: ng-show="block305" .description}

> Referência: [Atribuição let](http://clojurebridgesp.github.io/community-docs/docs/clojure/let/)
{: ng-show="block305" .description}

```clojure
(let [mangas 3
      laranjas 5]
  (+ mangas laranjas))
;=> 8
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
