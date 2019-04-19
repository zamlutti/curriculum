---
layout: default
title: Introdução
permalink: /outline/intro.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridgesp.github.io/curriculum/outline/intro.html

{% endcomment %}

<section>
Introdução à linguagem Clojure
----------------------------------------
{: .slide-title .chapter}

* Por que Clojure?
* Em que o Clojure é bom?
* Como é o Clojure?
    - Comentários
* O que é um REPL?
* REPL em ação
</section>

<section ng-controller="NarrativeController">
## Por que Clojure?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Introdução</button>

> Por que estamos ensinando Clojure?
> Embora não seja uma linguagem muito popular, estamos usando Clojure por causa de três qualidades
> que o tornam uma primeira linguagem ideal para aprender -- ou uma ótima linguagem para se aprender
> além das outras que talvez você já conheça:
{: ng-show="block11" .description}

#### Clojure é _simples_ <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> Clojure é _simples_. O que não quer dizer que não seja poderoso; pois o é. O
> número de conceitos que você precisa conhecer pra programar em Clojure é bem 
> pequeno e são fáceis de compreender. Com Clojure você consegue ser bastante
> produtivo com um conjunto bem pequeno da linguagem, e melhor na medida em que
> você vai aprendendo mais sobre a linguagem
{: ng-show="block12" .description}

#### Clojure é _universal_ <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button>

> Clojure é _universal_. Algumas linguagens tem um foco específico.
> JavaScript, por exemplo, foi tradicionalmente usado apenas em páginas web
> (embora isso tenha mudado um pouco recentemente). Objective-C é usado
> principalmente para aplicativos iOS. Clojure pode ser usado para qualquer
> tipo de aplicação facilmente.
{: ng-show="block13" .description}

#### Clojure é _divertido_ <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> Clojure é _divertido_. Isso é questão de opinião, é claro, mas a
> gente acha que é verdade. Espero que durante esse curso você sinta
> a alegria de ver um programa Clojure ser criado e fazer algo poderoso
> e surpreendente.
{: ng-show="block14" .description}
</section>

<section ng-controller="NarrativeController">
## Em que o Clojure é bom?
{: .slide_title .slide}

#### <button class="link" ng-model="block21" ng-click="block21=!block21">Introdução</button>

> Então, dissemos que Clojure é universal, e é. O que não significa que
> não tenha situações em que ele seja mais útil.
{: ng-show="block21" .description}

#### Processamento de dados<button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> Clojure é conhecido por ser bom em processar dados, pois tem um bom 
> conjunto de estruturas de dados -- isto é, tem várias formas nativas
> de representar dados que são fáceis de usar e poderosas.
{: ng-show="block22" .description}

#### Concorrência <button class="link" ng-bind-html="details" ng-model="block23" ng-click="block23=!block23"></button>

> Clojure é conhecido por sua concorrência.
> As variáveis e estruturas de dados em Clojure são imutáveis por padrão, ou seja, seus conteúdos nunca mudam.
> Toda vez que alguma modificação é necessária, um novo valor é criado. Por exemplo, se vc adiciona um elemento
> em uma lista, uma nova lista é criada com os elementos antigos mais o novo elemento, enquanto a lista antiga 
> continua a mesma. Pode parecer uma abordagem ineficiente, mas por baixo dos panos existe um compartilhamento 
> muito eficiente das partes da lista que não mudaram, o que é invisível para o programador. Vetores em Clojure
> são particularmente eficientes nesse sentido.
{: ng-show="block23" .description}

#### Tudo o mais! <button class="link" ng-bind-html="details" ng-model="block24" ng-click="block24=!block24"></button>

> REST APIs, web apps...
{: ng-show="block24" .description}
</section>

<section ng-controller="NarrativeController">
## Como é o Clojure?
{: .slide_title .slide}

```clojure
(print-str "Hello, World!")
(+ 3 4)
(max 8 17 2)
```

