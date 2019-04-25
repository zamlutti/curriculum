---
layout: default
title: Vetores e Mapas
permalink: /outline/data_structures.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/data_structures.html

{% endcomment %}

<section>
Estruturas de Dados
----------------------------------------
{: .slide-title .chapter}

* Vetores
* Mapas
</section>

<section>
### Grupo de dados - Coleções
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Introdução</button>

> Até agora lidamos com pedaços discretos de dados: um número, uma
> string, um valor. Em programação, no entanto, é mais comum o caso em que temos
> que lidar com grupos de dados.
{: ng-show="block11" .description}

> Clojure tem ótimas facilidades para trabalhar com esses grupos, ou
> *coleções* de dados. Não só nos dá quatro tipos diferentes de coleções
> mas também nos permite acessar de uma maneira uniforme todos esses
> tipos de coleções junto.
{: ng-show="block11" .description}
</section>

<section ng-controller="NarrativeController">
### Vetores
{: .slide_title .slide}

#### Coleção sequencial <button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> Um vetor é uma coleção sequencial de valores. Um vetor pode estar vazio.
> Um vetor pode ter valores de diferentes tipos. Cada valor em um vetor
> é numerado começando em 0, e esse número é chamado de índice. O índice
> é usado para consultar cada valor de dentro do vetor quando estivermos
> procurando algo.
{: ng-show="block21" .description}

#### Estrutura em divisórias <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> Para imaginar um vetor, pense em uma caixa separada em uma quantidade
> de divisórias de mesmo tamanho. Cada uma dessas divisórias tem um número.
> Você pode colocar algum dado dentro de cada divisória e sempre saber onde
> procurar esse dado no número da divisória.
{: ng-show="block22" .description}

> Note que os números começam em zero. Isso pode parecer estranho, mas
> no geral em programação começamos a contar do zero.
{: ng-show="block22" .description}

![Vetor](img/vector.png)

</section>

<section ng-controller="NarrativeController">
#### Sintaxe <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> Vetores são geralmente escritos entre colchetes `[]` com qualquer quantidade
> de valores separados por espaços. Estes são alguns exemplos de vetores: 
{: ng-show="block31" .description}

```clojure
[1 2 3 4 5]
[56.9 60.2 61.8 63.1 54.3 66.4 66.5 68.1 70.2 69.2 63.1 57.1]
[]
```
</section>

<section ng-controller="NarrativeController">
#### Criação <button class="link" ng-bind-html="details" ng-model="block61" ng-click="block61=!block61"></button>

> As duas próximas funções são usadas pra criar novos vetores. A função `vector`
> recebe um número qualquer de itens e os coloca em um vetor novo. `conj` é 
> uma função interessante que você verá sendo usada com todas as estruturas
> de dados. Com vetores, ela recebe um vetor e um item e devolve um novo vetor
> que tem esse item adicionado ao final dos itens do vetor recebido.
> Por que o nome `conj`? `conj` é abreviação de conjoin, que significa juntar
> ou combinar. E é isso que estamos fazendo: Estamos juntando o novo item ao vetor.
{: ng-show="block61" .description}

```clojure
(vector 5 10 15)
;=> [5 10 15]

(conj [5 10] 15)
;=> [5 10 15]
```
</section>

<section ng-controller="NarrativeController">
#### Extração <button class="link" ng-bind-html="details" ng-model="block81" ng-click="block81=!block81"></button>

> Agora veja estas quatro funções. `count` nos dá a quantidade de itens
> que o vetor tem. `nth` nos dá o enézimo item do vetor. Note que começamos
> a contar do 0, então no exemplo chamar `nth` com o número 1 nos dá o que
> chamaríamos de segundo elemento se não estivéssemos programando. `first`
> devolve o primeiro item da coleção. `rest` retorna todos os itens exceto o primeiro.
> Tente não pensar sobre isso e `nth` ao mesmo tempo, pois pode ser confuso.
{: ng-show="block81" .description}

```clojure
(count [5 10 15])
;=> 3
(nth [5 10 15] 1)
;=> 10
(first [5 10 15])
;=> 5
(rest [5 10 15])
;=> (10 15)
```
</section>

<section ng-controller="NarrativeController">
### Mapas

#### pares de chave-valor <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> Mapas são conjuntos de chave e valores associados a elas. Você pode pensar
> nelas como se fossem um dicionário: você procura por coisas usando uma
> palavra (uma palavra-chave/keyword) e consegue ver a sua definição (seu valor).
> Se você já programou em outra linguagem, você pode já ter visto algo parecido 
> com mapas -- talvez chamados de dicionários, hashes ou arrays associativos.
{: ng-show="block101" .description}

