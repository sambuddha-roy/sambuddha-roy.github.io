---
layout: post
title:  "Regexes for keyphrase extraction"
date:   2019-11-29 18:30:15 -0800
categories: jekyll update
---
In this post, we are going to discuss some common code snippets used in extracting phrases out of text. 
Alternative possibilities exist (for instance using spaCy and tokenization); for this post, we will be using
the popular re package of Python. 

There are four main functions in the [re module](https://github.com/python/cpython/blob/3.8/Lib/re.py): 
match, search, findall and finditer (there are many other interesting functions such as sub, subn - for 
details look at the [source code](https://github.com/python/cpython/blob/3.8/Lib/re.py)).

The function findall gives 
us all the matches of the _pattern_ in the actual _string_, but it is the function finditer that also gives us
the _spans_ of the matches. This is often necessary in actual work, where we want to modify the spans (say, we want
to create a HTML span where the span of the _pattern_ is highlighted). 

Sample code snippet:

{% highlight python %}
import re
def extract_kp_from_sentence(kp, sentence):
   pattern = r'\b' + kp + r'\b'
   for match in re.finditer(pattern, sentence):
   	  print(match.span())
{% endhighlight %}

# References:
1. [Tutorial on regexes on google.developer.com](https://developers.google.com/edu/python/regular-expressions)
2. [Another tutorial on Python regexes](https://www.guru99.com/python-regular-expressions-complete-tutorial.html)
