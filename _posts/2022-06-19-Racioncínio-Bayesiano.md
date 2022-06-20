---
layout: post
title:  Raciocínio Bayesiano
author: Renan Brotto
tags:
  - Probabilidade e Estatística
  - Raciocínio Bayesiano
  - Filosofia da Ciência
---

Em um dia qualquer, consideramos que a chance de chover é baixa (ao menos aqui no Brasil, no estado de São Paulo, na maior parte dos dias). Contudo, quando notamos algumas nuvens carregadas, já pegamos o guarda-chuva, mesmo que seja “só por via das dúvidas”.

O que acabamos de fazer, intuitivamente, é atualizar a nossa crença em um evento (vai chover?) com base na observação de um outro (céu com nuvens carregadas), o  chamado **Raciocínio Bayesiano**.  Tal forma de raciocínio nos fornece um meio de quantificar as probabilidades antes e depois de observarmos um evento, de um modo preciso e muito interessante. Por simplicidade, vamos denotar o evento “chover” pela letra A, e o evento “observar nuvens carregadas” pela letra B; com isso, podemos equacionar a Regra de Bayes da seguinte forma:

$$
	P(A|B) = \dfrac{P(A,B)}{P(B)}
$$


A probabilidade $$ P(A \vert B) $$ denominada probabilidade a posteriori, corresponde à probabilidade de chover, dado que vimos nuvens carregadas no céu. Já o termo $$ P(A,B) $$ denota a probabilidade dos dois eventos acontecerem simultaneamente, ou seja, a chance de chover quando vemos nuvens carregadas no céu. E por fim, $$ P(B) $$ denota a chance de observarmos nuvens carregadas, em um dia qualquer.

Podemos mudar um pouco a equação (1), usando a seguinte relação:


$$
	P(A,B) = P(A \vert B).P(B)
$$


Desse modo, a Regra de Bayes se torna


$$
	P(A \vert B) = \dfrac{P(B \vert A).P(A)}{P(B)}
$$

onde o novo termo, $$P(B \vert A)$$, é denominado *verossimilhança* e corresponde à chance de ter nuvens carregadas, dado que chove.

Esse novo formato para a Regra de Bayes é bem interessante, pois ele nos diz que a nova probabilidade de chuva, $$P(A \vert B)$$, nada mais é do que a probabilidade inicial, $$P(A)$$, atualizada pelo termo $$\dfrac{P(B \vert A)}{P(B)}$$.  Se for muito frequente termos nuvens carregadas quando chove, então o termo $$P(B \vert A)$$  será alto, aumentando as chances de que chova, agora que vemos nuvens carregadas no céu.

Para estudarmos com um pouco mais de detalhes a Regra de Bayes, vamos considerar o seguinte exemplo **(Exemplo baseado nos slides do professor Eduardo Cypriano, IAC/USP)**: *em uma caixa, temos cinco moedas, das quais uma é “trucada”, ou seja, é uma moeda que tem cara dos dois lados. Sorteamos uma moeda dessa caixa ao acaso e a lançamos três vezes. Em todos os lançamentos, observamos sempre cara. Qual a probabilidade de que a moeda escolhida seja a “trucada”*?

Antes de fazermos qualquer tipo de cálculo, vamos desenvolver uma intuição acerca do problema. Se observarmos a ocorrência sistemática de cara ao longo de muitos lançamentos, começaremos a suspeitar que a moeda usada é a “trucada”. Por outro lado, se em qualquer lançamento observarmos ao menos uma vez coroa, temos certeza absoluta de que a moeda usada não é a “trucada” (afinal, ela possui cara dos dois lados). Contudo, o problema que temos em mãos é um pouco mais complicado: temos um número relativamente pequeno de lançamentos (apenas três) e em nenhum deles observamos coroa. Como estamos em uma “zona cinzenta”, precisamos quantificar a nossa incerteza sobre a moeda e, para isso, usaremos a Regra de Bayes. Vamos adotar a seguinte notação.

* $$P(T):$$  probabilidade (*a priori*) de sortear a moeda “trucada”;
* $$P(CCC):$$ probabilidade de tirar três caras consecutivas;
* $$P( \vert CCC):$$  probabilidade *a posteriori*, ou seja, probabilidade da moeda ser a “trucada”, dado que observamos três caras; e
* $$P(CCC \vert T):$$  probabilidade de tirarmos três caras com a moeda “trucada” (verossimilhança).

Como a caixa tem cinco moedas, $$P(T) = \dfrac{1}{5}$$. Se usarmos a moeda “trucada”, sempre teremos cara e, portanto,$$P(CCC \vert T) = 1$$. Agora para calcularmos a probabilidade de tirarmos três caras, precisamos considerar dois casos possíveis: tiramos três caras com uma moeda normal ou tiramos três caras com a moeda “trucada”. Temos então, o seguinte cálculo:


$$
	P(CCC) = P(CCC \vert T).P(T) + P(CCC \vert N).P(N) = \dfrac{1}{5} + \dfrac{1}{8}.\dfrac{4}{5} = \dfrac{3}{10}
$$

Com os cálculos auxiliares feitos, vamos determinar a probabilidade *a posteriori:*

$$
	P(T \vert CCC) = \dfrac{P(CCC \vert T).P(T)}{P(CCC)} = \dfrac{1/5}{3/10} = \dfrac{2}{3}.
$$

