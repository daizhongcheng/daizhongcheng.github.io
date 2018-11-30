---
title: Creating Regex Objects
comments: true
mathjax: true
date: 2018-11-18 17:17:14
long:
tags:
categories: python
---
### Regex Objects
All the regex function in python are in the 're' module.Enter the following into the interactive shell to import this module:
{% codeblock %}
import re
phoneNumRegex = re.compile(r'(\(\d\d\d\))(\d\d\d-\d\d\d\d)')
mo = phoneNumRegex.search('My phone number is (415) 555-4242.')
mo.group(1)
mo.group(2)
'555-4242'

{% endcodeblock %}
### Matching Multiple Groups with the Pipe
{% codeblock %}
batRegex = re.compile(r'Bat(man|mobile|copter|bat)')
mo = batRegex.search('Batmobile lost a wheel')
mo.group()
'Batmobile'
mo.group(1)
'mobile'
{% endcodeblock %}

