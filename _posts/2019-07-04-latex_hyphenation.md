---
layout: post
lang: en
ref: blogpost
comments: true
title: LaTeX hyphenation
author: joao
excerpt: How to not hyphenate proper names
---

Quick post.  
Today I found a very interesting LaTeX command. Setting

```tex
\uchyph=0
```

will tell LaTeX to *not* hyphenate upper-case words.

This is quite helpful with proper names like Keplerian, Bayesian, João, etc.
If I'm not mistaken, you can set this in either the preamble or in the document itself.

One drawback is that it will likely not work if you're writing German (the language, not the word).

In the process, I also (re)discovered the [TeX FAQ website](https://texfaq.org/),
which is nothing less than absolutely amazing.


That's it for today!