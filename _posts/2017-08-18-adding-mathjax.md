---
layout: post
title:  Adding MathJax!
---

# Blog posts get math equations :)

I've been wanting to learn [![LaTeX](https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/LaTeX_logo.svg/100px-LaTeX_logo.svg.png)](https://www.latex-project.org/about/) for a while now. It seems to be the de facto standard for the [STEM](https://en.wikipedia.org/wiki/Science,_technology,_engineering,_and_mathematics) fields. Honestly, I find it weird that a typesetting system is so popular for writing in. Some view its dogmatic use in the sciences as a [fetish](http://www.danielallington.net/2016/09/the-latex-fetish/). For publishing styled content quickly, I prefer [markdown](https://en.wikipedia.org/wiki/Markdown). In fact, this blog is powered by [![Jekyll]({{site.url}}/assets/img/jekyll.png)](https://jekyllrb.com/)

[Jekyll](http://jekyllrb.com/) allows me to write my posts in markdown and then converts them into html. Alas, LaTeX can't be ignored. During my search for LaTeX tutorials, material and documentation, I came across [ShareLaTeX](https://www.sharelatex.com)

[![ShareLaTeX](https://cdn.sharelatex.com/img/brand/logo-horizontal.svg)](https://www.sharelatex.com)

[ShareLaTeX](https://www.sharelatex.com) is a web app for collaborative LaTex editing. Pretty cool! You still have to compile after edits, but you don't have to install any additional software (texlive, texmaker etc..) or configure your environment. Plus, you have access to a bunch of free templates.

Now what if I wanted to have math equations in my blog posts?...something like LaTeX in markdown?...Enter a Javascript display engine fully compatible with Jekyll via:

[![MathJax](https://upload.wikimedia.org/wikipedia/en/thumb/5/5f/MathJax.svg/128px-MathJax.svg.png)](https://www.mathjax.org/)

## With [MathJax](https://www.mathjax.org/) I can blab on about the Pythagorean theorem in style:

$$a^2 + b^2 = c^2$$

#### Best of all, professor Farnsworth approves:

![Excellent](https://media.giphy.com/media/96N4qqW1JvL0c/giphy.gif)