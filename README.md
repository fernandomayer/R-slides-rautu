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
  [slides_ioslides.Rmd][].


<!-- links -->

[knitr]: http://yihui.name/knitr/
[rmarkdown]: http://rmarkdown.rstudio.com/
[ioslides]: http://rmarkdown.rstudio.com/ioslides_presentation_format.html
