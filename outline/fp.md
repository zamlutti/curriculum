---
layout: default
title: Introdução a Programação Funcional
permalink: /outline/fp.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/fp.html

{% endcomment %}

<section ng-controller="NarrativeController">
## Princípios de linguagens funcionais
{: .slide_title .slide}


#### <button class="link" ng-model="block11" ng-click="block11=!block11">Introdução</button>

>Ao invés de atualizar variáveis em memória, os programas usam composição de funções.
{: ng-show="block11" .description}

#### Imutabilidade <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button> <button class="link" ng-bind-html="details2" ng-model="block12e" ng-click="block12e=!block12e"></button>

>O Benefício da imutabilidade é saber mais facilmente o que está acontecendo no programa, já que cada valor que o programa referencia é sempre o mesmo de quando ele foi originalmente criado. Também torna mais fácil adicionar concorrência já que há bem menos necessidade de gerenciar atualizações simultâneas, e bem menos necessidade de usar travas (locks) nos valores. De fato, um dos principais objetivos do design do Clojure é a facilitação de programação concorrente com o mínimo de locks.

{: ng-show="block12" .description}

>
- Ruby
```ruby
def oo_func(str)
  str.upcase!
  puts str
end
```
- Clojure
```clojure
(def fp-func(str)
  (let [str2 (upper-case str)]
    (print str2)))
```
{: ng-show="block12e" .description}

#### Efeitos colaterais e transparência referencial <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button> <button class="link" ng-bind-html="details2" ng-model="block13e" ng-click="block13e=!block13e"></button>

> Funções deveriam ser o mais "puras" possível. O que significa:
>- não deveriam mudar o estado atual do sistema, como ter variáveis globais e funções que mudam os seus valores.
>- sempre retornam o mesmo resultado independente do contexto. Com as mesmas entradas a função sempre deveria retornar a mesma saída.
{: ng-show="block13" .description}

>
```ruby
def MyClass
  attr_writer :a
  def initialize(x)
    a = x
  end
  def double
    a = a*2
  end
end
```
```clojure
(ns my.namespace)
(defn double[x]
  (* x 2))
```
{: ng-show="block13e" .description}

#### Funções como cidadãs de primeira classe na linguagem<button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> Funções numa linguagem funcional são tratadas como qualquer outro elemento da linguagem (números, strings, etc), ou seja, podem ser guardadas numa variável, passadas para outras funções, retornadas por outras funções, ou ainda serem criadas em tempo de execução. Neste caso dizemos que as funções são cidadãs de primeira classe na linguagem.
{: ng-show="block14" .description}

</section>
<section>
Voltar ao <a href="javascript:;" onClick="Reveal.slide(1);">primeiro slide</a>,
ou ir para o [índice do currículo](/curriculum/#/1).
</section>