![Mapa](img/map.png)
</section>

<section ng-controller="NarrativeController">
#### Sintaxe <button class="link" ng-bind-html="details" ng-model="block102" ng-click="block102=!block102"></button>

> Para escrever mapas alternamos chaves e valores, colocando chaves `{}` em volta de todas elas.
{: ng-show="block102" .description}

> Mapas são útes pois conseguem guardar dados da maneira que normalmente já 
> pensamos sobre eles. Pense no nosso exemplo hipotético, Sally Brown. Um 
> mapa pode guardar o seu nome e sobrenome, seu endereço, sua comida favorita
> ou qualquer outra coisa. É uma forma simples de coletar estes dados e ser fácil
> de procurar depois. O último exemplo é um mapa vazio. É um mapa que está pronto 
> pra guardar alguma coisa, mas ainda não tem nada.
{: ng-show="block102" .description}

```clojure
{:first "Sally" :last "Brown"}
{:a 1 :b "two"}
{}
```
</section>

<section ng-controller="NarrativeController">
#### Criação <button class="link" ng-bind-html="details" ng-model="block104" ng-click="block104=!block104"></button>

> `assoc` e `dissoc` são funções complementares: elas associam e desassociam itens em um mapa. 
> Veja como colocamos o sobrenome "Brown" no mapa com `assoc`, e depois o removemos com `dissoc`.
> `merge` mistura dois mapas para formar um novo mapa com todos os seus elementos juntos.
{: ng-show="block104" .description}

```clojure
(assoc {:first "Sally"} :last "Brown")
;=> {:first "Sally", :last "Brown"}

(dissoc {:first "Sally" :last "Brown"} :last)
;=> {:first "Sally"}

(merge {:first "Sally"} {:last "Brown"})
;=> {:first "Sally", :last "Brown"}
```
</section>

<section ng-controller="NarrativeController">
#### Extração 1 <button class="link" ng-bind-html="details" ng-model="block105" ng-click="block105=!block105"></button>

> `count`, toda coleção tem essa função. Por que você acha que a resposta
> é dois? `count` nos devolve o número de associações.
{: ng-show="block105" .description}

> Como mapas são pares de chave-valor, a chave é usada para pegar o valor
> de um mapa. Um dos jeitos mais usados em Clojure são os exemplos abaixo.
> Podemos usar uma keyword como se fosse uma função para buscar os valores
> dentro do mapa. No último exemplo, passamos a chave `:INEXISTENTE` como 
> último argumento. Isso funciona para quando a chave que procuramos não
> existe no mapa.
{: ng-show="block105" .description}

```clojure
(count {:first "Sally" :last "Brown"})
;=> 2

(get {:first "Sally" :last "Brown"} :first)
;=> "Sally"
(get {:first "Sally"} :last)
;=> nil


(get {:first "Sally"} :last :INEXISTENTE)
;=> :INEXISTENTE
```
</section>

<section ng-controller="NarrativeController">
#### Extração 2 <button class="link" ng-bind-html="details" ng-model="block106" ng-click="block106=!block106"></button>

> Também temos `keys` e `vals`, que são bem simples: retornam as chaves
> e os valores do mapa. A ordem não é garantida, então poderiamos ter
> como resultado `(:first :last)` ou `(:last :first)`
{: ng-show="block106" .description}

```clojure
(keys {:first "Sally" :last "Brown"})
;=> (:first :last)

(vals {:first "Sally" :last "Brown"})
;=> ("Sally" "Brown")
```
</section>

<section ng-controller="NarrativeController">
#### Atualização <button class="link" ng-bind-html="details" ng-model="block110" ng-click="block110=!block110"></button>

> Após a criação, queremos salvar um novo valor associado à chave. 
> A função `assoc` pode ser usada para associar um novo valor a uma chave
> já existente. Também existe uma função útil chamada `update`. Esta 
> função recebe o mapa e a chave com uma função. O valor da chave especificada
> vai ser o primeiro argumento da função passada.
> A função `update-in` funciona como a `update`, mas recebe um vetor de
> chaves para atualizar um caminho dentro de um mapa aninhado.
{: ng-show="block110" .description}

```clojure
(def hello {:count 1 :words "hello"})

(update hello :count inc)
;=> {:count 2, :words "hello"}
(update hello :words str ", world")
;=> {:count 1, :words "hello, world"}


(def mine {:pet {:age 5 :name "able"}})

(update-in mine [:pet :age] - 3)
;=> {:pet {:age 2, :name "able"}}
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
