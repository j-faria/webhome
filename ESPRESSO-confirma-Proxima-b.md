---
layout: post
title: ESPRESSO confirma o exoplaneta Proxima b
author: joao
lang: pt
comments: true
ref: espresso
permalink: ESPRESSO-confirma-Proxima-b
date: 2020-05-26
---


{% include image.html 
    url="/assets/img/planet_M_dwarf.jpg"
    description="Credit: ESO/M. Kornmesser"
%}

Em 2016, a descoberta[^1] de um exoplaneta em órbita de Proxima Centauri foi um
resultado estrondoso. A Proxima é a estrela mais próxima do Sol, a uma distância
de "apenas" 1.3 parsec, ou 4.2 anos-luz de nós. E Proxima *b*, o planeta, tem
uma massa parecida com a da Terra e orbita dentro da zona habitável.

[^1]: O artigo ciêntifico pode ser encontrado [aqui](https://arxiv.org/abs/1609.03449) (em Inglês).

Agora, o novo instrumento chamado ESPRESSO[^2] conseguiu **confirmar**, de forma 
independente, a presença deste planeta e medir a sua massa com maior precisão.
O ESPRESSO é um novo espéctrografo instalado no Very Large Telescope (VLT) do 
ESO, no observatório de Paranal. Este instrumento consegue medir velocidades 
radiais com uma precisão sem precedentes, o que permite detetar planetas de 
muito pequena massa, como o Proxima b.

[^2]: Pode ler mais sobre o ESPRESSO [aqui](http://www.iastro.pt/news/news.html?ID=80).

Em poucos anos, os instrumentos do ELT (o *Extremely* Large Telescope) vão 
conseguir olhar para Proxima b com novos olhos e caracterizar a atmosfera deste 
planeta potencialmente habitável.


<p style="text-align: center;">
<!-- Veja o <a href="#" target="_blank">comunicado de imprensa</a> do IA -->
<!-- Veja o <a href="http://www.iastro.pt/news/news.html?ID=133" target="_blank">comunicado de imprensa</a> do IA -->
<!-- &nbsp; &mdash; &nbsp;  -->
Leia <a href="https://arxiv.org/abs/2005.12114" target="_blank">o artigo</a> no ArXiv (em Inglês)
</p> 


## A estrela

Os astrónomos classificam Proxima Centauri como uma anãs vermelha (ou estrela *M*). 
A sua massa e raio são menores que os do Sol por um factor de 8, aproximadamente.
A estrela tem uma luminosidade muito baixa (apesar de estar tão perto) mas, como 
outras anãs vermelhas, o seu brilho pode por vezes aumentar dramaticamente 
devido à actividade magnética no seu interior.
Proxima não é visível a olho nu, mas está junto a outras duas estrelas, α Cen A 
e B, as duas outras componentes do sistema triplo.


![Proxima_Sol]({{site.baseurl}}/assets/img/Proxima_Sun.png)

## O planeta

O planeta descoberto à volta de Proxima foi apelidade de *Proxima b*, porque os
astrónomos têm uma imaginação muito fértil a dar nomes a coisas. Este planeta
orbita a estrela a uma distância de 0.05 AU[^3] (cerca de 7.5 milhões de km) com
um período orbital de 11.2 dias. Isto quer dizer que um *ano* em Proxima b 
demora 11.2 dias!

[^3]: AU é uma unidade de distância, a Unidade Astronómica. Corresponde à 
      distância média entre a Terra e o Sol. Ou seja, a Terra orbita a 1 AU.

![Proxima_orbita]({{site.baseurl}}/assets/img/proxima_orbit.png)


Proxima b é um pouco mais massivo do que a Terra (1.27 massas terrestres) e é,
quase de certeza, um planeta rochoso como o nosso. Mesmo estando muito mais 
próximo da sua estrela, a temperatura à superfície do planeta pode ser 
suficiente para a água estar em estado liquído. Dizemos que o planeta está na
zona habitável. Mas isso não quer dizer que seja *habitado*! Isso, não sabemos ainda.


![Proxima_Terra]({{site.baseurl}}/assets/img/Proxima_b_Earth.png)


## O desafio da deteção

Encontrar estes planetas de pequena massa não é uma tarefa fácil. Em primeiro
lugar, a amplitude do sinal nas velocidades radiais que o planeta exerce na
estrela depende da massa e período orbital do planeta. Os planetas mais
massivos, como Júpiter e Saturno, criam sinais 100 vezes maiores do que os mais
leves, como a Terra e Vénus, apesar de estarem mais longe do Sol. Em outras
palavras, é mais fácil detetar planetas massivos que orbitam perto das suas
estrelas.

O planeta Proxima b está relativamente perto da estrela, mas tem uma pequena
massa. Então, como é que o conseguimos detetar?

A resposta é que a estrela é muito menos massiva que o Sol. Isto significa que o
planeta, mesmo com uma massa parecida à da Terra, consegue puxar e empurrar a
estrela um pouco mais, resultando num sinal de velocidade radial com maior
amplitude.

Na realidade, o planeta não orbita a estrela: ambos orbitam o centro de massa do
sistema. Ou seja, a estrela também se move, de trás para a frente,
aproximando-se e afastando-se de nós. O que observamos no espectro da estrela é
uma variação da luz estelar para o vermelho e para o azul. Quando esta variação
é periódica, conseguimos inferir a presença de um planeta. Esta é a essência do
método das velocidades radiais.

Uma fonte adicional de dificuldades é a actividade magnética da própria estrela.
À medida que a estrela roda sobre si própria, a cada 83 dias no caso de Proxima,
machas estelares à superfície produzem uma modulação extra nas velocidades
radiais. Muitas vezes esta modulação é maior do que os sinais dos planetas e é
necessário encontrar uma forma de a corrigir para podermos detectar os planetas
de menor massa. 

Neste novo estudo sobre o Proxima b, usámos uma ferramenta matemática chamada de
processos Gaussianos (GP), que conseguem modelar os sinais induzidos pela
actividade estelar. Pessoalmente, tenho trabalhado com processos Gaussianos há
já vários anos, mas ainda é impressionante ver o quanto nos podem ajudar. Na
figura abaixo conseguem ver o modelo GP junto com as velocidades radiais obtidas
pelo ESPRESSO. Todas estas variações são causadas pela própria estrela. O sinal
do planeta aparece adicionado a este sinal de actividade.


![Proxima_GP]({{site.baseurl}}/assets/img/proxima_GP.png)


Mas as novas observações do ESPRESSO são mais impressionantes quando comparadas
com os dados obtidos anteriormente com outros instrumentos. O planeta Proxima b
foi inicialmente detetado com o HARPS, um outro instrumento do ESO, situado no
observatório de La Silla. O HARPS era, até agora, o mais preciso espéctrografo
"caçador" de exoplanetas, e responsável pela deteção de centenas de exoplanetas.
É um feito impressionante de engenharia que o ESPRESSO consiga agora obter uma
precisão *muito mais elevada* na medição da velocidade radial

A figura abaixo mostra as observações do ESPRESSO (a verde) juntamente com as do
HARPS (a laranja). A melhoria nas barras de erro (que representam a precisão das
medições) é absolutamente impressionante.


![Proxima_phase_curve]({{site.baseurl}}/assets/img/proxima_phase_curve.png)


Valerá a pena alguma contexto: o ESPRESSO está agora a medir velocidades radiais
com uma precisão de 30 cm/s. Esta é, aproximadamente, a velocidade a que uma
tartaruga das Galápagos se move. Isto significa que somos agora capazes de medir
a velocidade de uma estrela, a 40 triliões de quilómetros, com uma precisão
semelhante à velocidade de uma targaruga!


### O futuro

Este é apenas o primeiro exoplaneta confirmado pelo ESPRESSO. Estamos neste
momento a observar outras estrelas, algumas como a Proxima e outras mais
parecidas com o Sol. Não ficaria surpreso se, daqui a alguns meses, escrevesse
aqui a anunciar a descoberta de uma planeta como a Terra na zona habitábel de
uma estrela como o Sol. O futuro promete!


---