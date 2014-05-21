---
layout: post
title:  "Parsing CSV File in Python"
date:   2014-05-21 
categories: Python
---

Using python to parse through a CSV file. The csv module is used to parse a csv file.
Example taken from "Practical Data Analysis" By Hector Cuesta

Example:

CSV Data

{% highlight ruby %}
id, typeTwo, name, type
001, Poison, Bulbasaur, Grass
002, Poison, Ivysaur, Grass
003, Poison, Venusaur, Grass
006, Flying, Charizard, Fire
012, Flying, Butterfree, Bug
013, Poison, Weedle, Bug
014, Poison, Kakuna, Bug
015, Poison, Beedrill, Bug
{% endhighlight %}


Code in python looks like:

{% highlight ruby %}
import csv

with open("pokemon.csv") as f:
    data = csv.reader(f)
    for line in data:
        print(" id: {0} , typeTwo: {1}, name:  {2}, type: {3}"
              .format(line[0],line[1],line[2],line[3]))
{% endhighlight %}


When run from the command line, the following is printed: 

{% highlight ruby %}
$ python csv_parse.py
 id: id , typeTwo: typeTwo, name:  name, type: type
 id:  001 , typeTwo:  Poison, name:   Bulbasaur, type:  Grass
 id:  002 , typeTwo:  Poison, name:   Ivysaur, type:  Grass
 id:  003 , typeTwo:  Poison, name:   Venusaur, type:  Grass
 id:  006 , typeTwo:  Flying, name:   Charizard, type:  Fire
 id:  012 , typeTwo:  Flying, name:   Butterfree, type:  Bug
 id:  013 , typeTwo:  Poison, name:   Weedle, type:  Bug
 id:  014 , typeTwo:  Poison, name:   Kakuna, type:  Bug
 id:  015 , typeTwo:  Poison, name:   Beedrill, type:  Bug
 id:  016 , typeTwo:  Flying, name:   Pidgey, type:  Normal
 id:  017 , typeTwo:  Flying, name:   Pidgeotto, type:  Normal
...........
{% endhighlight %}


Reference: "Practical Data Analysis" By Hector Cuesta
