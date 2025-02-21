---
title: 'Introduction to Embedded Geometry'
date: 2025-02-17
permalink: /posts/2025/02/blog-post-2/
tags:
  - Differential Geometry
---

The post is meant as an introduction to the theory of submanifolds. The crux of of the matter will be the following: certain sets can be linearized in a meaningful way around each of its points. To make this idea concrete we will consider the sphere, \\(\mathcal{S}^{d-1}\\), that is the set of vectors in \\(\mathbb{R}^d\\) satistyfing

$$
h(x)= x^Tx-1 = 0.
$$

We refer to \\(h\\) as the defining equation. To obtain a linearization around each point we differentiate the defining equation, or rather, consider a truncated Taylor expansion of it:

$$
h(x+tv) = h(x) + tDh(x)[v] + O(t^2) 

$$

Now, with \\(x\in \mathcal{S}^{d-1}\\) we have \\(h(x)=0\\). If we want to "force" \\(x + tv\in \mathcal{S}^{d-1}\\), clearly we must have \\(Dh(x)[v]=0\\), in other words \\(v\in \operatorname{ker}(Dh(x))\\). If this is the case, then \\(h(x + tv) = O(t^2)\\) meaning it almost satifies the defining equation for small \\(t\\). Hence, the subspace \\(\operatorname{ker}(Dh(x))\\) is the logical candidate to consider as the linearization of \\(\mathcal{S}^{d-1}\\) at \\(x\\).


\[
Dh(x)[v] = \lim_{t \to 0} \frac{h(x + tv) - h(x)}{t} = x^\top v + v^\top x = 2x^\top v,
\]

the kernel of \(Dh(x)\) is the subspace orthogonal to \(x\) in \(\mathbb{R}^d\) (with respect to the usual inner product). 

At first, one might think that if a set is defined by an equation of the form \( h(x) = 0 \) with some smooth function \( h \), then that set is smooth and can be linearized by the kernels of \( Dh \). However, this is not the case. Indeed, consider the following example in \(\mathbb{R}^2\), :

\[
\mathcal{X} = \{ x \in \mathbb{R}^2 : h(x) = x_1^2 - x_2^2 = 0 \}.
\]

The defining function \( h \) is smooth, yet the set \( \mathcal{X} \) is a cross in the plane formed by the union of the lines \( x_1 = x_2 \) and \( x_1 = -x_2 \). We want to exclude such sets because of the kink at the origin. What went wrong with it? If we blindly use the kernel of the differential to linearize \( \mathcal{X} \). As \(h\colon \mathbb{R}^2 \to \mathbb{R}\), the total derivative/ Jacobian is given by the \(1\times 2\) matrix

\[
Dh(x) = \left[ \frac{\partial h}{\partial x_1}(x), \frac{\partial h}{\partial x_2}(x) \right] = [2x_1, -2x_2].
\]

At \( x = 0 \), \( Dh(0) = [0,0] \), whose kernel is all of \( \mathbb{R}^2 \): that does not constitute a reasonable linearization of \( \mathcal{X} \) around the origin.

We can gain further insight into the issue at hand by considering additional examples. The zero-sets of the functions \( h(x) = x_1^2 - x_2^3 \) and \( h(x) = x_1^2 - x_2^4 \) from \( \mathbb{R}^2 \) to \( \mathbb{R} \), respectively, define a cusp and a double parabola, both of which fail our intuitive test of smoothness at the origin.


![image]({{site.baseurl}}/site/images/cross_cusp.png)


 What the cross, cusp and double parabola have in common is that the rank of \( Dh(x) \) suddenly drops from one to zero at the origin. For the sphere we have Jacobian

\[
Dh(x) = \left[ \frac{\partial h}{\partial x_1}(x), \frac{\partial h}{\partial x_2}(x) \right] = [2x_1, 2x_2]
\]

 The Jacobian has rank one, the maximal rank of the matrix, for all points on the sphere. 






These observations motivate the definition below. Since smoothness is a local notion, the definition is phrased in terms of what the set \( \mathcal{M} \) looks like around each point. Since a set \( \mathcal{M} \) may be equivalently defined by many different functions \( h \), and since it may not be practical (or even possible) to define all of \( \mathcal{M} \) with a single function \( h \), the definition allows for a different one to be used around each point.

**Definition 3.10.** Let \( \mathcal{E} \) be a linear space of dimension \( d \). A non-empty subset \( \mathcal{M} \) of \( \mathcal{E} \) is a smooth embedded submanifold of \( \mathcal{E} \) of dimension \( n \) if either  

1. \( n = d \) and \( \mathcal{M} \) is open in \( \mathcal{E} \)—we also call this an open submanifold; or  
2. \( n = d - k \) for some \( k \geq 1 \) and, for each \( x \in \mathcal{M} \), there exists a neighborhood \( U \) of \( x \) in \( \mathcal{E} \) and a smooth function \( h: U \to \mathbb{R}^k \) such that  
   (a) If \( y \) is in \( U \), then \( h(y) = 0 \) if and only if \( y \in \mathcal{M} \); and  
   (b) \( \text{rank} \ Dh(x) = k \).  

Such a function \( h \) is called a local defining function for \( \mathcal{M} \) at \( x \).  

If \( \mathcal{M} \) is a linear (sub)space, we also call it a linear manifold.
