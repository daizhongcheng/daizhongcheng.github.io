---
title: backslash python3
comments: true
mathjax: true
date: 2018-05-03 14:12:17
tags:
categories: python
---
#### practice
{% codeblock %}
tabby_cat = "\tI'm tabbed in."
persian_cat = "I'm split\non a line."
backslash_cat = "I'm \\a \\ cat."
print(tabby_cat)
print(persian_cat)
print(backslash_cat)
{% endcodeblock %}

Escape  what it does
{% codeblock %}
\\      Backslash \
\'      single-quote '
\"      double-quote "
\a 	Ascii bell
\b 	Ascii backspace
\f 	Ascii formfeed
\n	Ascii linefeed
\N{} 	Character named name in the Unicode database
\r	Ascii carriage return
\t	Ascii horizontal tab
\uxxxx  Character with 16-bit hex value xxxx
\v 	Ascii vertical tab
\ooo 	Character with octal value oo
\xhh 	Character with hex value hh
{% endcodeblock %}

