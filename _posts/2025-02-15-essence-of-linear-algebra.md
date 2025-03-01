---
title: 'Basics of Linear Algebra'
date: 2025-02-15
permalink: /posts/2012/08/blog-post-1/
tags:
  - Linear Algebra
---


### A linear map from a finite-dimensional space is always continuous  

Let \\( X \\) and \\( Y \\) be two normed spaces and \\( f: X \to Y \\) a linear map from \\( X \\) to \\( Y \\).  
If \\( X \\) is [finite-dimensional](https://en.wikipedia.org/wiki/Finite-dimensional_vector_space),  
choose a basis \\( (e_1, e_2, \dots, e_n) \\) in \\( X \\) which may be taken to be unit vectors. Then,  

$$
f(x) = \sum_{i=1}^{n} x_i f(e_i),
$$  

and so by the [triangle inequality](https://en.wikipedia.org/wiki/Triangle_inequality),  

$$
\| f(x) \| = \left\| \sum_{i=1}^{n} x_i f(e_i) \right\|  
\leq \sum_{i=1}^{n} |x_i| \| f(e_i) \|.
$$  

Letting  

$$
M = \sup_i \{ \| f(e_i) \| \},
$$  

and using the fact that  

$$
\sum_{i=1}^{n} |x_i| \leq C \| x \|
$$  

for some \\( C > 0 \\), which follows from the fact that  
[any two norms on a finite-dimensional space are equivalent](https://en.wikipedia.org/wiki/Norm_equivalence),  
one finds  

$$
\| f(x) \| \leq \left( \sum_{i=1}^{n} |x_i| \right) M \leq CM \| x \|.
$$  

Thus, \\( f \\) is a **bounded linear operator** and so is **continuous**.  
In fact, to see this, simply note that \\( f \\) is linear, and therefore  

$$
\| f(x) - f(x') \| = \| f(x - x') \| \leq K \| x - x' \|
$$  

for some universal constant \\( K \\). Thus for any \\( \epsilon > 0 \\),  
we can choose \\( \delta \leq \epsilon / K \\) so that  
\\( f(B(x, \delta)) \subseteq B(f(x), \epsilon) \\).  
Here, \\( B(x, \delta) \\) and \\( B(f(x), \epsilon) \\) are the normed balls around \\( x \\) and \\( f(x) \\),  
which gives continuity.
