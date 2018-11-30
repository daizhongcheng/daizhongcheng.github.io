---
title: python basic
comments: true
mathjax: true
date: 2018-11-16 23:25:06
long:
tags:
categories: python
---
### list example
{% codeblock %}
1 catNames =[]
  2 while True:
  3     print('Enter the name of the cat'+str(len(catNames)+1))
  4     name = input()
  5     if name =='':
  6         break
  7     catNames = catNames + [name]
  8 print('The cat names are:')
  9 for i in catNames:
 10     print(''+i)
 11     # catNames=['yang','zc']
{% endcodeblock %}
### function example
{% codeblock %}
1 ## write your own functions
  2 def hello():
  3     print('howdy!')
  4 hello()
  5 ## write your 2 functions
  6 def sage(age):
  7     print("you are " + age)
  8 sage("12")
  9 sage("10")
{% endcodeblock %}
### global statemen
{% codeblock %}
1 ## global statement                                         
  2 def spam():
  3     global eggs     # global statement,this variable will be     global
  4     eggs = 'spam'
  5 eggs = 'global'
  6 spam()
  7 print(eggs)
{% endcodeblock %}
### random function
{% codeblock %}
1 # this is a guess the number game.
  2 import random
  3 secretNumber = random.randint(1,20)
  4 print('I am thinking of a number between 1 and 20.')
  5 # ask the player to guess 6 times
  6 for guessestaken in range(1,7):
  7     print('take a guess.')
  8     guess = int(input())
{% endcodeblock %}
### The Tuple Data Type
eggs = ('hello',42,0.5)
tupels are typed with parenthese()
tuples cannot have their values modified

