## Estrutura de dados - Vetor

### Criando um vetor

```clj
(vector 5 10 15)
[1 2 3 4 5]
[56.9 60.2 61.8 63.1 54.3 66.4 66.5 68.1 70.2 69.2 63.1 57.1]
[]
```

#### Funções para vetores

```clj
(vector? [5 10 15])
;=> true

(vector 5 10 15)
;=> [5 10 15]

(conj [5 10] 15)
;=> [5 10 15]

(count [5 10 15])
;=> 3

(nth [5 10 15] 1)
;=> 10

(first [5 10 15])
;=> 5
```

## Estrutura de Dados 2 - Keyword, Mapas

#### Criando um mapa

```clj
{:first "Sally" :last "Brown"}
{:a 1 :b "two"}
{}
```


#### Funções para Mapas

```clj
; determina se o valor é um mapa
(map? {:first "Sally" :last "Brown"})
;=> true

; recupera o valor ao usar a keyword :first
(get {:first "Sally" :last "Brown"} :first)
;=> "Sally"

; recupera o valor ao usar a keyword :first e retorna :MISSse a chave não existe no mapa
(get {:first "Sally"} :last :MISS)
;=> :MISS

; adiciona uma chave/valor ao mapa
(assoc {:first "Sally"} :last "Brown")
;=> {:first "Sally", :last "Brown"}

; remove (desassocia) a chave/valor de :last
(dissoc {:first "Sally" :last "Brown"} :last)
;=> {:first "Sally"}

; faz o merge de dois mapas
(merge {:first "Sally"} {:last "Brown"})
;=> {:first "Sally", :last "Brown"}

; recupera a quantidade de pares chave/valor presentes no mapa
(count {:first "Sally" :last "Brown"})
;=> 2

; recupera todas as chaves presentes no mapa
(keys {:first "Sally" :last "Brown"})
;=> (:first :last)

; recupera todos os valores presentes no mapa
(vals {:first "Sally" :last "Brown"})
;=> ("Sally" "Brown")
```

## Definindo Funções

```clj
(defn nome-da-funcao
  "descrição da função, opcional"
  [param1 param2]
  (corpo-da-funcao))
```

* Funções que retornam true ou false--chamados predicados--normalmente terminam em `?`
* map e reduce - Funções que recebem outras funções

## Map e Reduce

```clj
; aplica a função a todos os elementos presentes em uma coleção
(map inc [1 2 3 4])
;=> (2 3 4 5)
; Semelhante a [(inc 1) (inc 2) (inc 3) (inc 4)]
```
**`map`** recebe uma função e uma coleção, então aplica a função a cada elemento presente na coleção respeitando a ordem. Isso retorna uma nova coleção.

```clj
; faz um reduce (transforma, converte, simplifica) de uma coleção para um valor usando uma função
(reduce + [1 3 5 7])
;=> 16
; Semelhante a (+ 1 3) ;=> 4
;              (+ 4 5) ;=> 9
;              (+ 9 7) ;=> 16
```

**`reduce`** recebe uma função e uma coleção. Primeiro, a função é aplicada ao primeiro e segundo elemento juntos, depois a função é aplicada ao *resultado* da aplicação anterior com o terceiro elemento. Os resultados vão sendo utilizados até chegar ao último valor da coleção.


## Controle de Fluxo

```clj
(if expressao-condicional
  expressao-para-usar-quando-for-true
  expressao-para-usar-quando-for-false)
```

## Lógica booleana com and, or e not

| x     | y     | (and x y) | (or x y) | (not x) | (not y) |
| ----- | ----- | --------- | -------- | ------- | ------- |
| false | false | false | false | true  | true  |
| true  | false | false | true  | false | true  |
| true  | true  | true  | true  | false | false |
| false | true  | false | true  | true  | false |

## let 
Atribuir nomes a valores dentro de funções

```clj
(let [primeiro-nome (:primeiro-nome usuario)            ; atribui a `primeiro-nome`
      mensagem (str "Olá, " primeiro-nome "!")]         ; atribui a `mensagem`
  (println mensagem))                                   ; faz algo com `mensagem`
```


