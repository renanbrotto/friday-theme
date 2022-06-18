---
layout: defaults/page
permalink: index.html
narrow: true
title: Bem Vindo(a)!
---

Criei essa página com o intuito de compartilhar alguns de meus estudos e procurar, mesmo que de forma mínima, divulgar a Ciência. Os assuntos que tenho interesse em tratar nessa página são:

* Processamento de Sinais
* Computação
* Probabilidade e Estatística
* Filosofia da Ciência
* Astrofísica

Como o objetivo é a divulgação científica, procurarei, sempre que possível, não me prender muito aos aspectos mais técnicos. Quando isso ocorrer, procurarei deixar referências técnicas para quem quiser se aprofundar mais.

Caso queira entrar em contato comigo, por favor, me mande um e-mail em: renanbrotto@gmail.com

### Textos Recentes

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


