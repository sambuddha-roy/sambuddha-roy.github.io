---
layout: post
title:  "Regexes for keyphrase extraction"
date:   2019-11-29 18:30:15 -0800
categories: jekyll update
---
In this post, we are going to discuss some common code snippets used in extracting phrases out of text. 
Alternative possibilities exist (for instance using spaCy and tokenization); for this post, we will be using
the popular re package of Python. 

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
