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

Primeiras gerações de linguagens de programação
-----------------------------------------------

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
era basicamente o que alimentava a memória de instruções das máquinas da época)
era completamente manual. Então, se buscava criar linguagens fáceis de seres
humanos fazerem essa tradução.

Quando, em 1952, Grace Hopper implementa o primeiro _linker_ (na época ele foi
chamado de "compilador", mas pelos conceitos atuais ele se encaixa como um
_linker_), que traduzia palavras em inglês para código de máquina, aos poucos a
necessidade de facilitar a tradução humana vai diminuindo, especialmente depois
da criação de **[Fortran](https://en.wikipedia.org/wiki/Fortran)**, cujo
**rascunho** de sua especificação foi formulado em **1954** e seu primeiro
compilador foi implementado em **1957**. O fato de ser o primeiro compilador
que aplicasse otimizações animou programadores de compiladores da época a
escrever compiladores para Fortran, e assim, com novas ideias e recursos em
novas edições de Fortran, as linguagens de programação foram tomando formas
mais parecidas com as que estamos acostumados hoje, mas isso se falarmos apenas
das imperativas.

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

C, PDP-11 e Ciência da Computação para Compiladores
---------------------------------------------------

A linguagem C surge só em **1972**, com o intuito de criar ferramentas para o
Unix para o PDP-11 (um processador da época) de uma maneira mais fácil, e aqui
que as coisas começam a ficar mais interessantes. As preocupações envolviam
trabalhar na portabilidade do Unix, afinal estamos falando de uma época em que
a recém se podia, aos poucos, **abstrair a máquina alvo** parando de se
importar tanto com Assembly para se ter um programa otimizado, se preocupando
em **tentar reduzir o tempo de compilação**. C conseguia ser simples o
suficiente para se aplicar otimizações e, tendo uma tipagem estática
**fraca¹**, não era exigido muito do compilador para fazer verificações para o
programador quanto ao sistema de tipos.

> _¹: Como há pelo menos 3 definições de "tipagem forte/fraca", deixo claro que
> utilizo "tipagem fraca" no sentido de **coerção** entre tipos, ou seja, C é
> extremamente permissivo com relação a interações entre valores de tipos
> diferentes: em comparações entre `unsigned` e `signed` ocorre uma conversão
> implícita, a operação é permitida e não gera erros de compilação, por
> exemplo._

Poucas preocupações com a qualidade da linguagem, do ponto de vista de
**projeto da linguagem**, tomavam conta de linguagens como C. Outras linguagens
tomavam alguns cuidados extras, seja com foco em didática (como
**[Pascal](https://en.wikipedia.org/wiki/Pascal_(programming_language))
(1970)**) ou com não incluir alguma forma de `goto` (que [era fortemente
criticada por
Dijkstra](https://homepages.cwi.nl/~storm/teaching/reader/Dijkstra68.pdf) -
quem trouxe grandes contribuições para a Ciência da Computação - já em 1968).
No mesmo período em que surge C, porém, temos algumas linguagens que visam
explorar conceitos dentro da área de Computação, em especial no quesito de
sistema de tipos, como **[Smalltalk](https://en.wikipedia.org/wiki/Smalltalk)
(1972)** e **[ML](https://en.wikipedia.org/wiki/ML_(programming_language))
(1973)**, ou em como é realizada a computação, e quem traz uma forte
contribuição nessa discussão é **[Prolog](https://en.wikipedia.org/wiki/Prolog)
(1972)**.

**Smalltalk** era uma descrição completa de "o que deveria ser uma linguagem
orientada a objetos" (da qual Java se distancia **muito** em aspectos bastante
fundamentais - mas isso é assunto para outro artigo). Nesse sentido, já se
pensa mais em dar forma a novos paradigmas, **explorar formas de descrever
programas** abordando conceitos como imutabilidade (que, sim, faz parte de
Orientação a Objetos), encapsulamento (que não é fazer _getters_ e _setters_),
_message-passing_ e polimorfismo.

Enquanto isso, **ML** consegue dar uma cara nova à programação funcional
introduzindo um **sistema de tipos** robusto bastante interessante. Repare no
[método de verificação de tipos em
expressões](https://en.wikipedia.org/wiki/Hindley%E2%80%93Milner_type_system#Type-checking_vs._type-inference):
compiladores fazem uso de conceitos de decidibilidade em provas de teoremas
para validar se os tipos estão corretamente definidos **sem que seja necessário
explicitá-los**. Ou seja, ML traz uma forma inteligente de se introduzir
**inferência de tipos** (não confunda com tipagem dinâmica!).

No lado de Prolog, temos uma forma de descrever computação que não se baseia em
sequências de instruções (como as imperativas) nem em séries de funções em um
sentido matemático puro, mas sim em **descrever programas como pequenos
teoremas a serem validados**.

Perceba: até então, boa parte da preocupação dos projetistas de linguagem era
na criação de ferramentas para automatizar alguma tarefa, criar mais
ferramentas, ou facilitar trabalho manual. Tempos depois, finalmente temos
conceitos teóricos sendo fundamentados em linguagens de programação, criando
uma nova geração de pesquisas e objetivos, ou seja: se enaltece que
compiladores e linguagens são **uma peça fundamental da Ciência da
Computação** enquanto um campo de estudo teórico bastante denso, ao mesmo tempo
que se traz, para uma área antes com foco majoritariamente prático, conceitos
definidos há décadas (computabilidade, decidibilidade, _cálculo-lambda_, ...).
Isso tem **sérios impactos** na qualidade dos programas de hoje em dia - não
estamos falando de qualidade enquanto "um código bonitinho" -, mas já
chegaremos lá.

Pascal e JavaScript: nem tão novas nem tão modernas
---------------------------------------------------

Continuando a linha do tempo, temos **C++ (1980)** estendendo C para dar
suporte a classes; **Eiffel (1985)** trazendo um sistema de testes totalmente
checável em tempo de compilação (baseado na noção de [_Design by
Contract_](https://en.wikipedia.org/wiki/Design_by_contract)); **Erlang
(1986)** trazendo _pattern matching_ e alguns conceitos de programação
funcional. Porém, por mais que comumente se diga que Python e JavaScript são
"linguagens moderninhas" (de maneira pejorativa), essas linguagens surgem logo
na década seguinte: Python em 1991 e JavaScript em 1995. PHP e Java, que nunca
entram nesse conceito de "moderninhas", surgiram em 1995: o mesmo ano de
JavaScript, e 4 anos posterior a Python!

Boa parte da pejoratividade em chamar essas linguagens de moderninhas se baseia
em questões como:

- São linguagens dinamicamente tipadas;
- Não exigem que tipos sejam explicitados;
- São projetadas pensando em executar em interpretadores;
- Carregam um caráter de simplicidade em relação à sintaxe.

Ou seja, se vê flexibilidade e simplicidade como características modernas e
infantis, porém essa visão é baseada em uma desinformação completa, veja:

- Tipagem dinâmica já era presente em **APL** e **Lisp**, dos anos 1950 e 1960;
- Já se tinham interpretadores para essas mesmas duas linguagens;
- Novamente, APL e Lisp não possuiam um mecanismo para se explicitar tipos;
- Um interpretador completo de Lisp pode ser feito em menos [1000 linhas de
  código C](https://github.com/rui314/minilisp), ou seja, já tínhamos
  linguagens bastante simples e minimalistas há quase 40 anos.

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
