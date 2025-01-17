---
title:  "The Joy of Lie Algebras I"
categories: 
  - Blog
tags:
  - Maths
  - Lie algebras
---

I've been studying Lie algebras from the fantastic book <span style="color:LightSeaGreen">_Lie Algebras of Affine and Finite Types_</span> by Roger Carter for quite a while. This textbook provides a rapid introduction to the core theorems
and results of Lie algebras. It lacks exercises, but deciphering the proofs there is in itself a hefty but rewarding exercise.

That being said, the book is certainly pitched at a more advanced level than <span style="color:LightSeaGreen">_Introduction to Lie Algebras_</span> by Karin Erdman and Mark J. Wildon, so I will suggest anyone
new to Lie algebras to check out that book first, which is friendly written and, in my opinion, quite enjoyable.

My (lukewarm) take of this topic? It should be taught in every undergraduate math course!

Lie algebras are excellent as a second topic course after linear algebra, as a showcase of how linear algebra is used in practice. The main motiviation is that, after we have found a fitting linear structure, or a useful generalisation
of eigenvalues on Lie algebras, we can use the wide arrays of tools, e.g. eigenspaces and Cayley--Hamilton theorem, to study them. In this example, weight decompositions, as we shall see later, are simply the same as invariant subspace decompositions determined
by (generalised) eigenvalues.

The question still remains: _why Lie algebras, instead of any other structure?_

Lie algebras are intimately connected to geometry, according to the [Lie algebra-Lie group correspondence.](https://en.wikipedia.org/wiki/Lie_group%E2%80%93Lie_algebra_correspondence) So if you are interested in geometry of manifolds, then Lie algebras
is essential. There is also a connection to quantum physics where representations of Lie algebras plays an important rôle in describing symmetries of particles. And finally, if you are an algebraist,
then Lie algebras are where representation theory shines.

As a primarily geometry-oriented person myself, I'd say that the Lie algebra-Lie group correspondence is rather amazing. I'd love that one day I'd get to describe that in a blog post. But we have to begin somewhere...

# What is a Lie algebra?

A **Lie algebra** is a vector space $$ L $$ over a field $$ k $$ (usually taken to be $$ \mathbb{C} $$) with an operation, called **the Lie bracket**, $$ [-,-] \colon L \times L \to L $$ satisfying the following properties:

1. $$[ax + bx', y] = a[xy] + b[x'y] $$ and $$ [x, ay + by'] = a[xy] + b[xy'] $$ (it is bilinear);
2. $$[xx] = 0 $$ for all $$ x \in L $$;
3. $$[x[yz]] + [y[zx]] + [z[xy]] = 0$$ for all $$ x, y, z \in L $$. This is called the **Jacobi identity**.

> **Exercise.** Show that $$ [xy] = -[yx] $$ for all $$ x, y \in L $$. Hence the Lie bracket is anticommutative.

As is tradition in algebra, after we have a structure, we seek maps between them which preserve the structure. This gives the notion of **Lie algebra homomorphism**.

If $$ L, M $$ are Lie algebras, then a linear map $$ \theta \colon L \to M $$ is a Lie algebra homomorphism if $$ \theta[xy] = [\theta x, \theta y] $$ for all $$x, y \in L$$. It is a **Lie algebra isomorphism**
if it is bijective as a function (thus a vector space isomorphism).

Finally we look at the notions of Lie subalgebras and ideals.

1. Let $$ L $$ be a Lie algebra, and let $$ H, K $$ be vector subspaces of $$ L. $$ Define $$ [HK] $$ to be the subspace of $$ L $$ spanned by the elements of the form $$ [hk] $$, where $$ h\in H $$ and $$ k \in K $$.
2. A subspace $$ H $$ of $$ L $$ is said to be a **Lie subalgebra** of $$ L $$ if $$ [HH] \subseteq H $$.
3. A subspace $$ I $$ of $$ L $$ is said to be an **ideal** of $$ L $$ if $$ [IL] \subseteq I $$.

> **Exercise.** Show that if $$ I $$ is an ideal of $$ L $$, then $$ [LI] \subseteq I $$ too.

After we obtain the notion of an ideal, we may define quotients of Lie algebras. Suppose $$ L $$ is a Lie algebra, and $$ I $$ an ideal of $$ L $$. Since $$ I $$ is already a subspace of $$ L $$,
we may simply take the quotient to get the factor space $$ L / I $$. Define the Lie braket on this space as follows:

$$
	[x + I, y + I] = [xy] + I
$$
for all $$ x, y \in L $$.

> **Exercise.** Show that the above operation is well-defined.

> **Exercise.** Prove the first isomorphism theorem for Lie algebras. Namely, let $$ \theta \colon L \to M $$ be a Lie algebra homomorphism. Then
> 
> $$ \operatorname{ker}(\theta) = \{ x \in L : \theta x = 0 \} $$ is an ideal of $$ L $$,
> 
> and $$ \operatorname{im}(\theta) $$ is a subalgebra of $$ M $$. 
>
> Finally, $$ L / \operatorname{ker}(\theta) $$ is isomorphic to $$ \operatorname{im}(\theta) $$.

Next time, we are going to investigate representations and modules arising from a Lie algebra, and prove the first substantial result, which is Lie's theorem.