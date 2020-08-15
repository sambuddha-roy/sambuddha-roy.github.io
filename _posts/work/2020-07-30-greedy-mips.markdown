---
layout: post
title:  "Greedy MIPS paper"
date:   2020-07-28 18:30:15 -0800
categories: jekyll update
---

### Main Idea
The basic problem is the _Maximum Inner Product Search_ (MIPS) problem: given a vector `q`, and a collection
of candidate vectors `h_1, h_2, ..., h_n`, find out the candidates (top-k) that have the largest
inner products `<w, h_i>`.

Important dimensions: there are
* `n` vectors
* each vector (including the query `q`) has dimension `k`.

Thus, a naive linear search will use `nk` operations to compute the inner products, followed by a sorting operation that takes
`n log n` time.

Overall goal is to improve on this, maybe with an approximation to the MIPS problem.
(One version the authors mention is _budgeted_ MIPS where there is a budget on the total
  number of inner products that are allowed.)

### Related Literature
The MIPS problem has seen a recent surge of interest, with solutions that involve a _reduction_ to
the _Nearest Neighbor Search_ (NNS) problem, as also _sampling_ based approaches.

**Reduction to NNS**

Let us consider the MIPS problem where we are trying to find only the _top_ candidate.



### References

* [greedy mips paper, neurips 2017](https://papers.nips.cc/paper/7129-a-greedy-approach-for-budgeted-maximum-inner-product-search.pdf)
  * [code by rofuyu](https://github.com/rofuyu/exp-gmips-nips17)
