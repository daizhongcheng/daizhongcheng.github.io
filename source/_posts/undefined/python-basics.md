---
title: python basics
comments: true
mathjax: true
date: 2018-07-05 21:48:11
tags:
categories: python
---
#### Entering Expressions into the interactive shell
my operation system is OS X
how to enter the interactive Shell?
you can just simple type in terminal
>> python or python3
math operator 
{% codeblock %}
** is Exponet  2**3=8
%   Modulus/remainder 22%8=6
// Integer division/floored quotient 22//8=6
/  Division 22/8=2.75
*  multiplication 3*5=15
-  subtraction 5-2=3
+  additon 2+2=4
{% endcodeblock %}
 
#### The integer,floationg-point,and string data types
##### common data types
Intergers examples -2,-1,0,1,2,3,4,5
floating-point numbers -1.25,-1.0,-0.5,0.0,0.5,1.0,1.25
strings 'a','11 cats'
{% codeblock %}

>>> 'alice'+'zc'
'alicezc'

{% endcodeblock %}
{% codeblock %}
>>> 'Alice' + 42
type error:can't 'int' object to str implicity

{% endcodeblock %}
{% codeblock %}
>>>'alice'*5
alicealicealicealicealice   

{% endcodeblock %}
{% codeblock %}
>>>'alice'*'bob'
error
>>>'alice'*5.0
error
{% endcodeblock %}


#### storing Values in Variables
a variable is like a box in the computer's memory where you can store a single value.if you want to use the result of an evaluated expression later in your program,you can save it inside a variable.i
if you enter the assignmen statemen zc = 42,then a variable named zc will have the integer value 42 stored in it.
vaiables name must following three rules:
it can be one word
it can use only letters,numbers,and the underscore character.
it cant begin with a number

#### your first program 
this program says hello and asks for my name.
{% codeblock %}
print('hello world!')
print('what is your name?') # ask for their name
myname = input() # type your name
print('it is good to meet you,'+myname)
print('it is good to meet you,'+myname)
print(len(myname))
{% endcodeblock %}

#### function
str(),int(),and float()
will evaluate to the string,integer,and floationg-point forms






















