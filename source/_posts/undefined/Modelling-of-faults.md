---
title: Modelling of faults
comments: true
mathjax: true
date: 2018-06-03 15:51:56
tags:
categories: FDI
---
this is my note,the book I read is Model-based Fault Diagnosis Techniques-Design Schemes Algorithms and Tools.Author is Steven X.Ding.
### Modelling of faults
#### three faults
there are manys to model faults,the widely used one is 
$ y(p)=G_{yu}(p)u(p)+G_{yd}(d)d(p)+G_{yf}(p)f(p) $
where f is unknonw vector.G_{yf} is a known transfer matrix.
Suppose that a minimal state space realization is given by
$ \dot{x} = Ax+Bu+E_dd+E_ff $
$ y = Cx+Du+F_dd+F_ff $ 
where $ E_f,F_f $ is known.then we have
$ G_{yf}(p)=F_f+C(pI-A)^{-1}E_f $
$ E_f,F_f $ indicate the place where a fault occurs and its influence on the system components.
there are three form faults.
1.sensor  faults $ f_S $
2.actuator faults $ f_A $
3.process faults $ f_P $
#### Sensor fault
 can be modelled by setting $ F_f = I $ i.e.
$ y = Cx + Du +F_dd+f_S $
#### actuator faults
can be modelled by setting $ E_f=B,F_f=D $,i.e.
$ \dot{x}=Ax+B(u+f_A)+E_dd,y=Cx+D(u+f_A)+F_dd $
#### process faults 
can be modelled by $ E_f=E_p and F_f = F_p $ 
#### summary
for the three fault,we define 
$f = \begin{bmatrix} f_A \\\\ f_P \\\\ f_S \end{bmatrix} , E_f=\begin{bmatrix} B & E_p & 0\end{bmatrix} F_f = \begin{bmatrix} D & F_p & I \end{bmatrix} $

 














<html>
<head>
<script async custom-element="amp-auto-ads"
        src="https://cdn.ampproject.org/v0/amp-auto-ads-0.1.js">
</script>
</head>
<body>
<amp-auto-ads type="adsense"
              data-ad-client="ca-pub-5143313871951336">
</amp-auto-ads>

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<script>
     (adsbygoogle = window.adsbygoogle || []).push({
          google_ad_client: "ca-pub-5143313871951336",
          enable_page_level_ads: true
     });
</script>
</body>
</html>
