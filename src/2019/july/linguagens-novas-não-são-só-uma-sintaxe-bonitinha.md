Linguagens novas não são só "uma sintaxe bonitinha"
===================================================

_Por Tiz_

Por algum motivo, em vez de admirar os avanços que se obtém em linguagens
modernas, algumas pessoas na área de tecnologia acabam olhando para a novidade
como uma perda de tempo, uma mera "brincadeira de novato". Programadores Python
e JavaScript chegam a ser chamados pejorativamente de "moderninhos" por algumas
dessas pessoas, que reforçam que suas linguagens de costume são mais
compensadoras, seja pela fama, pela performance, ou porque "dá pra fazer as
mesmas coisas nela", em um olhar de "coisa de adulto".

Até onde essas pessoas tem razão? Linguagens modernas, sejam as
_garbage-collected_, sejam as com omissão de tipos, são para brincar, sobrando
as linguagens _mainstream_ de tipagem estática, com aritmética de ponteiros,
bem consolidadas a partir dos anos 80 e 90, e por aí vai, como representantes
de linguagens para softwares de verdade?

Ou melhor: o que estamos negando aos softwares de verdade ao tratá-las dessa
forma?

Gerações de inguagens de programação
------------------------------------

Primeiramente, não só pela história de linguagnes de programação é **longa** e
bem complexa, mas também pelo fato de que outros tipos de linguagem não são
relevantes para este tópico, quando falarmos "linguagens de programação"
**estaremos nos referindo apenas às linguagens de alto-nível**.

Vejamos então quais eram as preocupações dos projetistas de linguagens de
programação ao longo do tempo.

### Primeira Geração de Linguagens

Boa parte das linguagens de programação da década de 1940 eram apenas
protótipos teóricos, a preocupação era muito mais explorar modelos de descrever
computações que fossem fáceis de um humano transformar em código de máquina.
**[Plankalkül](https://en.wikipedia.org/wiki/Plankalk%C3%BCl) (1948)**, por
exemplo, só foi ser verdadeiramente implementada em 1998 (apesar de que isso é
mais por não terem utilizado a máquina para qual a linguagem havia sido
pensada: a [Z3](https://en.wikipedia.org/wiki/Z3_(computer))). Veja, se
quiséssemos descrever:

  $$y = ax^{2} + bx + c$$

Em Plankalkül, nosso programa seria:

```plankalkul
P1 func (V0[:32.0],V1[:32.0],V2[:32.0],V3[:32.0]) => R0[:32.0]
    V0[:32.0] * V1[:32.0] * V1[:32.0] + V2[:32.0] * V1[:32.0] + V3[:32.0] => R0[:32.0]
```

Apesar de ser uma linguagem de alto-nível, a representação ainda lida muito com
número de bits das variáveis (`:32`), a sintaxe não era muito complexa (se você
entender o código acima, você entendeu praticamente a linguagem toda). Ao longo
da década de 1950 outras linguagens surgiram, como **[Short
Code](https://en.wikipedia.org/wiki/Short_Code_(computer_language)) (1952)**,
**[GEORGE](https://en.wikipedia.org/wiki/GEORGE_(programming_language))
(1957)** e então a tão conhecida
**[Fortran](https://en.wikipedia.org/wiki/Fortran) (1957)**. A primeira
especificação de Fortran (FORTRAN I) era quase literalmente definir equações, a
exemplo de que aquela mesma equação acima era seria simplesmente `Y = A * X * X
+ B * X + C`.


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
