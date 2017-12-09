---
layout: default
title: Introduction
permalink: /outline/intro.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/intro.html

{% endcomment %}

<section>
Introdução a linguagem Clojure
----------------------------------------
{: .slide-title .chapter}

* Why Clojure?
* What is Clojure good at?
* What does Clojure look like?
    - Comments
* What is a REPL?
* REPL in action
</section>

<section ng-controller="NarrativeController">
## Why Clojure?
{: .slide_title .slide}

#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

> So why are we teaching Clojure?
> Although it's not a popular language, we're using Clojure because of three qualities
> it has that make it an ideal first language to learn--or a great
> language to learn in addition to others you might already know:
{: ng-show="block11" .description}

#### Clojure is _simple_ <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button>

> Clojure is _simple_. That's not to say it's not powerful; it is. The
> number of concepts you have to know to program in Clojure is very
> small, however, and easy to grasp. Clojure grows with you as you
> learn it, and you can be very productive with a small subset of the
> language.
{: ng-show="block12" .description}

#### Clojure is _all-purpose_ <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button>

> Clojure is _all-purpose_. Some languages have a specific focus.
> JavaScript, for example, was traditionally used only in web pages
> (although that's changed somewhat). Objective-C is used mainly for
> iPhone apps.
> you can use Clojure for any sort of application easily.
{: ng-show="block13" .description}

#### Clojure is _fun_ <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> Clojure is _fun_. That's a matter of opinion, of course, but we
> think it holds true. I hope that during this course you experience
> the joy of seeing a Clojure program come together and do something
> powerful and surprising.
{: ng-show="block14" .description}
</section>

<section ng-controller="NarrativeController">
## What is Clojure good at?
{: .slide_title .slide}

#### <button class="link" ng-model="block21" ng-click="block21=!block21">Intro</button>

> So, we said Clojure is all-purpose, and it is. That doesn't mean it
> doesn't have strong suits, though.
{: ng-show="block21" .description}

#### Data processing <button class="link" ng-bind-html="details" ng-model="block22" ng-click="block22=!block22"></button>

> Clojure is known for being good at data processing. That's because
> it has a good set of data structures--that is, it has several
> built-in ways to represent data that are easy to use and powerful.
{: ng-show="block22" .description}

#### Concurrency <button class="link" ng-bind-html="details" ng-model="block23" ng-click="block23=!block23"></button>

> Clojure is known for its concurrency.
>Variables and data structures in Clojure are immutable by default, i.e. they never change in place. Every time a modification is needed, a new object is created. For instance, if you add an element to >a list, a new list is created with the new element added, and the old list stays the same.
>This may seem like an inefficient approach, but underneath there is a very efficient sharing of the parts that didn't change, but it's invisible to the programmer. Clojure vectors are in particular efficient in this sense.
{: ng-show="block23" .description}

#### Everything! <button class="link" ng-bind-html="details" ng-model="block24" ng-click="block24=!block24"></button>

> REST APIs, web apps...
{: ng-show="block24" .description}
</section>

<section ng-controller="NarrativeController">
## What does Clojure look like?
{: .slide_title .slide}

```clojure
(print-str "Hello, World!")
(+ 3 4)
(max 8 17 2)
```

#### Parentheses <button class="link" ng-bind-html="details" ng-model="block31" ng-click="block31=!block31"></button>

> Notice the parentheses. Parentheses enclose instructions to the
> computer in Clojure. A left parenthesis
> is the start of the instruction, and a matching right parenthesis is
> the end of enclosing instruction. Normally, Clojure code has a lot
> of nested parentheses, or in other words, nested enclosing instructions.
{: ng-show="block31" .description}

#### Functions <button class="link" ng-bind-html="details" ng-model="block32" ng-click="block32=!block32"></button>

> Next to the parentheses, we see the _function_.
> Functions do all the hard work in Clojure.
> `print-str`, `+` and `max` are all functions.
> When these functions get run, they return some type of value.
> Clojure functions always return a value.
{: ng-show="block32" .description}

#### Arguments <button class="link" ng-bind-html="details" ng-model="block33" ng-click="block33=!block33"></button>

> Many functions take in _arguments_--which are everything else inside
> the enclosing parentheses after the function--.
> `print-str` takes "Hello, World!" and returns a string.
> `+` takes 3 and 4, adds them, and returns 7.
> `max` takes numbers and returns the greatest of them.
{: ng-show="block33" .description}
</section>

<section ng-controller="NarrativeController">
### Comments

<button class="link" ng-bind-html="details" ng-model="block42" ng-click="block42=!block42"></button>

> In Clojure, comments can be started with a semicolon. Everything
> after a semicolon until the end of that line is a comment that gets
> ignored. Only one semicolon is necessary, but
> sometimes you see two semicolons in a row, depending on stylistic
> tastes.
{: ng-show="block42" .description}

> Reference: [Comment](http://clojurebridge.github.io/community-docs/docs/clojure/comment/)
{: ng-show="block42" .description}

```clojure
;; example functions from a previous slide
(print-str "Hello, World!")  ; a well-known hello world
(+ 3 4)                      ; why not 3 + 4? figure out later

```
</section>

<section>
## What is a REPL?
{: .slide_title .slide}

#### <button class="link" ng-model="block51" ng-click="block51=!block51">Intro</button>

> "REPL" stands for "Read-Eval-Print-Loop," which still doesn't make a
> ton of sense without context. Many programming languages, including
> Clojure, have a way to execute code interactively so you get instant
> feedback. In other words, the code is read, then it is evaluated,
> then the result is printed, and you begin again--thus, a loop.
{: ng-show="block51" .description}

**R**ead, **E**val, **P**rint, **L**oop

![Nightcode's repl](img/repl.png)

</section>

<section>
#### EXERCISE 1: Try the REPL

1. Open your terminal
2. `lein repl`
3. Type the Clojure functions below and see what happens

```clojure
(print-str "Hello, World!")
(print-str "Hello, World!" " " "from Clojure")
(+ 3 4)
(- 3 4)
(* 3 4)
```
> Make sure you type the lines <em>exactly</em> as you see them above,
> taking care to put the parentheses in the right locations.
</section>

<section>
#### EXERCISE 2: Look at Clojure docs

* In the bottom REPL pane, try to look up the documentation for a function you have used
* You can use the `(doc function-name)` command to do this
* Try `(doc +)` and `(doc max)` on the REPL
* Try other functions we used so far, for example, `-`, `*`, or `doc`
</section>

{% comment %}

:star2: A link below is for a slide only. Go to [README.md](../README.md)
instead. :star2:

{% endcomment %}

<section>
Return to the <a href="javascript:;" onClick="Reveal.slide(1);">first slide</a>,
or go to the [curriculum outline](/curriculum/#/1).
</section>
