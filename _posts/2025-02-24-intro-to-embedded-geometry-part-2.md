---
title: 'Introduction to Embedded Geometry: Part 2'
date: 2025-02-17
permalink: /posts/2025/02/blog-post-3/
tags:
  - Differential Geometry
---


An interesting problem deals with how we can desribe the direcions we can move away from a point on the manifold. One such possible way of describing this set of directions we may move away from a point on the manifold \\(x\in\mathcal{M}\\) is by considering all smooth curves passing through, in particular their instantenous direction as they pass through the point i.e. their derivative at \\(x\\). 


**Definition: Tangent Space** *Let* \\(\mathcal{M}\\) *be a subset of* \\(\mathcal{E}\\). *For all* \\(x \in \mathcal{M}\\), *define:*

$$
T_x \mathcal{M} = \{ c'(0) \mid c: I \to \mathcal{M} \text{ is smooth and } c(0) = x \}, \tag{3.23}
$$

*where* \\( I \\) *is any open interval containing* \\( t = 0 \\). *That is,* \\( v \in T_x \mathcal{M} \\) *if and only if there exists a smooth curve on* \\( \mathcal{M} \\) *passing through* \\( x \\) *with velocity* \\( v \\).  

Note that \\( T_x \mathcal{M} \\) is a subset of \\( \mathcal{E} \\). For the sphere, it is easy to convince oneself that \\( T_x \mathcal{M} \\) coincides with the subspace in. We show in the next theorem that this is always the case for embedded submanifolds.  

**Theorem: Tangent space for embedded submanifolds** *Let* \\(\mathcal{M}\\) *be an embedded submanifold of* \\(\mathcal{E}\\). *Consider* \\(x \in \mathcal{M}\\) *and the set* \\( T_x \mathcal{M} \\) *(3.23). If* \\(\mathcal{M}\\) *is an open submanifold, then* \\(T_x \mathcal{M} = \mathcal{E}\\). *Otherwise,*  

$$
T_x \mathcal{M} = \ker Dh(x)
$$  

*with* \\( h \\) *any local defining function at* \\( x \\).

**Note**
Recall the fact that if \\(U\\) is a subspace of the finite dimensional linear space \\(V\\), if this subspace has the same dimension as the superspace, then in fact \\(U=V\\). This fact is obvious because if we have a basis of \\(U\\), say \\(\{v_1,\dots,v_n\}\\), the each of these elements are also elements of \\(V\\). Moreover, they are linearly independent and we have as many basis elements as \\(V\\) has dimension, hence this collection satifies the sufficient conditions of being a basis of \\(V\\) also. Hence \\(U=V\\).

**Proof**

For open submanifolds, the claim is clear. By definition, \\(T_x \mathcal{M}\\) is included in \\(\mathcal{E}\\). The other way around, for any \\( v \in \mathcal{E} \\), consider \\( c(t) = x + tv \\): this is a smooth curve from some non-empty interval around \\( 0 \\) to \\( \mathcal{M} \\) such that \\( c(0) = x \\), hence \\( v = c'(0) \\) is in \\( T_x \mathcal{M} \\). This shows \\( \mathcal{E} \\) is included in \\( T_x \mathcal{M} \\), so that the two coincide.  

Now consider the case of \\(\mathcal{M}\\) an embedded submanifold of dimension \\( n = d - k \\) with \\( k \geq 1 \\). Let \\( h: U \to \mathbb{R}^k \\) be a local defining function of \\(\mathcal{M}\\) around \\( x \\). The proof is in two steps. First, we show that \\( T_x \mathcal{M} \subseteq \ker Dh(x)\\). Then, we use the trick noted above the proof: we show that \\( T_x \mathcal{M} \\) contains a linear subspace of the same dimension as \\( \ker Dh(x) \\). These two facts combined indeed confirm that \\( T_x \mathcal{M} = \ker Dh(x) \\).  

**Step 1.** To show \( T_x \mathcal{M} \subseteq \ker Dh(x)\\), suppose \\( v \\) is in \\( T_x \mathcal{M} \\), there exists \\( c: I \to \mathcal{M} \\), smooth, such that \\( c(0) = x \\) and \\( c'(0) = v \\). Since \\( c(t) \\) is in \\( \mathcal{M} \\), we have \\( h(c(t)) = 0 \\) for all \\( t \in I \\) (if need be, restrict the interval \\( I \\) to ensure \\( c(t) \\) remains in the domain of \\( h \\)). Thus, the derivative of \\( h \circ c \\) vanishes at all times:  

$$
0 = \frac{d}{dt} h(c(t)) = Dh(c(t))[c'(t)].
$$

In particular, at \\( t = 0 \\) this implies \\( Dh(x)[v] = 0 \\), that is, \\( v \in \ker Dh(x) \\). This confirms \\( T_x \mathcal{M} \subseteq \ker Dh(x) \\).  

**Step 2.** To show that \\( T_x \mathcal{M} \\) contains a subspace of the same dimension as \\( \ker Dh(x) \\) (namely, of dimension \\( n = d - k \\)), we must construct smooth curves on \\( \mathcal{M} \\) that pass through \\( x \\) with various velocities. To do so, we call upon Theorem **3.12**. The latter provides us with a diffeomorphism \\( F': U \to V \\) (where \\( U \\) is now a possibly smaller neighborhood of \\( x \\) than the original domain of \\( h \\)). We use \\( F'^{-1} \\) to construct smooth curves on \\( \mathcal{M} \\) that pass through \\( x \\).




