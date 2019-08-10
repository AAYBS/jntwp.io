# Jupyter Notebooks To Web Page starter

[![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ZoranPandovski/qtp.io/blob/master/notebooks/VIX_blend.ipynb)

This repository contains a boilerplate for:

* Converting [Jupyter notebooks](https://jupyter.org/) to markdown or html
* Push them to static site generator ([Pelican](http://docs.getpelican.com/en/3.6.3/index.html))
* Deploy the site on [GitHub pages](https://pages.github.com/) 

# Installation

To install:

1.Clone this repository:
```
git clone git@github.com:ZoranPandovski/qtp.io.git
```
2.Create virtual environment and activate it:
```
python3 -m venv qtp
source qtp/bin/activate
```
3.Install Python packages into your virtual environment: 
```
pip install -r requirements.txt
```
# Development

All of the jupyter notebooks that should be converted to pages must be inside `notebooks` directory. 

## Converting notebooks 

Use nbconvert to convert a Jupyter notebook (input) to a a different format (output). The basic command structure is:

```
jupyter nbconvert --to <output format> <input notebook>
```
The current setup uses markdown so run:

```
jupyter nbconvert --to markdown notebooks/mynotebook.ipynb /content
```

## Markdown structure

> Note: Each markdown file must have:
> * Title: My First Review
> * Date: 2010-12-03 10:20
> * Category: Review

## Publish to gihub pages

To publish a Pelican site as a Project Page you need to push the content of the output dir generated by Pelican to a repository’s gh-pages branch on GitHub.

```
pelican content -o output -s pelicanconf.py
ghp-import output
```
Then push to gh-pages branch:
```
git push origin gh-pages
```
