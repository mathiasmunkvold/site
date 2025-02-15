---
title: 'Basics of Calculus'
date: 2025-02-13
permalink: /posts/2012/08/blog-post-1/
tags:
  - Calculus
---

Essential Calculus
======

This post is meant as a simple and short calculus summary that can be refereced to as a preliminary knowledge for alot of the other posts.


#### Motivation: Best linear approximation




Our defintion will concern functions of the form

$$ f: \mathbb{R}^n \rightarrow \mathbb{R}^m $$

which can be thought of as a vector of scalar fields $f_i(\mathbf{x}) \colon \mathbb{R}^n \rightarrow \mathbb{R}$,


$$
f(\mathbf{x}) = \left( \begin{array}{c} f_1(\mathbf{x}) \\ f_2(\mathbf{x}) \\ \vdots \\ f_m(\mathbf{x}) \end{array} \right).
$$


**Definition: Total Derivative**

This is a test of some inline math
\\(f \colon U\subset \mathbb{R}^m \rightarrow \mathbb{R}^m\\).Let $f \colon U\subset \mathbb{R}^m \rightarrow \mathbb{R}^m$. $f$ is differentiable at $p \in U$ if there exists an operator $A \in \mathcal{L}(\mathbb{R}^n,\mathbb{R}^n)$ and a mapping $R\colon \mathbb{R}^n \rightarrow \mathbb{R}^m $
such that for all $u \in U$

$$
f(p+u) = f(p) + Au + R(u), \quad \textcolor{red}{(1)}
$$

where the remainder satifies

$$
\frac{\lVert R(u)\rVert}{\lVert u \rVert}\rightarrow 0, \text{ as } \lVert u \rVert \rightarrow 0. \quad \textcolor{red}{(2)}
$$

Note the norm we use here is arbitrary as the norms are equivalent on these spaces.



