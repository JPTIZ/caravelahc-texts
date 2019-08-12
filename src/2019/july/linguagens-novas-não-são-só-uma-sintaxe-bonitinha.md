Linguagens modernas: só "uma nova sintaxe"?
===========================================

_Por Tiz_

Por algum motivo, em vez de admirar os avanços que se obtém em linguagens
modernas, algumas pessoas na área de tecnologia acabam olhando para a novidade
como uma perda de tempo, uma mera "brincadeira de novato". Programadores Python
e JavaScript chegam a ser chamados pejorativamente de "moderninhos" por algumas
dessas pessoas, que reforçam que suas linguagens de costume são mais
compensadoras, seja pela fama, pela performance, porque "dá pra fazer as mesmas
coisas nela", ou simplesmente por não verem a necessidade na novidade.

Até onde essas pessoas tem razão? Linguagens modernas, sejam as
_garbage-collected_ e/ou com omissão de tipos, são para brincar, sobrando as
linguagens _mainstream_ de tipagem estática com aritmética de ponteiros, bem
consolidadas a partir dos anos 80 e 90, e por aí vai, como representantes de
linguagens para softwares de verdade?

Ou melhor: o que estamos negando aos softwares de verdade ao tratá-las dessa
forma?

Gerações de linguagens de programação
-------------------------------------

Primeiramente, não só pela história de linguagens de programação é **longa** e
bem complexa, mas também pelo fato de que outros tipos de linguagem não são
relevantes para este tópico, quando falarmos "linguagens de programação"
**estaremos nos referindo apenas às de alto-nível**.

Na década de 1940 e início da de 1950 tínhamos alguns protótipos de linguagens,
como **[Plankalkül](https://en.wikipedia.org/wiki/Plankalk%C3%BCl) (1948)**
(que só foi efetivamente implementada em 1998) e **[Short
Code](https://en.wikipedia.org/wiki/Short_Code_(computer_language)) (1952)**.
Como na época não tínhamos compiladores, todo o processo de traduzir o código
em alto-nível para binário/hexadecimal e repassar para um cartão perfurado (que
era basicamente a memória de instruções das máquinas da época) era
completamente manual. Então, essas linguagens buscavam facilitar essa tradução
para seres humanos.

Quando, em 1952, Grace Hopper implementou o primeiro _linker_ (na época ele foi
chamado de "compilador", mas pelos conceitos atuais ele se encaixa como um
_linker_), que traduzia palavras em inglês para código de máquina, aos poucos a
necessidade de facilitar a tradução humana vai diminuindo, especialmente depois
da criação de **[Fortran](https://en.wikipedia.org/wiki/Fortran)**, cujo
**rascunho** de sua especificação foi formulado em **1954** e seu primeiro
compilador foi implementado em **1957** sendo o primeiro a realizar
otimizações. Isso animou programadores de compiladores da época a escrever
compiladores para Fortran, e assim, com novas ideias e recursos em novas
edições de Fortran, as linguagens de programação foram tomando formas mais
parecidas com as que estamos acostumados hoje, mas isso se falarmos apenas das
imperativas.

Ainda na década de 1950, temos o surgimento das primeiras noções de linguagens
funcionais, como
**[IPL](https://en.wikipedia.org/wiki/Information_Processing_Language)
(1956)**, que introduz conceitos como manipulação de listas e funções de
primeira-ordem (a grosso modo, tratar funções da mesma forma que você trata
dados do ponto de vista de o que a linguagem permite fazer), e
**[Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language)) (1958)**
que, apesar de tudo, [não é
funcional](https://letoverlambda.com/index.cl/guest/chap5.html), mas algumas
características dela tendem a se aproximar desse paradigma. Em **1966** temos
**[APL](https://en.wikipedia.org/wiki/APL_(programming_language))** (de "A
Programming Language", fazendo um trocadilho com "Uma linguagem de
programação"), que começou como simples notações matemáticas para manipulação
de _arrays_.

A linguagem C surge só em 1974,

Old
---

. A primeira
especificação de Fortran (FORTRAN I) era quase literalmente definir equações, a
exemplo de que aquela mesma equação acima era seria simplesmente `Y = A * X * X
+ B * X + C`.

### 2ª Geração: Linguagens para algoritmos

- Grace Hopper, compiladores e automatização;
- Código para seres humanos;
- Abstração da máquina alvo muito maior.

Ideas
-----

Tínhamos problemas, nos encaixávamos neles, mas agora não os temos mais, então
**let's move on**.

Quais são as linguagens modernas?
---------------------------------

Mas por mais que geralmente "moderninhos" seja direcionado a programadores
Python, JavaScript e Ruby (possivelmente por serem mais conhecidas), elas já
são de uma geração passada de linguagens (e não digo isso de maneira
pejorativa). Não significa, de maneira alguma, que estão defasadas, mortas e
muito menos inutilizáveis, mas apenas que o conjunto de preocupações,
características de implementação e funcionamento não são mais os de hoje em
dia. Linguagens crescem, nós a utilizamos, identificamos seus problemas e os
corrigimos ao longo do tempo, seja em atualizações da linguagem, seja em novas
linguagens aproveitando novas ideias e focos.
