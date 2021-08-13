Documentation for Marine Benchmark API and Webplatform.


Built using [Sphinx](https://www.sphinx-doc.org/en/master/) and [Read the Docs theme](https://github.com/readthedocs/sphinx_rtd_theme). 

Requires:
 * sphinx 1.8.4
 * sphinx-rtd-theme 0.4.3



Enables continous documenation by updating corresponding .rst files and resources in _static. 

```
make hmtl
```

under \docs builds the site in _build. A makefile for windows is also included. 

When pushing into master - Github Actions will automatically launch and update *gh-pages* branch using the script in buildDocs.sh. 

Hosted on Github pages using guide from [Michael Altfield](https://tech.michaelaltfield.net/2020/07/18/sphinx-rtd-github-pages-1/)
