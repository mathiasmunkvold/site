---
title: 'Introduction to Embedded Geometry: Part 1'
date: 2025-02-17
permalink: /posts/2025/02/blog-post-2/
tags:
  - Differential Geometry
---

The post is meant as an introduction to the theory of submanifolds. The crux of of the matter will be the following: certain sets can be linearized in a meaningful way around each of its points. To make this idea concrete we will consider the sphere, $\mathcal{S}^{d-1}$, that is the set of vectors in $\mathbb{R}^d$ satistyfing

$$
h(x)= x^Tx-1 = 0.
$$

We refer to $h$ as the defining equation. To obtain a linearization around each point we differentiate the defining equation, or rather, consider a truncated Taylor expansion of it:

$$
h(x+tv) = h(x) + tDh(x)[v] + O(t^2) 

$$

Now, with $x\in \mathcal{S}^{d-1}$ we have $h(x)=0$. If we want to "force" $x + tv\in \mathcal{S}^{d-1}$, clearly we must have $Dh(x)[v]=0$, in other words $v\in \operatorname{ker}(Dh(x))$. If this is the case, then $h(x + tv) = O(t^2)$ meaning it almost satifies the defining equation for small $t$. Hence, the subspace $\operatorname{ker}(Dh(x))$ is the logical candidate to consider as the linearization of $\mathcal{S}^{d-1}$ at $x$.


$$
Dh(x)[v] = \lim_{t \to 0} \frac{h(x + tv) - h(x)}{t} = x^\top v + v^\top x = 2x^\top v,
$$

the kernel of \\(Dh(x)\\) is the subspace orthogonal to \\(x\\) in \\(\mathbb{R}^d\\) (with respect to the usual inner product). 

At first, one might think that if a set is defined by an equation of the form \\( h(x) = 0 \\) with some smooth function \\( h \\), then that set is smooth and can be linearized by the kernels of \\( Dh \\). However, this is not the case. Indeed, consider the following example in \\(\mathbb{R}^2\\), :

$$
\mathcal{X} = \{ x \in \mathbb{R}^2 : h(x) = x_1^2 - x_2^2 = 0 \}.
$$

The defining function \\( h \\) is smooth, yet the set \\( \mathcal{X} \\) is a cross in the plane formed by the union of the lines \\( x_1 = x_2 \\) and \\( x_1 = -x_2 \\). We want to exclude such sets because of the kink at the origin. What went wrong with it? If we blindly use the kernel of the differential to linearize \\( \mathcal{X} \\). As \\(h\colon \mathbb{R}^2 \to \mathbb{R}\\), the total derivative/ Jacobian is given by the \\(1\times 2\\) matrix

$$
Dh(x) = \left[ \frac{\partial h}{\partial x_1}(x), \frac{\partial h}{\partial x_2}(x) \right] = [2x_1, -2x_2].
$$

At \\\( x = 0 \\\), \\( Dh(0) = [0,0] \\), whose kernel is all of \\( \mathbb{R}^2 \\): that does not constitute a reasonable linearization of \\( \mathcal{X} \\) around the origin.

We can gain further insight into the issue at hand by considering additional examples. The zero-sets of the functions \\( h(x) = x_1^2 - x_2^3 \\) and \\( h(x) = x_1^2 - x_2^4 \\) from \\( \mathbb{R}^2 \\) to \\( \mathbb{R} \\), respectively, define a cusp and a double parabola, both of which fail our intuitive test of smoothness at the origin.


![image]({{site.baseurl}}/site/images/cross_cusp.png)


 What the cross, cusp and double parabola have in common is that the rank of \\( Dh(x) \\) suddenly drops from one to zero at the origin. For the sphere we have Jacobian

$$
Dh(x) = \left[ \frac{\partial h}{\partial x_1}(x), \frac{\partial h}{\partial x_2}(x) \right] = [2x_1, 2x_2]
$$

 The Jacobian has rank one, the maximal rank of the matrix, for all points on the sphere. 






These observations motivate the definition below. Since smoothness is a local notion, the definition is phrased in terms of what the set \\( \mathcal{M} \\) looks like around each point. Since a set \\( \mathcal{M} \\) may be equivalently defined by many different functions \\( h \\), and since it may not be practical (or even possible) to define all of \\( \mathcal{M} \\) with a single function \\( h \\), the definition allows for a different one to be used around each point.

**Definition 3.10.** Let \\( \mathcal{E} \\) be a linear space of dimension \\( d \\). A non-empty subset \\( \mathcal{M} \\) of \\( \mathcal{E} \\) is a smooth embedded submanifold of \\( \mathcal{E} \\) of dimension \\( n \\) if either  

1. \\( n = d \\) and \\( \mathcal{M} \\) is open in \\( \mathcal{E} \\)—we also call this an open submanifold; or  
2. \\( n = d - k \\) for some \\( k \geq 1 \\) and, for each \\( x \in \mathcal{M} \\), there exists a neighborhood \\( U \\) of \\( x \\) in \\( \mathcal{E} \\) and a smooth function \\( h: U \to \mathbb{R}^k \\) such that  
   (a) If \\( y \\) is in \\( U \\), then \\( h(y) = 0 \\) if and only if \\( y \in \mathcal{M} \\); and  
   (b) \\( \text{rank} \ Dh(x) = k \\).  

