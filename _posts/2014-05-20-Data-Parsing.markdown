---
layout: post
title:  "Data Parsing"
date:   2014-05-20 
categories: Python
---

Using python to parse through text. The re module is used to implement regular expressions into Python:

Example Email verification:

The function (search) scans through a string and will search for any location where the regex might match:

{% highlight ruby %}
result = re.search('([\w.-]+)@([\w.-]+)', myString)
{% endhighlight%}


The function group() helps to return the string matched by the regex. 


The pattern \w matches any alphanumeric character and is equivalent to the class (a-z, A-Z, 0-9_).



Example:


{% highlight ruby %}
import re

myString = 'From: rjarmand@yahoo.com (Rahmans email)'
result = re.search('([\w.-]+)@([\w.-]+)', myString)
if result:
    print (result.group(0))
    print (result.group(1))
    print (result.group(2))
{% endhighlight %}


Run on the command line:


{% highlight ruby %}
$ python textparsing.py
rjarmand@yahoo.com
rjarmand
yahoo.com
{% endhighlight %}


Reference: "Practical Data Analysis" By Hector Cuesta