Antes de observarmos qualquer um dos lançamentos, tínhamos uma probabilidade de $$1/5$$ ou 20% de que a moeda escolhida fosse a “trucada”; agora que observamos três caras consecutivas, temos uma chance de $$2/3$$ ou 66,6%. Os eventos que observamos moveram a nossa crença de “pouco provável que seja a moeda ‘trucada’” para “é provável que seja a moeda ‘trucada’”. O Raciocínio Bayesiano nos ajudou a partir de uma crença inicial (*probabilidade a priori*) ajustá-la de acordo com os dados observados, e obter uma nova crença no evento (*probabilidade a posteriori*), de forma clara e precisa.

Podemos também usar o Raciocínio Bayesiano para determinar a crença em uma dada teoria, à medida que realizamos experimentos para testá-la. Usando o Teorema das Probabilidades Totais, podemos reescrever a Regra de Bayes da seguinte maneira:


$$
	P(T_0 \vert D) = \dfrac{P(D|T_0).P(T_0)}{P(D|T_0).P(T_0) + \sum_{T_i \neq T_0} P(D|T_i).P(T_I)  }
$$ 

Vamos olhar para a equação acima de um modo um pouco diferente: $$P(T_0)$$ corresponde à crença inicial que temos em uma dada teoria $$T_0$$; $$P(T_0 \vert D)$$ é a crença atualizada, ou seja, quanto o observador acredita na teoria $$T_0$$ agora que observou os dados experimentais $$D$$; finalmente, $$P(D \vert T_0)$$ é a verossimilhança entre os dados e a teoria, ou seja, como os dados observados aderem à teoria $$T_0$$. Dados que aderem fortemente a uma teoria levam a uma alta verossimilhança; dados que pouco adequam a uma teoria levam a uma verossimilhança baixa.

Notamos, então, que a probabilidade a posteriori consiste numa composição entre verossimilhanças: comparamos a verossimilhança entre os dados e a teoria $$T_0$$ com a verossimilhança dos mesmos dados com todas as demais teorias possíveis. Nossa crença na teoria $$T_0$$ deverá aumentar **somente** se a verossimilhança entre os dados e $$T_0$$ for alta **ao mesmo tempo que** a verossimilhança de  tais dados com outras explicações for baixa. Com a Regra de Bayes, buscamos, portanto, comparar a força de explicação da teoria $$T_0$$ com a força de todas as demais teorias possíveis.  

<div class="card mb-3">
    <img class="card-img-top" src="./img/CaboDeGuerraTeorias.png"/>
    <div class="card-body bg-light">
        <div class="card-text">
            A Regra de Bayes mede a força de explicação da Teoria sob Teste com todas as demais Teorias Alternativas. Imagem feita pelo autor.
        </div>
    </div>
</div>


<!---
<img src="img/CaboDeGuerraTeorias.png" width="400" height="auto"  class="center" />
-->

<!---
![A Regra de Bayes mede a força de explicação da Teoria sob Teste com todas as demais Teorias Alternativas. Imagem feita pelo autor.](2022/06/19/CaboDeGuerraTeorias.png)
-->

Se os dados D aderem bem à Teoria  $$T_0$$, então o numerador da equação será alto. Contudo, se os mesmos dados aderem bem às outras teorias $$T_i$$, o denominador também vai aumentar. Um efeito tende a compensar o outro e, por isso, a crença na teoria $$T_0$$ não aumenta, necessariamente. É por essa razão que não podemos acreditar em uma teoria somente porque os dados coletados levam a uma alta verossimilhança. Para citar um provérbio Bayesiano, “a verossimilhança dos dados não é igual à crença na teoria”.

Um exemplo interessante para ilustrar esta diferença é a teoria da Terra Plana. Defensores desta teoria alegam que algumas ilhas não deveriam ser vistas de determinados pontos do oceano, caso a Terra fosse curvada. Temos neste caso uma observação (a ilha que não deveria ser vista) que adere bem à uma teoria (Terra Plana). Este é um exemplo de alta verossimilhança, mas onde devemos ter pouca crença na Teoria.

A mesma observação pode ser muito bem explicada pelo modelo de Terra no formato de geóide irregular com um raio muito grande. Como a verossimilhança nesse caso é tão grande quanto a do caso da Terra Plana, a crença nesta última teoria perde força. Há ainda muitas outras teorias que explicariam essa mesma observação muito bem: poderíamos ter uma Terra em formato cilíndrico, ou retangular, ou irregular, mas com pequenas elevações situadas nas posições de cada uma dessas ilhas. Como as possibilidades são muitas, observar ilhas supostamente invisíveis não é evidência suficiente de que a Terra seja plana. Quando os dados aderem muito bem a muitas teorias, isso se torna um indicativo de que tais dados não são discriminatórios e que precisamos de estudos mais aprofundados.

Por fim, devemos notar uma sutileza: crença na teoria **é diferente** da chance da teoria estar correta. A crença na Teoria só pode ser definida dada a existência de um observador. Ela é portanto algo subjetivo, ou seja, que depende do sujeito observando e explicando o evento. Dois observadores diferentes poderiam coletar os mesmos dados e ainda assim terem crenças diferentes em uma mesma teoria. Por outro lado, uma Teoria está correta ou não independentemente da presença de um observador. A Verdade a respeito de uma teoria é uma propriedade intrínseca: uma teoria é verdadeira mesmo que nenhum ser humano consiga constatar tal fato. Devemos tomar muito cuidado para não cair no erro indutivista de dizer que se mais dados corroboram uma teoria, ela tem “maior probabilidade de estar certa”. Podemos coletar uma quantidade enorme de dados, mas, dada a primeira evidência contrária, a teoria que tanto buscamos justificar é colocada em cheque.