Such a function \\( h \\) is called a local defining function for \\( \mathcal{M} \\) at \\( x \\).  

If \\( \mathcal{M} \\) is a linear (sub)space, we also call it a linear manifold.

In summary, while we initally may expect that as long as the defining function is smooth, so will our set/manifold be as well. As a matter of fact, one can show for any closed set in $\mathbb{R}^n$, the set can be expressed as the zero set of some function. As this statement does not put any constraints on how messed up a the closed set may look like, naturally we need another condtion to ensure smoothness of the set. 


We will state an equivalent way to define a embedded submanifold. First recall the definition of a diffeomorpihism (see the Calculus blog-post.)

**Theorem** *Let* \\(\mathcal{E}\\) *be a linear space of dimension* \\(d\\). *A subset* \\(\mathcal{M}\\) *of* \\(\mathcal{E}\\) *is an embedded submanifold of* \\(\mathcal{E}\\) *of dimension* \\(n = d - k\\) *if and only if for each* \\(x \in \mathcal{M}\\) *there exists a neighborhood* \\(U\\) *of* \\(x\\) *in* \\(\mathcal{E}\\), *an open set* \\(V\\) *in* \\(\mathbb{R}^d\\) *and a diffeomorphism* \\(F: U \to V\\) *such that* 

$$
F(\mathcal{M} \cap U) = E \cap V
$$

*, where* \\(E = \{ y \in \mathbb{R}^d : y_{n+1} = \cdots = y_d = 0 \}\\) *is a linear subspace of* \\(\mathbb{R}^d\\).


![image]({{site.baseurl}}/site/images/submanifolds-intution.png)



**Proof**

We will prove the right direction i.e. assuming we have local defining funcion \\(h\\) in a nbh. of \\(x\in\mathcal{M}\\) and with the help of the inverse function theorem construct a diffeomorphism \\(F\\) that linearizes \\(\mathcal{M}\\) around \\(x\\).


Let \\( h: U \to \mathbb{R}^k \\) be smooth, where \\( x \in U \\), \\( U \\) is open in \\(\mathcal{E}\\), and \\(\dim \mathcal{E} = d\\).

\\( h(y) = 0 \Leftrightarrow y \in U \cap \mathcal{M} \\)

\\[
\text{rank}(Dh(x)) = k = d - n, \quad \dim \mathcal{M} = n
\\]

The derivative \\( Dh(x) \\) is given by:

\\[
Dh(x): \mathcal{E} \to \mathbb{R}^k
\\]

Since \\(\mathcal{E} \equiv \mathbb{R}^d\\) after choosing a basis, \\( Dh(x) \\) is a matrix of dimension \\( k \times d \\). Now, since this matrix has rank \\(k\\), it has \\(k\\) linearly independent columns. If we were to permute our basis vectors we can collect these columns into a \\(k\times k\\) invertible submatrix. To give a little further recollection on this switching of basis, recall that any permutation of the basis vectors of a finite dimensional linear space can be expressed by means of a permuation matrix. Left multiplication with such matrices change the order of the columns. The simplest such permutation matrices is the identity matrix, which does a trivial permuation:

$$
\begin{bmatrix}
a_1 & a_2 \\
a_3 & a_4
\end{bmatrix}
\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} =
\begin{bmatrix}
a_1 & a_2 \\
a_3 & a_4
\end{bmatrix}
$$

Permuting the standard basis vectors in \\(\mathbb{R}^2\\), corresponds to

$$
\begin{bmatrix}
a_1 & a_2 \\
a_3 & a_4
\end{bmatrix}
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix} =
\begin{bmatrix}
a_2 & a_1 \\
a_4 & a_3
\end{bmatrix}.
$$

So in short, we permute the columns so that the last \\(k\\) columns are linearly independent.

\\[
Dh(x) =
\begin{bmatrix}
A & B
\end{bmatrix}
\in \mathbb{R}^{k \times d}
\\]


We introduce a candidat  for our diffeomorphism. 

Define \\( F: U \to \mathbb{R}^d \\):

$$
F(y) =
\begin{bmatrix}
y_1 \\
\vdots\\
y_{d-k} \\
h_1(y) \\
\vdots\\
h_k(y)
\end{bmatrix}
$$

where \\( F \\) is smooth.

When computing the Jacobian in the standard way of it reduces to this in block form:

$$
DF(x): \mathbb{R}^d \to \mathbb{R}^d
$$

$$
DF(x) =
\begin{bmatrix}
I_{d-k} & A \\
0_{(d-k) \times k} & B
\end{bmatrix}
$$

We can argue that it is invertible by either noticing that this is a triagonal matrix where each diagonal block is invertible. Or we can find the inverse explictly by:

$$
(DF(x))^{-1} =
\begin{bmatrix}
I_{d-k} & 0 \\
- B^{-1} A & B^{-1}
\end{bmatrix}
$$


So, the inverse function theorem now applies. So we reduce \\(U\\) to a smaller nbh. And let \\(V = F(U)\\). It only remains to show 


$$
F(\mathcal{M} \cap U) = E \cap V
$$
