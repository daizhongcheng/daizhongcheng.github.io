---
title: correlation 2D for CRV

comments: true
mathjax: true
date: 2018-11-01 07:16:06
tags:
categories: Matlab simulation
---
author:Zhongcheng Dai
{% codeblock %}
function [ fimCorr ] = myCorrelation(fim,fop);
%MYCORRELATION calculation 2D correlation for CRV
%   name:zhongcheng dai
%   studentnumber:3043255
%   fimCorr = myCorrelation(fim,fop) calculates the correlation of the
%   image function fim and the operator function fop as introduced in the
%   CRV lecture. Both fim and fop have to be matrices. fop has to be
%   smaller than fim and of odd size. fimCorr is of the same size as fim.
%   The outer pixels, where the correlation can not be calculated
%   sufficiently, are set to zero;

%% b
  tfim = ndims(fim);
   tfop = ndims(fop);
   if tfim ~= 2 
        error('fim is not a 2d');
   end

  if tfop ~= 2
       error('fop is not a 2d');
   end
rfim = ismatrix(fim);
rfop = ismatrix(fop);
if rfim ~= 1
    error('fim is not a matrix');
end
if rfop ~= 1
    error('fop is not a matrix');
end

%% c
   [sfop1 sfop2]= size(fop); 
   mfop1 = mod(sfop1,2);  
   mfop2 = mod(sfop2,2);
   if mfop1 == 0
     error("fop don't allow even row ");
   end
   if mfop2 == 0;
     error("fop don't allw even column");
   end
%% d
[orow ocl] = size(fop);
[lfim bfim] = size(fim);
if orow>lfim | ocl > bfim
    error('fop is not smaller than the fim');
end
%% e

    Fim = double(fim);
    Fop = double(fop);

%% f
[orow ocl] = size(fop);
[lfim bfim] = size(fim);
h1 = (orow-1)/2 ;
h2 = (ocl-1)/2 ;

%% g

fimCorrt=zeros(lfim,bfim);  
for xi=h1+1:lfim-h1
    for yi=h2+1:bfim-h2
                sumf = 0;
                for j=1:ocl
                             for i=1:orow
                              sumf = sumf+Fop(i,j)*Fim(xi+i-h1-1,yi+j-h2-1);
                             end
                end
                    fimCorrt(xi,yi) = sumf;
    end    
end
fimCorr=fimCorrt;

end
{% endcodeblock %}
<html><head>
      <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
   <!--
This HTML was auto-generated from MATLAB code.
To make changes, update the MATLAB code and republish this document.
      --><title>fimcorr</title><meta name="generator" content="MATLAB 9.3"><link rel="schema.DC" href="http://purl.org/dc/elements/1.1/"><meta name="DC.date" content="2018-11-01"><meta name="DC.source" content="fimcorr.m"><style type="text/css">
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





  </style></head><body><div class="content"><pre class="codeinput">fimcorr2 = myCorrelation(magic(5),magic(3));
fimcorr3 = myCorrelation(magic(5),-1:1);
fimcorr4 = myCorrelation(magic(5),(-1:1)');
</pre><pre class="codeoutput">fimCorr =

     0     0     0     0     0
     0   405   570   585     0
     0   550   615   730     0
     0   595   760   575     0
     0     0     0     0     0


fimCorr =

     0   -16   -16    14     0
     0   -16     9     9     0
     0     9    14     9     0
     0     9     9   -16     0
     0    14   -16   -16     0


fimCorr =

     0     0     0     0     0
   -13   -18    12    12     7
   -13     7    12     7   -13
     7    12    12   -18   -13
     0     0     0     0     0

</pre></body></html>

