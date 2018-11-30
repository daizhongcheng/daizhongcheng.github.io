---
title: use arrays to describe MIMO system
comments: true
mathjax: true
date: 2018-05-26 00:13:42
tags:
categories: Matlab simulation 
---
#### cell arrays
zaehlerpolynome := NUM
nennerpolynome  := DEN
$$  NUM = \begin{pmatrix} n_{11} &  n_{12} \\\\ n_{21} &  n_{22} \end{pmatrix}  $$
$$  DEN = \begin{pmatrix} d_{11} & d_{12} \\\\ d_{21} & d{22} \end{pmatrix}  $$
In Matlab geben wir die Vektoren mit den Koeffizienten von s in absteigende Reihenfolge von s ein.

#### IN matlab
>> NUM = {[2 -3] [1 1 -6];[1 2] 1}
>> DEN = {[1 1] [1 5];[1 5 4] [2 6 10]}
Und dann koennen wir noch ein mal tf Befehl benutzen.
>>G(s) = tf(NUM,DEN);


#### System nur mit Verstaerkung
das bedeutet output / input = constant
zB.
$$ G_1(s) = 3/1  $$
$$ G_2(s) = 0/2 $$
in matlab wir koennen eingeben
>>G = tf{[1 2;3 0]}; %1 2 sind input,3 0 sind ouptput.
