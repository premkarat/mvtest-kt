mvtest documentation is hosted using [github pages](https://montavista-opensourcetechnology.github.io/mvtest/home.html)

####Documentation 101:

Two possible ways to generate documentation from plain text is to use 

 * **markdown (md)** - [a primer on markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)  
    or  
 * **reStructuredText (rst)** - [a primer on rst](http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html)

mvtest uses [Sphinx](http://www.sphinx-doc.org/en/stable    /) for HTML documentation generation, which is based on **restructuredText(rst)** and it automatically document our tests and APIs using [autofunction](http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html#auto-document-your-python-code). So to document the tests and APIs, all you have to do is to use [python docstrings](https://www.python.org/dev/peps/pep-0257/) in the tests & APIs (modules, functions, classes, and methods)

Here is an [example on how to document python docstrings](http://thomas-cokelaer.info/tutorials/sphinx/docstring_python.html
)

**Markdown** is best suited for writing for the web where as **reStructuredText(rst)** is best suite for writing techincal documentation.

Here is an [interesting read on markdown vs rst](http://zverovich.net/2016/06/16/rst-vs-markdown.html)

[Github pages](https://pages.github.com/) supports [Jekyll](https://help.github.com/articles/using-jekyll-as-a-static-site-generator-with-github-pages/) for documentation generaton. Jekyll supports Markdown format. Since mvtest uses Sphinx(rst format) for doc generation, this [wonderful blog](http://daler.github.io/sphinxdoc-test/includeme.html) helped us to publish Sphinx generated docs on github.

####mvtest document setup

mvtest doc setup involved following steps  
 1. [setting up mvtest repo](http://daler.github.io/sphinxdoc-test/includeme.html#set-up-main-repository)  
 2. [setting up sphinx in mvtest repo](http://daler.github.io/sphinxdoc-test/includeme.html#set-up-sphinx-within-main-repository)  
 3. [setting up mvtestdocs repo](http://daler.github.io/sphinxdoc-test/includeme.html#set-up-separate-docs-repository)  
 4. [Makefile changes](http://daler.github.io/sphinxdoc-test/includeme.html#makefile-changes)  
 5. [Defining documentation structure](http://www.sphinx-doc.org/en/stable/tutorial.html#defining-document-structure)  
 6. [Automatic document generation using autodoc](http://www.sphinx-doc.org/en/stable/tutorial.html#autodoc)

####mvtest document generation workflow

**Steps to be followed in mvtest repo**

* Add test function (**def test_**) in test module (**test_xx.py**) or APIs (**apis/xxx.py**) in [mvtest repo](https://github.com/MontaVista-OpenSourceTechnology/mvtest.git) and ensure it has [python docstrings](https://www.python.org/dev/peps/pep-0257/) as per [rst format](http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html)
* If the test or API module already exits as an **automodule** directive in **test.rst** or **apis.rst** file, then any new test function or API function with docstrings will automatically be included in the documentation.

* If the test or API module is new, then use the [autodoc mechanism](https://github.com/MontaVista-OpenSourceTechnology/mvtest.git) and **automodule directive** to add the module in test.rst or apis.rst file found under **docs/** folder. For example to add the **utils.py** API module, the following automodule directive was used in [apis.rst](https://raw.githubusercontent.com/MontaVista-OpenSourceTechnology/mvtest/master/docs/apis.rst)

```python
   utils
   -----

   .. automodule:: apis.utils
       :members:
```
* Run git add .

* Run git commit

* cd docs

* make html

* git push origin master

**Steps to be followed in mvtestdocs repo**

* cd html

* git branch (to ensure you are in gh-pages branch)

* git add .

* git commit

* git push origin gh-pages
