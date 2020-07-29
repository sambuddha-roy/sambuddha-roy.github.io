---
layout: post
title:  "Mixture of h-1 heads vs. h heads - ACL 2020"
date:   2020-07-28 18:30:15 -0800
categories: jekyll update
---

What follows are some short notes on the paper on the [mixture of h-1 heads vs. h heads](https://www.aclweb.org/anthology/2020.acl-main.587/).

**Overall theme**

Usually in the transformer architecture we use multiple heads. Are all of these
necessary?

Earlier papers have indicated that the architecture is overparametrized, not all of
the heads might be necessary.

This paper keeps all the heads, but instead of mixing the heads uniformly, inserts a
layer that learns the right _mixture_ of the heads. 


## References:
1. [h-1 heads, ACL 2020](https://www.aclweb.org/anthology/2020.acl-main.587/)
2. [programmersought blog article](https://www.programmersought.com/article/85534594552/)
