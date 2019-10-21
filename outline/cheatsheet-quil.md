# Quil Cheatsheet

## Formas -- (os comandos só funcionam nas funções de desenho!)

```clj
(line x1 y1 x2 y2)
```

Desenha uma linha (uma reta entre dois pontos) na tela. `x1`, `y1`,
`x2`, e `y3` são todos número usados como coordenadas, ou pixels a partir do canto superior esquerdo de sua tela.

```clj
(rect x y largura altura)
```

Desenha um retângulo na tela. `x` e `y` sãp coordenadas. `largura` e
`altura` são quão grande a área é, novamente, em números.
```clj
(ellipse x y largura altura)
```

Desenha uma elipse (oval) na tela.

## Cor

```clj
(color r g b a)
```

Uma cor consiste em quatro valores. Os três primeiros valores (vermelho, verde, azul 
em valores que vão de `0` a `255`) vão gerar uma cor. Forneça um quarto valor para definir a
opacidade. `(color 0 0 255 128)`, por exemplo, é um azul com meia transparência.

```clj
(background color)
```

Define toda a área de coloração para uma cor. Ótimo para apagar a tela a cada
desenho.

```clj
(fill color)
```

Define o preenchimento de formas que são coloridas após a chamada dessa função.

```clj
(stroke color)
```

Define um traço, uma borda ao redor de formas pintadas depois.

```clj
(no-fill)
(no-stroke)
```

Desabilita o preenchimeto e/ou traço de formas que serão desenhadas. Por exemplo:

```clj
(background (color 255 0 0))
(fill (color 0 0 255))
(ellipse 100 100 30 30)
```

## Texto

```clj
(text seu-texto x y)
```

Exibe seu texto na tela em uma coordenada específica.

## Mouse

Essas são funções úteis para recuperar valores do seu mouse. Ótimas se você quer move coisas em sua tela.

```clj
(mouse-x) ;=> número
(mouse-y) ;=> número
(mouse-pressed?) ;=> true/false
```

O que você acha que isso faz?

```clj
(ellipse (mouse-x) (mouse-y) 30 30)
```

## Tempo

```clj
(frame-count) ;=> número
```

O número de frames exibidos a partir do início do programa. Tente enquanto
engloba isso em `(mod num div)` uma função módulo. Pro exemplo:

```clj
(ellipse 100 100 (mod (frame-count) 30) (mod (frame-count) 30))
```

## Mais funções Quil

As funções mencionadas acima são apenas algumas simples para você dar início.
A [documentação API](http://quil.info/api) lista todas as funções de Quil, que são muitas!
