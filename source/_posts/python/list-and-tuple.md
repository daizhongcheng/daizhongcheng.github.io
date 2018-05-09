---
title: list and tuple
comments: false
mathjax: true
long: python
date: 2018-05-07 22:32:34
tags:
categories:
- python
---
#### list 数据类型
python的一种数据类型是列表：list它是一个有序的集合，可以随时添加和删除其中的元素。
比如：列出自己的课程，就可以用list表示：
> \>\>\> vorlesungen = ['math','SPE','FDI']

变量`vorlesungen`就是一个list,用`len()`函数可以获得list函数的个数：

> \>\>\> len(vorlesungen) 
> \>\>\> 3

用索引可以访问list中的每一个位置的元素，记得索引是从`0`开始的：

> \>\>\> vorlesungen[0]
> \>\>\> 'math'

`list`添加无素
*.append()命令可以添加元素，在列数最末尾追加。

> \>\>\> vorlesungen.append('mehrg')

.insert(i,'*****')可以在任意位置添加元素。

> \>\>\> vorlesungen.insert(2,'pr')

要删除list末尾的元素，用`pop()`命令

> \>\>\> vorlesungen.pop()

要删除指定的位置元素，用`pop()`的方法，其中`i`是索引位置。


> \>\>\> vorlesungen.pop(i)

可以用`len()`命令计算元数个数。

> \>\>\> len(vorlesungen)

#### tuple 数据类型


> \>\>\> vorl=('a','b','c')

注意：如果定义一个1个元素的tuple，需要加入逗号

> \>\>\> t=(1,)

tuple的元素不能更改。


