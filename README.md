# R-slides-rautu

Diferentes formas de criar slides com R através do knitr e rmarkdown.

## Introdução

O [knitr][] é um pacote do R capaz de gerar relatórios dinâmicos,
misturando texto e códigos do R. A parte textual geralmente é escrita em
uma linguagem de marcação, como LaTeX ou Markdown. O pacote
[rmarkdown][] possibilita escrever documentos usando a facilidade da
linguagem Markdown para gerar relatórios dinâmicos em HTML ou PDF.

Além da possibilidade de criar relatórios mais longos, o rmarkdown
também tem a capacidade de gerar **slides** dinâmicos, principalmente em
HTML, o que possui certas vantagens sobre o uso do PDF. Algumas destas
vantagens são que os slides podem ser acessados pelo próprio navegador
web do usuário, e o conteúdo dos slides pode conter gráficos interativos
(através da funcionalidade de outros pacotes).

## Tipos de slides

O rmarkdown possui duas formas de gerar slides em HTML:

* [ioslides][]: uma forma simples e mais flexível de gerar slides em
  HTML. Um template com uma aplicação desta classe está em
  [slides_ioslides.Rmd](./slides_ioslides.Rmd).
* [slidy][]: uma forma um pouco mais simples de fazer slides em HTML. Um
  template com uma aplicação desta classe está em
  [slides_slidy.Rmd](./slides_slidy.Rmd).

O rmarkdowm também é capaz de gerar slides em PDF com:

* [beamer][]: a forma tradicional de fazer em slides em LaTeX torna-se
  facilitada com o uso da linguagem rmarkdown. Um template com uma
  aplicação desta classe está em
  [slides_beamer.Rmd](./slides_beamer.Rmd).
* [tufte][]: esta classe segue o padrão se slides utilizada pelo famoso
  [Edward Tufte][] (autor do livro *The Visual Display of Quantitative
  Information*, entre outros), e segue um padrão mais tradicional (os
  slides são em tamanho carta). Um template com uma aplicação desta
  classe está em [slides_tufte.Rmd](./slides_tufte.Rmd).

## Uso

Instalar a versão mais nova do pacote rmarkdown:

```r
library(devtools)
install_github("rstudio/rmarkdown")
```

Escreva o documento usando a linguagem Markdown em um arquivo com
extensão `.Rmd`. No cabeçalho YAML de cada documento existe a
especificação de `output`, que irá determinar o formato final do
arquivo.

Use `#` e `##` para criar seções dentro dos slides, e uma linha (`----`)
para separar o conteúdo de cada slide.

Para renderizar (transformar) o arquivo `Rmd` no seu formato final, use
a função `render()`:

```{r}
library(rmarkdow)
render("nome_do_arquivo.Rmd")
```

Para as classes de slides em HTML, a função `render()` irá converter o
conteúdo de `Rmd` para `md` através do knitr, e posteriormente o
[pandoc][][^1] será chamado para converter de `md` para HTML.

Para as classes em PDF, a `render()` irá converter o conteúdo de `Rmd`
para `tex` através do knitr, e o pandoc irá converter de `tex` para
`pdf`.

## Equações matemáticas e Mathjax

Para os slides em PDF, que serão convertidos para LaTeX, as equações
matemáticas podem ser inseridas usando a linguage TeX padrão para
renderizar as equações.

As equações nos slides HTML também pode ser escritas usando a linguagem
TeX. As equações serão então renderizadas no navegador pelo
[MathJax][]. Esta renderização é feita on-line, ou seja, é necessário
estar sempre conectado para que as equações apareçam corretamente. Em
muitos lugares a conexão não é possível, mas podemos contornar esse
problema se tivermos uma instalação local do MathJax.

A maneira mais fácil de fazer isso é clonando o MathJax diretamente do
GitHub

```sh
git clone git@github.com:mathjax/MathJax.git
```

Agora, basta "linkar" a instalação do MathJax local com os slides que
está preparando. Isto pode ser feito no cabeçalho YAML do documento, por
exemplo:

```
---
title: "Teste de slides em rmarkdown"
author: Fernando Mayer
date: Julho, 2015
output:
  ioslides_presentation:
    mathjax: "/local/clone/MathJax/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
    self_contained: true
---
```

*****

Repositório original:
http://git.leg.ufpr.br/fernandomayer/R-slides-rautu

Repositório espelho:
https://github.com/fernandomayer/R-slides-rautu

<!-- links -->

[knitr]: http://yihui.name/knitr/
[rmarkdown]: http://rmarkdown.rstudio.com/
[ioslides]: http://rmarkdown.rstudio.com/ioslides_presentation_format.html
[slidy]: http://rmarkdown.rstudio.com/slidy_presentation_format.html
[beamer]: http://rmarkdown.rstudio.com/beamer_presentation_format.html
[tufte]: http://rmarkdown.rstudio.com/tufte_handout_format.html
[Edward Tufte]: http://www.edwardtufte.com/tufte/
[pandoc]: http://pandoc.org/
[MathJax]: https://www.mathjax.org/

[^1]: Por isso é necessário ter o pandoc instaldo no sistema.
