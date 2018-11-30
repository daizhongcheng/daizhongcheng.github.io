---
title: list and tuple
comments: true
mathjax: true
date: 2018-11-15 09:07:20
long:
tags:
categories: python
---
## The list data type
A list is a vale that contains multiple values in an ordered sequence.Items are separed with commas.
{% codeblock %}
[1,2,3]
['cat','bat']
spam = ['cat','bat']
{% endcodeblock %}
### Getting individual values in a list with indexes
{% codeblock %}
spam = ['cat','bat','rat','elephant']
spam[0]
spam[1]
{% endcodeblock %}
list can also contain other list values.
{% codeblock %}
spam = [['cat','bat'],[10,20,30,40,50]]
spam[0]
- ['cat','bat']
spa,[0][1]
'bat'
{% endcodeblock %}
### Negative Indexes
While indexes start at 0 and go up,you can also use negative integers for the index.The integer value -1 refers to the last index in a list,the value -2 refers to the second-to-last index in a list,and so on.
{% codeblock %}

spam = ['cat','bat','rat','elephant']
spam[-1]
answer is : 'elephant'
{% endcodeblock %}
### Getting Sublists with Slices
A slice is typed between square brackets,like an index,but it has two integers separated by a colon.Notice the difference between indexes and slices.
{% codeblock %}
spam = ['cat','bat','rat','elephant']
spam[0:1]
['cat','bat']
{% endcodeblock %}
### Getting a list's length with len()

spam = ['cat','bat','rat','elephant']
len(spam)
>>>3
len can return the number of values that are in a list value passed to it.
### List Concatenation and list Replication
[1,2,3]+['a','b','c']
[1,2,3,'a','b','c']
### Removing Values from Lists with del statement

spam = ['cat','bat','rat','elephant']
def spam[2] # 'rat' is deleted

