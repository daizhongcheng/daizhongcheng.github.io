---
title: zpk-mimo-Modellen
comments: true
mathjax: true
date: 2018-05-27 22:33:54
tags:
categories: Matlab simulation
---
#### MIMO Modelle
$$ G(s) = \begin{pmatrix} h_{11} & h_{12} \\\\ h_{21} & h{22} \end{pmatrix} $$
#### Eingabe in Matlab erfolgt auf die zwei Arten:
1.definieren der einzelnen zpk-siso-modelle mit zpk
h11 = zpk(z1,p1,k1) ;
h12 = zpk(z2,p2,k2) ;
h21 = zpk(z3,p3,k3) ;
h22 = zpk(z4,p4,k4) ;
G = [h11 h12;h21 h22];
2.rationale Funktionen is s:
s = zpk('s');
h11 = 2*1/((s-1)*(s+2));
h12 = 2*(s-4)/((s-1)*(s+2));
h21 = 3*(s-5)/((s-7)*(s-5));
h22 = 4*(s-1)*(s-2)*(s-3)/((s-3)*s(4.5));
G = [h11 h12;h21 h22];
3.Definieren von zwei Cell Arrays
$$ Z = \begin{pmatrix} z_{11} & z_{12} \\\\ z_{21} & z_{22}  \end{pmatrix}      $$
$$ P = \begin{pmatrix} p_{11} & p_{12} \\\\ p_{21} & p_{22}  \end{pmatrix}      $$
$$ K = \begin{pmatrix} k_{11} & k_{12} \\\\ k_{21} & k_{22}  \end{pmatrix}      $$
Aufruf von zpk mit den Parametern Z,P und K.
$$ >> G= zpk(Z,P,K) ;
#### Matlab Zeigen
click  [Matlab Zeigen](https://sites.google.com/site/publishcode/home/zpk) 
<html><head>
      <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
   <!--
This HTML was auto-generated from MATLAB code.
To make changes, update the MATLAB code and republish this document.
      --><title>ZPK MIMO Modell</title><meta name="generator" content="MATLAB 9.3"><link rel="schema.DC" href="http://purl.org/dc/elements/1.1/"><meta name="DC.date" content="2018-10-28"><meta name="DC.source" content="zpklern.m"><style type="text/css">
html,body,div,span,applet,object,iframe,h1,h2,h3,h4,h5,h6,p,blockquote,pre,a,abbr,acronym,address,big,cite,code,del,dfn,em,font,img,ins,kbd,q,s,samp,small,strike,strong,sub,sup,tt,var,b,u,i,center,dl,dt,dd,ol,ul,li,fieldset,form,label,legend,table,caption,tbody,tfoot,thead,tr,th,td{margin:0;padding:0;border:0;outline:0;font-size:100%;vertical-align:baseline;background:transparent}body{line-height:1}ol,ul{list-style:none}blockquote,q{quotes:none}blockquote:before,blockquote:after,q:before,q:after{content:'';content:none}:focus{outine:0}ins{text-decoration:none}del{text-decoration:line-through}table{border-collapse:collapse;border-spacing:0}

html { min-height:100%; margin-bottom:1px; }
html body { height:100%; margin:0px; font-family:Arial, Helvetica, sans-serif; font-size:10px; color:#000; line-height:140%; background:#fff none; overflow-y:scroll; }
html body td { vertical-align:top; text-align:left; }

h1 { padding:0px; margin:0px 0px 25px; font-family:Arial, Helvetica, sans-serif; font-size:1.5em; color:#d55000; line-height:100%; font-weight:normal; }
h2 { padding:0px; margin:0px 0px 8px; font-family:Arial, Helvetica, sans-serif; font-size:1.2em; color:#000; font-weight:bold; line-height:140%; border-bottom:1px solid #d6d4d4; display:block; }
h3 { padding:0px; margin:0px 0px 5px; font-family:Arial, Helvetica, sans-serif; font-size:1.1em; color:#000; font-weight:bold; line-height:140%; }

a { color:#005fce; text-decoration:none; }
a:hover { color:#005fce; text-decoration:underline; }
a:visited { color:#004aa0; text-decoration:none; }

p { padding:0px; margin:0px 0px 20px; }
img { padding:0px; margin:0px 0px 20px; border:none; }
p img, pre img, tt img, li img, h1 img, h2 img { margin-bottom:0px; } 

ul { padding:0px; margin:0px 0px 20px 23px; list-style:square; }
ul li { padding:0px; margin:0px 0px 7px 0px; }
ul li ul { padding:5px 0px 0px; margin:0px 0px 7px 23px; }
ul li ol li { list-style:decimal; }
ol { padding:0px; margin:0px 0px 20px 0px; list-style:decimal; }
ol li { padding:0px; margin:0px 0px 7px 23px; list-style-type:decimal; }
ol li ol { padding:5px 0px 0px; margin:0px 0px 7px 0px; }
ol li ol li { list-style-type:lower-alpha; }
ol li ul { padding-top:7px; }
ol li ul li { list-style:square; }

.content { font-size:1.2em; line-height:140%; padding: 20px; }

pre, code { font-size:12px; }
tt { font-size: 1.2em; }
pre { margin:0px 0px 20px; }
pre.codeinput { padding:10px; border:1px solid #d3d3d3; background:#f7f7f7; }
pre.codeoutput { padding:10px 11px; margin:0px 0px 20px; color:#4c4c4c; }
pre.error { color:red; }

@media print { pre.codeinput, pre.codeoutput { word-wrap:break-word; width:100%; } }

span.keyword { color:#0000FF }
span.comment { color:#228B22 }
span.string { color:#A020F0 }
span.untermstring { color:#B20000 }
span.syscmd { color:#B28C00 }

.footer { width:auto; padding:10px 0px; margin:25px 0px 0px; border-top:1px dotted #878787; font-size:0.8em; line-height:140%; font-style:italic; color:#878787; text-align:left; float:none; }
.footer p { margin:0px; }
.footer a { color:#878787; }
.footer a:hover { color:#878787; text-decoration:underline; }
.footer a:visited { color:#878787; }

table th { padding:7px 5px; text-align:left; vertical-align:middle; border: 1px solid #d6d4d4; font-weight:bold; }
table td { padding:7px 5px; text-align:left; vertical-align:top; border:1px solid #d6d4d4; }





  </style></head><body><div class="content"><h1>ZPK MIMO Modell</h1><pre class="codeinput"><span class="comment">%erstens Verfahren</span>
<span class="comment">%name:zhongcheng</span>
h11 = zpk([1 2 5],[1 3 2],1) ;
h12 = zpk([2 3 6],[5 4],2) ;
h21 = zpk([2.1 3],[0 1],4) ;
h22 = zpk([4 7],[1 6],2) ;
H =[h11 h12 ; h21 h22]
</pre><pre class="codeoutput">H =
 
  From input 1 to output...
       (s-1) (s-2) (s-5)
   1:  -----------------
       (s-1) (s-2) (s-3)
 
       4 (s-2.1) (s-3)
   2:  ---------------
           s (s-1)
 
  From input 2 to output...
       2 (s-2) (s-3) (s-6)
   1:  -------------------
           (s-5) (s-4)
 
       2 (s-4) (s-7)
   2:  -------------
        (s-1) (s-6)
 
Continuous-time zero/pole/gain model.

</pre><p class="footer"><br><a href="http://www.mathworks.com/products/matlab/"></a><br></p></div></body></html>
#### 小结
至此，利用matlab，我们学会了用tf,zpk描述模型。下一部分我将要学到利用matlab去描述状态空间模型。
