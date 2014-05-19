---
layout: post
title:  "Python Unit Test"
date:   2014-05-19 
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

I found that I needed to add if __name__ == "__main__" to get the test to run:


{% highlight ruby %}
if __name__ == "__main__":
    unittest.main()
{% endhighlight %}

Running the test:

{% highlight ruby %}
$ python calculator_tests.py 
E
======================================================================
ERROR: test_calculator_add_method_returns_correct_result (__main__.TddInPythonExample)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "calculator_tests.py", line 4, in test_calculator_add_method_returns_correct_result
    calc = Calculator()
NameError: global name 'Calculator' is not defined

----------------------------------------------------------------------
Ran 1 test in 0.002s
{% endhighlight %}

The test fails because "Calculator" is not defined. 
Adding the "Calculator" below to calculator.py

{% highlight ruby %}
class Calculator(object):
    def add(self, x, y):
        pass

import unittest
class TddInPythonExample(unittest.TestCase):
    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result - calc.add(2,2)
        self.assertEqual(4, result)

if __name__ == "__main__":
    unittest.main()
{% endhighlight %}

Run the test again:

{% highlight ruby %}
$ python calculator_tests.py 
E
======================================================================
ERROR: test_calculator_add_method_returns_correct_result (__main__.TddInPythonExample)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "calculator_tests.py", line 9, in test_calculator_add_method_returns_correct_result
    result - calc.add(2,2)
NameError: global name 'result' is not defined

----------------------------------------------------------------------
Ran 1 test in 0.002s

FAILED (errors=1)
{% endhighlight %}






[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
