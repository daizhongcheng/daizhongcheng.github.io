---
title: zero and pole gain
comments: true
mathjax: true
date: 2018-05-28 10:18:51
tags:
categories: Matlab simulation
---
#### Nullstellen Polstellen Darstellung
die Nullstellen Polstellen Darstellung kann beschreibt Das Uebertragungsverhalten.
$$ G(s) = k\frac{(s-z_1) \dots  (s-z_{m-1})(s-z_m)}{(s-p_1) \dots (s-p_{n-1})(s-p_n)} $$
hier ist k ein Verstaerkungsfaktor.z_1 bis z_m sind Nullstellen.p_1 bis p_n sind Polstellen.
#### Befehl zpk(z,p,k)
- z bedeutet zero
- p bedeutet pole
In matlab wir koennen einfach eingeben.
ZB.
- >> h = zpk([1 2 3],[1 5 6],2);
#### Rationale Funktion in s
zuesert wir sollen s definieren.
' >> s = zpk('s');'
dann direct rationale Funktion is s ein geben.
' >> h = 2*1/(s-1)*(s+2);'
