---
layout: default
title: Sequências
permalink: /outline/sequences.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/sequences.html

{% endcomment %}

<section>
[BONUS]

Sequências
-------------------------
{: .slide-title .chapter}

* O que são sequências
* Funções para sequências
    * `doseq`
    * `dotimes`
</section>

<section ng-controller="NarrativeController">
### O que são sequências?
{: .slide_title .slide}

#### Estruturas de dados do Clojure <button class="link" ng-bind-html="details" ng-model="block11" ng-click="block11=!block11"></button>

> Em Clojure podemos dizer que qualquer estrutura de dados é uma sequência.
> Até agora aprendemos `vector` e `map`, que são ambos sequências.
> String também é uma sequência. Quando algo é **sequenciável**, é uma sequência
{: ng-show="block11" .description}

#### `first` para o primeiro item, ou não <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> Se algo é **sequenciável**, a função `first` retorna o primeiro item da sequência.
> Isso é um bom teste pra saber se algo é ou não é uma sequência.
{: ng-show="block12" .description}
</section>

<section ng-controller="NarrativeController">
#### Resultados de `first`

```clojure

(range 2 8)
;=> (2 3 4 5 6 7)

(first (range 2 8))
;=> 2

(first "Hello, World!")  ; string
;=> \H                   ; a primeira letra

(first :trinity)         ; keyword não é sequenciável
;=> IllegalArgumentException Don't know how to create ISeq from:
;=> clojure.lang.Keyword  clojure.lang.RT.seqFrom (RT.java:528)
```
</section>

<section ng-controller="NarrativeController">
### Funções para sequências
<button class="link" ng-bind-html="details" ng-model="block21" ng-click="block21=!block21"></button>

> Clojure é muito bom para *iterar* numa sequência.
> Existem várias funções que interagem com sequências.
> Por exemplo, `doseq`, `dotimes`, `for`, `loop`, `doall`, ou `dorun`.
>
> Já vimos as funções `map` e `reduce` em "Funções que recebem outras funções".
> Estas também são funções para sequências
{: ng-show="block21" .description}
</section>

<section ng-controller="NarrativeController">
#### `doseq`

<button class="link" ng-bind-html="details1" ng-model="block31" ng-click="block31=!block31"></button>
<button class="link" ng-bind-html="details2" ng-model="block32" ng-click="block32=!block32"></button>

> O `doseq` (pra **rodar uma sequencia**) é uma das funções bastante usadas para sequências, e funciona de
> forma bem similar à função `map`. Esta função repetidamente avalia o conteúdo
> passado para cada elemento da sequência.
{: ng-show="block31" .description}

> A função `doseq` recebe *bindings* (atribuições) como argumentos.
> Os argumentos podem ser um vetor estranho: `[nome-da-variavel sequencia]`.
> Onde cada elemento da sequência é percorrido e atribuído a `nome-da-variavel`,
> um por um, a cada vez que o conteúdo do `doseq` é executado.
{: ng-show="block32" .description}

```clojure
;; exemplo do doseq
(doseq [item items] (my-function item))
```
</section>

<section ng-controller="NarrativeController">
#### `dotimes`

<button class="link" ng-bind-html="details1" ng-model="block41" ng-click="block41=!block41"></button>
<button class="link" ng-bind-html="details2" ng-model="block42" ng-click="block42=!block42"></button>

> O `dotimes` (para **rodar um número de vezes**) é outra função
> bastante usada pra sequências. Assim como `doseq`, a função repetidamente
> avalia o seu conteúdo. A diferença é a atribuição feita no argumento. 
> `dotimes` recebe: `[nome-da-variavel numero-inteiro-de-vezes]`.
{: ng-show="block41" .description}

> A função `dotimes` é o que tem de mais parecido com os *for-loop*s (laços for) de
> outras linguagens de programação. Essa função nos permite acessar uma sequência por índice
> em combinação com a função `nth`.
{: ng-show="block42" .description}

```clojure
;; supondo que exitem várias tartarugas
(def nomes ["a" "b"])
(dotimes [n (count nomes)] (prn n))
```
</section>

{% comment %}

:star2: Um link abaixo é apenas pra slides. Vá para o [README.md](../README.md)
ao invés. :star2:

{% endcomment %}

<section>
Voltar para o <a href="javascript:;" onClick="Reveal.slide(1);">primeiro slide</a>,
ou ir para o [índice do currículo](/curriculum/#/1).
</section>
