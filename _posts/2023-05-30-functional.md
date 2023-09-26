---
layout: post
title: "About compactness and an incursion into factorizing operators"
description: "Brief commented exposition about some main Theorems regarding compactness in general spaces. Application of some ideas to the context of operator theory."
comments: false
keywords: "operator ideals, compact sets"
---

I always recall this anecdote while I was starting getting into Functional Analysis. 
[Vanessa](https://people.math.rochester.edu/grads/vmatusde/) (great student, friend, and TA) always had this strong *geometrical* intuition. So when we were introduced to Riesz's Lemma, she always highlighted its strange nature.
It implies the closed unit ball of a normed vector space (NVS) is not compact, despite being closed and bounded.
She used to do this gesture with her hand *à la [right-hand rule](https://en.wikipedia.org/wiki/Right-hand_rule)* for showing us that the set is *small*.

It took me a while to learn to visualize this in a different way.
The first part of my exposition is to present different visualizations, where the **true smallness** of the set is evident.

I deviated from this topic.
This conversation sparked my devotion for Functional Analysis, and its techniques.

# Small sets in small settings...

The modern definition of compact set is due to Alexandrof and Urysohn.
Nevertheless, there were great mathematicians working towards unraveling the meaning of compacness.
Big names involve Borel, Heine, Weierstrass, Bolzano...

The main idea is the following: compact sets are equivalent to sequentially compact set, and they are the same as *closed and bounded* sets.
We know this will break on infinite dimensions. 

# Small sets in big settings... and tight distances!

One cool thing about Banach spaces is their *embeddability* into spaces of continuous functions.
Given \(X\) a Banach space, consider \\(B_{X^*}\\) to be the the unit ball of the dual of \\(X\\).
Then \\(\Phi: X \to C(B_{X^*}\\), where \\(\Phi(x)(x^*) = x^*(x)\\).

We can do better if \\(X^*\\) is separable.
We can provide a metric to \\(B_{X^*}\)).

*I will continue this post in a next post...*
