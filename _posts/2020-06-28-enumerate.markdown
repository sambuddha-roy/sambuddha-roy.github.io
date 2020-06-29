---
layout: post
title:  "Modifying a list while in enumerate"
date:   2020-06-28 18:30:15 -0800
categories: jekyll update
---
In this post, we will understand what happens 
when we modify a list inside a `for` loop, where
the `for` loop essentially loops over the list 
itself. 

The problem that we will tackle is the following:
Suppose you are given a list of string tokens. Now, some 
of the string tokens may include _apostrophes_: and in such a case
we want to merge those apostrophes with the tokens 
appearing immediately before. 

As an example, a list of tokens `["I", "don", "'t", "want", "to", "go"]`
should be converted to `["I", "don't", "want", "to", "go"]`.

We abstract out the essence of this problem as the following:

**Problem**:
We are given a `special` string (call it `x`), and a list of
strings. Traverse the list of strings; if the special
string appears at a position, then merge it with the 
string at the _previous_ position. Output this
modified list of strings.

One key assumption that we will make (as is also 
reasonable to make for the original setting of the problem)
is that the appearances of the special string in the list of
string is _non-consecutive_. 

Given this, here is a sample implementation in Python:

{% highlight python %}
def process_list(special, input_list):
    rev_input_list = input_list[::-1]

    for idx, item in enumerate(rev_input_list):
        if item == special:
            if idx + 1 < len(rev_input_list):
                rev_input_list[idx+1] = rev_input_list[idx + 1] + special
                rev_input_list.pop(idx)
                
    output_list = rev_input_list[::-1]
    return output_list
{% endhighlight %}

A sample run:

{% highlight python %}
special = "b"
input_list = ["a", "bc", "b", "d",  "c",  "b"]

output_list = ['a', 'bcb', 'd', 'cb']
assert process_list(special, input_list) == output_list
{% endhighlight %}
