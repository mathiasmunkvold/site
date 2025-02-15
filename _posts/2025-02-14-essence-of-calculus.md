---
title: 'Basics of Calculus'
date: 2025-02-13
permalink: /posts/2012/08/blog-post-1/
tags:
  - Calculus
---

This post is meant as a simple and short calculus summary that can be refereced to as a preliminary knowledge for alot of the other posts.


#### Motivation: Best linear approximation


Our defintion will concern functions of the form

$$ f: \mathbb{R}^n \rightarrow \mathbb{R}^m $$

which can be thought of as a vector of scalar fields $f_i(\mathbf{x}) \colon \mathbb{R}^n \rightarrow \mathbb{R}$,


$$
f(\mathbf{x}) = \left( \begin{array}{c} f_1(\mathbf{x}) \\ f_2(\mathbf{x}) \\ \vdots \\ f_m(\mathbf{x}) \end{array} \right).
$$


**Definition: Total Derivative**

Let \\(f \colon U\subset \mathbb{R}^m \rightarrow \mathbb{R}^m\\). \\(f\\) is differentiable at \\(p \in U\\) if there exists an operator \\(A \in \mathcal{L}(\mathbb{R}^n,\mathbb{R}^n)\\) and a mapping \\(R\colon \mathbb{R}^n \rightarrow \mathbb{R}^m\\)
such that for all \\(u \in U\\)

$$
f(p+u) = f(p) + Au + R(u), \quad \textcolor{red}{(1)}
$$

where the remainder satifies

$$
\frac{\lVert R(u)\rVert}{\lVert u \rVert}\rightarrow 0, \text{ as } \lVert u \rVert \rightarrow 0. \quad \textcolor{red}{(2)}
$$

---

Note the norm we use here is arbitrary as the norms are equivalent on these spaces. This definiton with the help of the remainder function is often useful in proofs. We also state the equivalent and more familiar looking defintion:  \\(f\\) is differentiable at \\(p \in U\\) if there exists an operator \\(A \in \mathcal{L}(\mathbb{R}^n,\mathbb{R}^n)\\) such that

$$
\operatorname{lim}_{u\rightarrow 0} \frac{\lVert f(p+u)-f(u) - A[u] \rVert}{\lVert u \rVert} = 0
$$


The operator satifysing \\(\textcolor{red}{(1)},\textcolor{red}{(2)}\\) is unique, and is given by a familiar formula.

**Theorem 1**
If \\(f \colon U\subset \mathbb{R}^m \rightarrow \mathbb{R}^m\\) is differentiable at \\(p\\), then \\(Df(p)\\) is the unique linear operator satisfying  \\(\textcolor{red}{(1)} \text{ and }\textcolor{red}{(2)}\\). Moreover, the operator is given by the limit formula

$$
Df(p)[u] = \lim_{t \to 0} \frac{f(p+tu) - f(p)}{t}
$$

**Proof**

Let \\(T\\) be a linear operator satisfying \\(\textcolor{red}{(1)} \text{ and }\textcolor{red}{(2)}\\). Fix an arbitrary \\(u \in \mathbb{R}^n\\), take \\(v = tu\\).


$$
\begin{aligned}
    \frac{f(p+tu) - f(p)}{t} &= \frac{T(tu) +R(tu)}{t} \\
    &= T(u) + \frac{R(tu)}{t\lVert u\rVert}\lVert u \rVert\\
    \lim_{t \to 0} \frac{f(p+tu) - f(p)}{t} &= T(u) =Df(p)[u].
\end{aligned}
$$

Limits, when they exist, are unique. Hence, if \\(\hat{T}\\) is another linear transformation satisfying  \\(\textcolor{red}{(1)} \text{ and }\textcolor{red}{(2)}\\), then \\(T(u)=\hat{T}(u)\\) for all \\(u\\), and \\(T=\hat{T}\\).














