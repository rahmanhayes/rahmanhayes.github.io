---
layout: post
title:  "Parsing an XML file in Python"
date:   2014-05-24 
categories: python 
---

This is an example of Parsing an XML File in Python using the xml module

Edit the file pythonparsexml.py
Add import command from the ElementTree object:

{% highlight ruby %}
from xml.etree import ElementTree
{% endhighlight%}

The xml file that will be used in this example is called "pokemon.xml". In the python script this will be opened and the function ElementTree.parse will parse the file:

{% highlight ruby %}
with open ("pokemon.xml") as f:
    doc = ElementTree.parse(f)
{% endhighlight%}

Add the 'row' element with the 'findall' function:


{% highlight ruby %}
for node in doc.findall('row'):
    print("")
    print("id: {0}".format(node.find('id').text))
    print("typeTwo: {0}".format(node.find('typeTwo').text))
    print("name: {0}".format(node.find('name').text))
    print("type: {0}".format(node.find('type').text))
{% endhighlight%}

*When this is run it will output the following:*

{% highlight ruby %}
$ python pythonparsexml.py
id:  001
typeTwo:  Poison
name:  Bulbasaur
type:  Grass

id:  002
typeTwo:  Poison
name:  Ivysaur
type:  Grass

id:  003
typeTwo:  Poison
name:  Venusaur
type:  Grass

id:  006
typeTwo:  Flying
name:  Charizard
type:  Fire

id:  012
typeTwo:  Flying
name:  Butterfree
type:  Bug

id:  013
typeTwo:  Poison
name:  Weedle
type:  Bug

id:  014
typeTwo:  Poison
name:  Kakuna
type:  Bug

id:  015
typeTwo:  Poison
name:  Beedrill
type:  Bug

id:  016
typeTwo:  Flying
name:  Pidgey
type:  Normal

id:  017
typeTwo:  Flying
name:  Pidgeotto
type:  Normal

id:  018
typeTwo:  Flying
name:  Pidgeot
type:  Normal
{% endhighlight%}

