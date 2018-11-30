---
title: Zeitdiskrete Darstellung von LTI-Modellen
comments: true
mathjax: true
date: 2018-07-01 09:55:26
tags:
categories: Matlab simulation
---
#### Die Matlab-Befehle
{% codeblock %}
systf syszpk sysss sysf rd
= tf(num,den,Ts) = zpk(z,p,k,Ts)
= ss(a,b,c,d,Ts)
= frd (ant,f req,Ts)
{% endcodeblock %}
#### Eine zeitdiskrete Uebertragungsfunktion
z.B.
$ h_{TF}=\frac{z-0.5}{z^2+z-2}=h_{ZPK}=\frac{z-0.5}{(z+2)(z-1)} $
{% codeblock %}
Befehl:
tf(num,den,Ts)
Befehl:
zpk(z,p,k,Ts)

h=tf([1 -0.5],[1 1 -2],0.01) ;
h=zpk(0.5,[-2,1],1,0.01);

{% endcodeblock %}
#### Rationale Funktion in z
{% codeblock %}
z = tf('z',0.01);
g= (z-0.05)/(z^2+z-2);
or
z=zpk('z',0.01);
g= (z-0.05)/((z+2)*(z-1))

{% endcodeblock %}
#### Matlab Zeigen
      <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
   <!--
This HTML was auto-generated from MATLAB code.
To make changes, update the MATLAB code and republish this document.
      --><title>discretelern</title><meta name="generator" content="MATLAB 9.3"><link rel="schema.DC" href="http://purl.org/dc/elements/1.1/"><meta name="DC.date" content="2018-10-29"><meta name="DC.source" content="discretelern.m"><style type="text/css">
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





  </style></head><body><div class="content"><h2>Contents</h2><div><ul><li><a href="#1">normal</a></li><li><a href="#2">Rationale Funktion</a></li></ul></div><h2 id="1">normal</h2><pre class="codeinput">h=tf([1 -0.5],[1 1 -2],0.01)
h=zpk(0.5,[-2,1],1,0.01)
</pre><pre class="codeoutput">h =
 
    z - 0.5
  z^2 + z - 2
 
Sample time: 0.01 seconds
Discrete-time transfer function.


h =
 
    (z-0.5)
  (z+2) (z-1)
 
Sample time: 0.01 seconds
Discrete-time zero/pole/gain model.

</pre><h2 id="2">Rationale Funktion</h2><pre class="codeinput">z = tf(<span class="string">'z'</span>,0.01)
g= (z-0.05)/(z^2+z-2)

z=zpk(<span class="string">'z'</span>,0.01);
g= (z-0.05)/((z+2)*(z-1))
 
Sample time: 0.01 seconds
Discrete-time transfer function.


g =
 
   z - 0.05
  z^2 + z - 2
 
Sample time: 0.01 seconds
Discrete-time transfer function.


g =
 
   (z-0.05)
  (z+2) (z-1)
 
Sample time: 0.01 seconds
Discrete-time zero/pole/gain model.


