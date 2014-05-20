---
layout: post
title:  "Python Unit Test"
date:   2014-05-19 
categories: jekyll update
---

As python pratice, I decided to follow one of the tutorials on Tuts for Unit Testing in Python:  [Tuts] (http://code.tutsplus.com/tutorials/beginning-test-driven-development-in-python--net-30137)

This is a code that introduces unit testing in Python. From David Sale's post, the main methods in Python's Unit Testing is:

- assert - base assert allowing you to write your own assertions
- assertEqual(a, b) - check a and b are equal
- assertNotEqual(a, b) - check a and b are not equal
- assertIn(a, b) - check that a is in the item b
- assertNotIn(a, b) - check that a is not in the item b
- assertFalse(a) - check that the value of a is False
- assertTrue(a)- check that the value of a is True
- assertIsInstance(a, TYPE) - check that a is of type "TYPE"
- assertRaises(ERROR,a,args) - check that when a is called with args that it raises ERROR.



The following tutorial involves writing a calculator class, with add, subtract and other methods.
Below is an add function which determines the sum of two numbers and returns the output. Below is the failing test:

This will be called: calculator_tests.py

{% highlight ruby %}
import unittest

class TddInPythonExample(unittest.TestCase):

    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result = calc.add(2,2)
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
F
======================================================================
FAIL: test_calculator_add_method_returns_correct_result (__main__.TddInPythonExample)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "calculator_tests.py", line 10, in test_calculator_add_method_returns_correct_result
    self.assertEqual(4, result)
AssertionError: 4 != None

----------------------------------------------------------------------
Ran 1 test in 0.001s

FAILED (failures=1)

{% endhighlight %}

Fix the method and see if our test passes now: 

{% highlight ruby %}
class Calculator(object):
 
    def add(self, x, y):
        return x+y
{% endhighlight ruby %}

- Final code:

{% highlight ruby %}

class Calculator(object):
    def add(self, x, y):
        return x+y

import unittest
class TddInPythonExample(unittest.TestCase):
    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result = calc.add(2,2)
        self.assertEqual(4, result)

if __name__ == "__main__":
    unittest.main()
{% endhighlight %}

- Run from the Command line:

{% highlight ruby %}
$ python calculator_tests.py
.
----------------------------------------------------------------------
Ran 1 test in 0.001s

OK

{% endhighlight %}


- Test to add anything other than numbers. Using the assertRaises to test.
This test is a failing test:


{% highlight ruby %}
import unittest
from calculator import Calculator

class TddInPythonExample(unittest.TestCase):

    def test_calculator_add_method_returns_correct_result(self):
        calc = Calculator()
        result = calc.add(2,2)
        self.assertEqual(4, result)

    def test_calculator_returns_error_message_if_both_args_not_number(self):
        self.assertRaises(ValueError, self.calc.add, 'two', 'three')
{% endhighlight %}
 

- Run the calculator_test.py from the command line:


{% highlight ruby %}
{% endhighlight %}



