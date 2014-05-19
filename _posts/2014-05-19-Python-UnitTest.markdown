---
layout: post
title:  "Python Unit Test"
date:   2014-05-18 
categories: jekyll update
---

As python pratice, I decided to follow one of the tutorials on Tuts for Unit Testing in Python: http://code.tutsplus.com/tutorials/beginning-test-driven-development-in-python--net-30137

This is a code that introduces unit testing in Python.
This involves writing a calculator class, with add, subtract and other methods.
Below is an add function which determines the sum of two numbers and returns the output. Below is the failing test:

This will be called: calculator_tests.py

{% highlight ruby %}
import unittest

class TddInPythonExample(unittest.TestCase):

    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result - calc.add(2,2)
        self.assertEqual(4, result)
{% endhighlight %}


{% highlight ruby %}
import unittest
class TddInPythonExample(unittest.TestCase):
    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result - calc.add(2,2)
        self.assertEqual(4, result)

if __name__ == "__main__":
    unittest.main()
{% endhighlight %}



[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