#### Parênteses <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> Note os parênteses. Parêntesis cercam as instruções para o computador no Clojure.
> O parênteses da esquerda é o início da instrução, e o parênteses da direita correspondente
> é o final desta instrução. Em geral códigos em Clojure têm muitos parêntesies aninhados, ou 
> em outras palavras, instruções cercadas aninhadas.
{: ng-show="block31" .description}

#### Funções <button class="link" ng-bind-html="details" ng-model="block32" ng-click="block32=!block32"></button>

> Logo depois dos parêntheses, vemos a _função_.
> Funções fazem todo o trabalho pesado no Clojure.
> `print-str`, `+` e `max` são ambos funções.
> Quando estas funções são executadas, elas devolvem algum tipo de valor.
> Funções em Clojure sempre devolvem um valor.
{: ng-show="block32" .description}

#### Argumentos <button class="link" ng-bind-html="details" ng-model="block33" ng-click="block33=!block33"></button>

> Muitas funções recebem _argumentos_--que são todo o resto que está dentro
> do parênteses ao redor da função, após o seu nome. 
> `print-str` recebe `"Hello, World!"` e devolve o próprio texto.
> `+` recebe `3` e `4`, soma, e devolve `7`.
> `max` recebe vários números e devolve qual é o maior deles.
{: ng-show="block33" .description}
</section>

<section ng-controller="NarrativeController">
### Comentários

<button class="link" ng-bind-html="details" ng-model="block42" ng-click="block42=!block42"></button>

> Em Clojure, comentários podem ser iniciados com um ponto-e-vírgula. Tudo
> após o ponto-e-vírgula até o fim da linha é considerado como comentário
> é ignorado. Apenas um ponto-e-vírgula é o suficiente, mas algumas vezes
> vemos dois pontos-e-vírgulas na mesma linha, dependendo do estilo do escritor.
{: ng-show="block42" .description}

> Referência: [Comentário](http://clojurebridge.github.io/community-docs/docs/clojure/comment/)
{: ng-show="block42" .description}

```clojure
;; funções de exemplo do slide anterior
(print-str "Hello, World!")  ; o tão conhecido hello world
(+ 3 4)                      ; por que não 3 + 4? descobrir depois
```
</section>

<section>
## O que é um REPL?
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Introdução</button>

> "REPL" significa "Read-Eval-Print-Loop", ou "Leia-Execute-Imprima-Repita",
> que ainda não faz tanto sentido sem contexto. Muitas linguagens de programação,
> incluindo Clojure, tem uma maneira de executar código interativamente para que
> você consiga ver o resultado instantaneamente. Em outras palavras, o código é lido,
> executado, e então o resultado é mostrado na tela, e começa novamente -- por isso, um _loop_.
{: ng-show="block51" .description}

**R**ead, **E**val, **P**rint, **L**oop

![Nightcode's repl](img/repl.png)

</section>

<section>
#### EXERCÍCIO 1: Experimente o REPL

1. Abra o seu terminal
2. `lein repl`
3. Digite as funções Clojure abaixo e veja o que acontece

```clojure
(print-str "Hello, World!")
(print-str "Hello, World!" " " "from Clojure")
(+ 3 4)
(- 3 4)
(* 3 4)
```

> Tenha certeza de digitar as linhas <em>exatamente</em> como você as vê acima,
> cuidando para colocar os parênteses nos lugares certos.
</section>

<section>
#### EXERCÍCIO 2: Veja as documentações do Clojure (em inglês)

* No final do painel do REPL, tente procurar pela documentação de uma das funções que você usou
* Você pode usar o comando `(doc nome-da-funcao)` para fazer isso
* Tente `(doc +)` e `(doc max)` no REPL
* Tente outras funções que a gente usou até agora, por exemplo `-`, `*`, ou mesmo `doc`
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Volte para o <a href="javascript:;" onClick="Reveal.slide(1);">primeiro slide</a>,
ou vá para o [índice do currículo](/curriculum/#/1).
</section>
