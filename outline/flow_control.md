---
layout: default
title: Controle de fluxo
permalink: /outline/flow_control.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/flow_control.html

{% endcomment %}

<section>
Controle de fluxo
-------------------------
{: .slide-title .chapter}

* `if`
* `cond`
* Lógica booleana
</section>


<section ng-controller="NarrativeController">
### `if`
{: .slide_title .slide}

<button class="link" ng-bind-html="details1" ng-model="block21"
ng-click="block21=!block21"></button>
<button class="link" ng-bind-html="details2" ng-model="block22" ng-click="block22=!block22"></button>

> Em Clojure, a ferramenta mais básica que temos para controle de fluxo é o operador `if`.
> Veja este exemplo de como você poderia escrever um código no cenário de validação de dados.
{: ng-show="block21" .description}

> Um exemplo. Se somarmos 40 a `y` e ele ainda for menor que 150, então devolva `(+ y 40)`;
> caso contrário, devolva `-150`. (No aplicativo da tartaruga a tela tem a parte superior 150 em y e 
> a inferior em -150 em y.)
{: ng-show="block22" .description}

> Referência: [Condicional `if`](http://clojurebridgesp.github.io/community-docs/docs/clojure/if/)
{: ng-show="block22" .description}

```clojure
(if (< (+ y 40) 150)
  (+ y 40)
  -150))
```
</section>

<section ng-controller="NarrativeController">
#### Forma geral do operador `if`

```clojure
(if expressao-condicional
  expressao-para-avaliar-quando-verdadeiro
  expressao-para-avaliar-quando-falso)
```
</section>

<section ng-controller="NarrativeController">
#### exemplos de `if`

```clojure
(if (> 3 1)
  "3 é maior que 1"
  "3 não é maior que 1")
;=> "3 é maior que 1"

(if (> 1 3)
  "1 é maior que 3"
  "1 não é maior que 3")
  ;=> "1 não é maior que 3"
```
</section>

<section ng-controller="NarrativeController">
#### Veracidade <button class="link" ng-bind-html="details" ng-model="block51" ng-click="block51=!block51"></button>

> Quando testamos a veracidade de uma expressão, o Clojure considera que valores
> `nil` e `false` são falsos e todo o resto é verdadeiro.
> Estes são alguns exemplos: 
{: ng-show="block51" .description}

> Referência: [Veracidade](http://clojurebridge.github.io/community-docs/docs/clojure/truthiness/)
{: ng-show="block51" .description}


```clojure
(if "tudo que não for false e nil é considerado verdadeiro"
  "Uma string é considerada verdadeira"
  "Uma string não é considerada verdadeira")
;=> "Uma string é considerada verdadeira"

(if nil
  "nil é considerado verdadeiro"
  "nil não é considerado verdadeiro")
;=> "nil não é considerado verdadeiro"

(if (get {:a 1} :b)
  "expressões que valem nil são consideradas verdadeiras"
  "expressões que valem nil não são consideradas verdadeiras")
;=> "expressões que valem nil não são consideradas verdadeiras"
```
</section>

<section ng-controller="NarrativeController">
### `cond`
{: .slide_title .slide}

<button class="link" ng-bind-html="details1" ng-model="block61" ng-click="block61=!block61"></button>
<button class="link" ng-bind-html="details2" ng-model="block62" ng-click="block62=!block62"></button>

> O operador `if` aceita apenas um predicado. Quando queremos usar múltiplos predicados
> `if` não é uma boa opção. Teríamos que escrever vários `if`s, um dentro do outro, para
> conseguir isso. Para decidirmos entre múltiplas situações, o operador `cond` funciona melhor.
{: ng-show="block61" .description}

> Por exemplo, se somarmos 40 a y e passar de 150, avalie a primeira expressão,
> que no caso devolve -150. Se somarmos 40 a y e for menos de -150, avalie a segunda
> expressão, que no caso devolve 150. Se ambos os predicados forem falsos, avalie a
> expressão do `:else`. Nesse caso, retorne y mais 40. Se usarmos esta função na app
> da tartaruga, podemos manter a tartaruga sempre entre a parte de cima e a de baixo da tela.
{: ng-show="block62" .description}

> Referência: [Condicional `cond`](http://clojurebridge.github.io/community-docs/docs/clojure/cond/)
{: ng-show="block62" .description}

```clojure
(cond
  (> (+ y 40) 150) -150
  (< (+ y 40) -150) 150
  :else (+ y 40)))
```
</section>

<section ng-controller="NarrativeController">
#### Forma geral do operador `cond`

```clojure
(cond
  predicado1 expressao-para-avaliar-se-o-predicado1-for-verdadeiro
  predicate2 expressao-para-avaliar-se-o-predicado2-for-verdadeiro
  ...
  :else expressao-para-avaliar-se-nenhum-dos-predicados-anteriores-forem-verdadeiros)
```
</section>

<section ng-controller="NarrativeController">
### Lógica booleana com `and`, `or` e `not`
{: .slide_title .slide}

#### <button class="link" ng-model="block81" ng-click="block81=!block81">Introdução</button>

> `if`s não são limitados a testar apenas uma coisa. Você pode testar múltiplas
> condições usando lógica booleana. _Lógica booleana_ s
> `if` statements are not limited to testing only one thing. You can
> test multiple conditions using boolean logic. _Boolean logic_ é o que chamamos de
> combinar e mudar o resultado de predicados usando `and` (e), `or` (ou) e `not` (não).
> to combining and changing the results of predicates using `and`,
> `or`, and `not`.
{: ng-show="block81" .description}

> Se você nunca viu esse conceito em programação, lembre-se que é bem parecido
> com o nosso senso comum do jeito que você olha para as coisas normalmente.
> Seria isso _e_ aquilo verdade? Só se os dois forem verdade. Seria isso _ou_ aquilo
> verdade? Sim, se um dos dois for verdade. A diferença pro _ou_ do português é que
> se os dois forem verdade, também consideramos a expressão toda como verdade. 
> Isto _não_ é verdade? Sim, se for falso.
{: ng-show="block81" .description}
</section>

<section ng-controller="NarrativeController">
#### Combinando `and`, `or`, e `not` <button class="link" ng-bind-html="details" ng-model="block101" ng-click="block101=!block101"></button>

> `and`, `or`, e `not` podem ser combinados. O que pode ficar um pouco difícil de ler.
> Eis um exemplo:
{: ng-show="block101" .description}

```clojure
(defn ano-bissexto?
  "A cada quatro anos, exceto em anos divisíveis por 100, mas sim se for divisível por 400."
  [ano]
  (and (zero? (mod ano 4))
       (or (zero? (mod ano 400))
           (not (zero? (mod ano 100))))))
```
</section>

<section ng-controller="NarrativeController">
#### [Bônus] `cond`, `and`, `or`, e `not` combinados <button class="link" ng-bind-html="details" ng-model="block110" ng-click="block110=!block110"></button>

> Aprendemos sobre `cond`, `and `, `or` e `not`. Vamos pensar em que funções podemos escrever
> combinando eles.
> Vamos ao exemplo:
{: ng-show="block110" .description}

```clojure
(defn verdadeiro-ou-falso?
  "Dada uma operacao, devolve true ou false"
  [operacao]
  (let [x true
        y false]
    (cond
      (= operacao :and) (and x y)
      :else false)))

(defn correto?
  "Dados uma operacao e uma resposta, devolve um mensagem se a resposta está certa ou não"
  [operacao resposta]
  (if (= resposta (verdadeiro-ou-falso? operacao))
      "Você venceu!"
      "Você perdeu ='("))
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
