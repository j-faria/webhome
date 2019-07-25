---
layout: post
lang: en
ref: blogpost
comments: true
title: Regex to find repeated words &nbsp;&nbsp;&nbsp;
author: joao
excerpt: How to find "the the"s
---

Even quicker post than the last one.

For some reason, a lot of times I end up writing "the the" and "show show" and
the like.  
I have no idea why this happens, but I usually say it's because I'm left-handed
and cover the last word as I'm writing. Of course, this doesn't make any sense
since I'm writing on a keyboard, but you know know...

Anyway, here's a regular expression to find those repeated words, 
[courtesy of stack overflow](https://stackoverflow.com/a/2823037/1352183).

```sh
\b(\w+)\s+\1\b
```


