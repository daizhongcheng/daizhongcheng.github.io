---
title: Modellierung linearer Zeitinvarianter Systeme
comments: true
mathjax: true
date: 2018-05-24 19:47:58
tags:
categories: Matlab simulation
---
#### LTI-Modelle
- Zu Beginn wir machen die mathematische , systembeschreibung, die die Zusammenhaenge zwischen den Eingaengen u und den Ausgaengen y beschreibt.
- Matlabtellt nun fuer zeitkontinuierlicheund -diskrete lineare zeitinvariante systeme(LTI-system) die folgenden vier Darstellungsarten zur Verfuegung:
1.transfer function
2.zero-pole-gain ZPK
3.state-space
4.frequency response data

#### Uebertragungsfunktion
Eine Uebertragungsfunktion ist mit dem Zaehlerpolynom und dem Nennerpolynom,und beschreibt das Uebertragungsverhalten eines Systems im Laplace-Breich.
$ h(s)=\frac{num(s)}{den(s)}=\frac{a_ms^m+a_{m-1}s^{m-1}+ \dots +a_1 s+a_0}{b_n s^n+b_{n-1} s^{n-1}+ \dots +b_1 s+b_0} $
#### Erstellen von TF-SISO-Modellen
1.Befehl:tf(num,den)
##### ZB.transfor function
$ \frac{4s-2}{s-3} $
in matlab:G(s)=tf([4 -2],[1 -3])
##### ZB.rationale function in s
Es wird zuerst die Variable s als TF-modell definiert
>> s = tf('s')
>> G(s) =(4*s-2)/(s-3)
##### ZB.MIMO TF
$ G(s)=\begin{bmatrix} g_{11} & g_{12} \\\\ g_{21} & g_{22} \\ \end{bmatrix} $

$ g_{11}=\frac{2s-3}{s+1} $
$ g_{12}=\frac{s^2+s-6}{s+5} $
$ g_{21}=\frac{s+2}{s+4} $
$ g_{22}=\frac{-1}{2s^2+6s+10} $
* in matlab 
g11 = tf([2 -3],[1 1]);
g12 = tf([1 1 -6],[1 5]);
g21 = tf([1 2],[1 4]);
g22 = tf([-1],[2 6 10]);
Zusammenfuegen zur Matrix G:
G = [g11 g12;g21 g22];




