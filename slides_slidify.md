---
title       : Teste de slides em rmarkdown
subtitle    : Um teste
author      : Fernando Mayer
job         : 
framework   : dzslides        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax]            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

# Teste de slides em rmarkdown (**slidify**)

## Isto é um header h2

Uma lista com hash:

- Item 1
- Item 2

## Outro header h2 no mesmo slide

E um alista com asterisco

* Item 1
* Item 2

----

# Isto é um header h1

## Um header h2 | Com um sub-header

- Item 1
    - Sub-item 1
    - Sub-item 2
- Item 2

----

## Figura (h2)

![Gitlab](gitlab.png)

----

## Um código em R

Gerando valores de uma VA $X$ de uma distribuição normal $X \sim
\text{N}(0,1)$.


```r
(x <- rnorm(100))
```

```
##   [1] -0.17627861 -0.03071979 -0.22628514 -1.39222455  1.57494646
##   [6] -1.05469202 -1.64113981  0.27945946 -0.64860032 -0.94621276
##  [11]  0.53914927 -2.86386143  0.43324841  1.06899160  0.20722299
##  [16]  1.23266054  0.26918865 -0.92911124  0.45574984  0.06625766
##  [21]  1.06477220 -0.03435858  0.45986445  0.32255745  1.07150103
##  [26]  0.04833050  3.04351802 -0.30935986  0.13577933  0.40210659
##  [31] -0.55814212  0.45430173 -1.46154674  1.06489679  1.29610869
##  [36] -0.44350006 -1.98112777  1.04760682  0.15371287 -2.60160150
##  [41] -0.50286729  1.55548812  1.28507517  1.39453459  1.43658648
##  [46] -0.17639194 -0.32487173 -0.59604901  1.10732125 -0.29545997
##  [51] -0.44366452  2.87244012  0.15495026 -1.38500393  0.18334374
##  [56] -0.17904161  0.18566694 -1.91815155  0.40223341  0.37013412
##  [61] -0.87659075 -1.43540438 -0.13348993  0.71377301 -0.56677774
##  [66]  1.43093826 -0.82319720  0.80427319 -2.05944045  0.35687107
##  [71] -0.87360712 -0.32139970  0.80537738 -0.06722616 -0.69023654
##  [76]  0.84955329 -0.33974573 -0.03986149  1.01202636 -0.85992413
##  [81]  0.67879471 -1.27034017 -0.89537301 -0.60206448  1.48992378
##  [86] -0.08938471  1.11058106 -0.81157337  0.14426098  0.35674251
##  [91] -0.11486118  1.61931657  1.75962254  0.40545911  0.68260447
##  [96] -1.03613715  0.44797204  1.04466169 -1.69627544 -1.15815167
```

----

## Uma figura com R

Histograma do objeto `x`. A média de `x` é 0.0347113.


```r
hist(x)
```

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png) 

----

### A distribuição normal (h3)

$$ f(x) = \frac{1}{\sqrt{2\pi\sigma^2}} \cdot \exp
\left[-\frac{1}{2}\frac{(x - \mu)^2}{\sigma^2} \right] $$

#### A distribuição de Poisson (h4)

$$ P[X = x] = \frac{e^{-\lambda} \lambda^x}{x!} $$
