---
title: coprime factorization
comments: true
mathjax: true
date: 2018-11-19 14:30:51
long:
tags:
categories: robust
---
#### right coprime factorization,a state feedback interpretation
$ y = Gu \rightarrow 
\begin{cases}
\dot{x}=Ax+Bu \\\\
y = Cx+Du
\end{cases}
\rightarrow{u:=Fx+v}
\begin{cases}
\dot{x}=(A+BF)x+Bv \\\\
u=Fx+v \\\\
y=Cx+D(v+Fx)=(C+DF)x+Dv
\end{cases}
我们把u定义的公式代入，得到F和v的式子。F,v的式子可以得到传递矩阵。
M,N
$ u = Mv, y = Nv
#### The left co-prime factorization
an observer-based residual generation interpretation

