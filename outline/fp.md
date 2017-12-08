---
layout: default
title: Introduction
permalink: /outline/fp.html
---

{::options parse_block_html="true" /}

{% comment %}

http://clojurebridge.github.io/curriculum/outline/fp.html

{% endcomment %}

<section ng-controller="NarrativeController">
## Principles of functional languages
{: .slide_title .slide}


#### <button class="link" ng-model="block11" ng-click="block11=!block11">Intro</button>

>Rather than updating variables in memory, programs work by function composition.
{: ng-show="block11" .description}

#### Immutability <button class="link" ng-bind-html="details" ng-model="block12" ng-click="block12=!block12"></button> <button class="link" ng-bind-html="details2" ng-model="block12e" ng-click="block12e=!block12e"></button>

>The benefit of immutability is that it is easier to know exactly what's happening in a program since every object that a program references is always the same as when it was originally created. This also makes it easier to incorporate concurrency since there is much less of a need to keep track of simultaneous updates, so much less of a need to lock objects. In fact, one of the main design goals of Clojure was the ease of concurrent programming with minimal locking.
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

#### Side effects & Referential transparency <button class="link" ng-bind-html="details" ng-model="block13" ng-click="block13=!block13"></button> <button class="link" ng-bind-html="details2" ng-model="block13e" ng-click="block13e=!block13e"></button>

> Functions should be as "pure" as possible. This means that functions should:
>- not change state in current running system, like having global variables and functions that changes their values.
>- always evaluates to the same result in any context. With the same input, a function should always return the same output.
{: ng-show="block13" .description}

> ds
``` ruby
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
``` clojure
(ns my.namespace)
(defn double[x]
  (* x 2))
```
{: ng-show="block13e" .description}

#### Functions as first class citizens in the language <button class="link" ng-bind-html="details" ng-model="block14" ng-click="block14=!block14"></button>

> Functions in a functional language are treated as other elements of the language (numbers, strings, etc.), i.e. they can be stored in a variable, passed to other functions, returned from other functions, and even created at run time. This is often refers to as functions being first class citizens in the language.
{: ng-show="block14" .description}

</section>
