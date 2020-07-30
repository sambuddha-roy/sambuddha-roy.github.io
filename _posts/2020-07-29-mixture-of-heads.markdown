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

What is mostly important to follow in this paper is the transition from the usual
aggregation of heads in a transformer to what this paper does.

Usual aggregation:
Given the head outputs `H_1, H_2, ..., H_h` the vanilla transformer uses a matrix `W`
to aggregate these head outputs.

### Main questions
* Surprise 1: we would have made each individual head `H_i` as an expert. Instead here,
each expert corresponds to `h-1` heads, so that every two experts "share" `h-2` heads.
Why is this?
* Surprise 2: The sampling step in the F-step. We use the relative importances/weights of the
experts (the `g` values) and then we _sample_ using these weights. We choose _only_ the
expert chosen by this process to update weights in this round.
Is this why we choose an expert to be a selection of `h-1` heads? So that across
different experts (and their updates) there is some sharing of weights; so that in
different rounds, we are not updating entirely different sets of weights. 



## References:
1. [h-1 heads, ACL 2020](https://www.aclweb.org/anthology/2020.acl-main.587/)
2. [programmersought blog article](https://www.programmersought.com/article/85534594552/)
