---
layout: post
title:  "Installing a Virtual Environment for Python"
date:   2014-05-28 
categories: python 
---

When I am working in Python, I tend to install various modules depending on the project. While reading the stacktrace forum, I found that having a clean environment is helpful when going from one project to another. Python has a virtual environment that can be used to keep a clean and organized Python environment.

### Install the virtualenv tool via pip:

{% highlight ruby %}
pip install virtualenv
{% endhighlight%}

* This command did not work on cygwin. Using the easy_setup.py to install virtualenv for python:

{% highlight ruby %}
$ wget http://peak.telecommunity.com/dist/ez_setup.py | python
{% endhighlight%}

* Use easy_install to install the virtualenv

{% highlight ruby %}
$ easy_install virtualenv
Searching for virtualenv
Reading http://pypi.python.org/simple/virtualenv/
Best match: virtualenv 1.11.6
Downloading https://pypi.python.org/packages/source/v/virtualenv/virtualenv-1.11.6.tar.gz#md5=f61cdd983d2c4e6aeabb70b1060d6f49
Processing virtualenv-1.11.6.tar.gz
Writing /tmp/easy_install-6YIwbk/virtualenv-1.11.6/setup.cfg
Running virtualenv-1.11.6/setup.py -q bdist_egg --dist-dir /tmp/easy_install-6YIwbk/virtualenv-1.11.6/egg-dist-tmp-TEZCBb
warning: no previously-included files matching '*' found under directory 'docs/_templates'
warning: no previously-included files matching '*' found under directory 'docs/_build'
Adding virtualenv 1.11.6 to easy-install.pth file
Installing virtualenv script to /usr/bin
Installing virtualenv-2.7 script to /usr/bin

Installed /usr/lib/python2.7/site-packages/virtualenv-1.11.6-py2.7.egg
Processing dependencies for virtualenv
Finished processing dependencies for virtualenv
{% endhighlight%}

### Basic Usage:

* Create a virtual environment:


{% highlight ruby %}
$ virtualenv venv
New python executable in venv/bin/python2.7
Also creating executable in venv/bin/python
Installing setuptools, pip...done.
{% endhighlight%}

* Use new environment:

{% highlight ruby %}
$ source venv/bin/activate
(venv)
{% endhighlight%}

* A new folder has been created for this virtual environment:

{% highlight ruby %}
$ ll venv
total 8
drwxr-xr-x+ 1 rhayes 0 May 28 15:47 .
drwxr-xr-x+ 1 rhayes 0 May 28 15:55 ..
drwxr-xr-x+ 1 rhayes 0 May 28 15:47 bin
drwxr-xr-x+ 1 rhayes 0 May 28 15:47 include
drwxr-xr-x+ 1 rhayes 0 May 28 15:47 lib
(venv)
{% endhighlight%}


### References: 
[http://docs.python-guide.org/en/latest/dev/virtualenvs/](http://docs.python-guide.org/en/latest/dev/virtualenvs/)
