---
title:  "The Joy of Lie Algebras, Part II: Representations, Modules and Lie's Theorem"
categories: 
  - Blog
tags:
  - Maths
  - Lie algebras
---

In the previous blog post, we introduced the concept of Lie algebras and their related basic notions. We now proceed to investigate the theory of representations of Lie algebras.

# Important Classes of Lie Algebras

Let's first consider some examples of Lie algebras.

Given a field $$ k $$, considered as a vector space over itself, the only possible Lie algebra on $$ k $$ is the trivial one. Indeed, for any $$ x, y \in k $$,

$$
[x, y] = xy [1,1] = 0.
$$

Such a Lie algebra is called **abelian**. More generally, any vector space can be given the **abelian Lie algebra structure** by declaring the Lie bracket to be zero at all inputs.

Now for a non-trivial example. The vector space $$ M_n (k) $$ of $$ n $$-dimensional square matrices over a field $$ k $$ is a $$ k $$-vector space. It is furthermore an associative noncommutative $$ k $$-algebra
with matrix multiplication. Define a Lie bracket on $$ M_n (k) $$ by the formula

$$
	[x,y] = xy - yx,
$$

for every $$ x, y \in M_n (k) $$. 

The reader is invited to check that the Jacobi identity holds (which is just an exercise in algebra). Erdmann and Wildon say that it is "one of the exercises that every mathematician should do in their lifetime".
The Lie algebra structure on $$ M_n (k) $$ is called **the general linear Lie algebra** of degree $$ n $$ over $$ k $$, and is written $$ \mathfrak{gl}_n(k) $$.

There is nothing special with matrices here. If we have an associative algebra $$ A $$ over a field $$ k $$, then we can define a Lie algebra on it by setting $$ [x, y] = xy - yx $$ as we have done here. This is aptly named
the associated Lie algebra of $$ A $$.

# Representations and Modules

As of now, Lie algebras are still "up in the air", and to work with them, it would be nice if we can find a concrete way of writing Lie algebras as something easily computable, such as matrices. This leads to the following definition.

<div class="notice">
  <h4>Definition</h4>
  <p>A <b>representation</b> of a Lie algebra \(L \) is a Lie algebra homomorphism $$ \rho\colon L \to \mathfrak{gl}_n(k).$$ for some \(n\). The number \(n\) is the <b>degree</b> of the representation.</p>
</div>

We may as well view $$ L $$ as acting directly on the $$ n $$-dimensional vector space that $$ \mathfrak{gl}_n(k) $$ acts on.

<div class="notice">
  <h4>Definition</h4>
  <p>Let \(L \) be a Lie algebra. A (left) \(L \)-<b>module</b> is a vector space \( V \) with a multiplication 
  $$ 
  \begin{align}
	L \times V & \to V \\
	(x, v) & \mapsto xv.
  \end{align}
  $$
  satisfying the following axioms:
  <ol>
	<li>\((x,v)\mapsto xv\) is linear in both \(x\) and \(v\);</li>
	<li>\([x,y]v = x(yv) - y(xv)\) for all \(x, y \in L\) and \(v \in V\).</li>
  </ol>
  </p>
</div>

The two notions are indeed the same, as the following exercises show.

> **Exercise.** Let $$ L $$ be a Lie algebra, and $$ V $$ a finite-dimensional $$ L $$-module. Then this gives rise to a representation $$ \rho \colon L \to \mathfrak{gl}_n(k).$$
>
> Conversely, given a representation $$ \rho\colon L \to \mathfrak{gl}_n(k) $$, then this define an $$ L $$-module on an $$ n $$-dimensional vector space $$ V $$.

Two representation $$ \rho, \rho'$$ are said to be **equivalent** if they differ by a change of basis, that is, there is an invertible matrix $$ T $$ such that, for all $$ x \in L $$,
$$
	\rho(x) = T^{-1} \rho'(x) T.
$$

> **Exercise.** Let $$ L $$ be a Lie algebra, and $$ V $$ a finite-dimensional $$ L $$-module. We have shown that this gives rise to a representation $$ \rho \colon L \to \mathfrak{gl}_n(k).$$ This will involve choosing a basis for $$ V $$ to write the action of $$ L $$ as a linear map.
> Now pick a new basis for $$ V $$, and so we have a new representation $$ \rho' $$. Prove that $$ \rho $$ and $$ \rho' $$ are equivalent in the above sense.

The following example is an important one which shall appears often in the sequel. We let a Lie algebra $$ L $$ to be an $$ L $$-module over itself by considering the action given by

$$
	x \cdot y = [xy] \quad\text{for all } x, y \in L.
$$

This is indeed an $$ L $$-module, because the Jacobi identity implies that

$$
	[[xy]z] = [x[yz]] - [y[xz]],
$$

and bilinearity is immediate. This $$ L $$-module structure on $$ L $$ is named the **adjoint module**. We also have the adjoint map $$ \operatorname{ad}x\colon L \to L $$ given by

$$
	\operatorname{ad}x\cdot y = [xy]	\quad\text{for all } x, y.
$$

This is both a Lie algebra homomorphism over $$ L $$ and an $$ L $$-module homomorphism.

Finally, we have the notion of submodules analogous to the usual definition: $$ U $$ is a submodule of $$ V $$ if the action of $$ L $$ on $$ U $$ is closed in $$ U $$, i.e. $$ LU \subseteq U $$. Any $$ L $$-module $$ V $$ has two trivial submodules $$ {0} $$ and $$ V $$.
A module is **irreducible** if it has no non-trivial submodules.

# Nilpotent and Soluble Lie Algebras

Taking inspiration from the study of groups and modules, we consider a series of Lie algebras.

<div class="notice">
  <h4>Definition</h4>
  <p>Suppose \(L\) is a Lie algebra. The sequence of Lie subalgebras defined by $$ L^1 = L, \text{ and }  L^{n + 1} = [L^nL] \quad\text{for all } n \geq 1$$ is called the <b>lower central series</b> of \(L\).
  We say that \(L\) is <b>nilpotent</b> if this sequence eventually vanishes, i.e. \(L^n = 0\) for some \(n\).</p>
</div>

I find that the literature differs in regard to naming this sequence. In the textbook _Lie Groups, Lie Algebras and Representations_ by Brian Hall, it is called the **upper central series**. We shall keep to the name lower central series, in connection with
groups and modules.

> **Exercise.** 
> 1. A Lie algebra is abelian if and only if $$ L^2 = 0 $$. 
> 2. Every subalgebra and every factor algebra of a nilpotent algebra is nilpotent.

We now consider another type of sequences.

<div class="notice">
  <h4>Definition</h4>
  <p>Suppose \(L\) is a Lie algebra. The sequence of Lie subalgebras defined by $$ L^{(1)} = L, \text{ and }  L^{(n+1)} = [L^{(n)},L^{(n)}] \quad\text{for all } n \geq 1$$ is called the <b>derived series</b> of \(L\).
  We say that \(L\) is <b>soluble</b> (or <b>solvable</b>) if this sequence eventually vanishes, i.e. \(L^{(n)} = 0\) for some \(n\).</p>
</div>

The two series are descending sequences of Lie algebras, that is 

$$ L^1 \supseteq L^2  \supseteq L^3 \supseteq \dotsc $$ 

and 

$$ L^{(1)} \supseteq L^{(2)}  \supseteq L^{(3)} \supseteq \dotsc. $$

> **Exercise.** Show that $$ L^{(n)} \subseteq L^n $$ for all $$ n \in \mathbb{N} $$. Hence $$ L $$ is soluble if it is nilpotent. (The converse is false.)

> **Exercise.** Every subalgebra and every factor algebra of a soluble algebra is soluble. Conversely, if $$ I $$ is an ideal of a Lie algebra $$ L $$ such that $$ I $$ and $$ L/I $$ are soluble, then $$ L $$ is soluble.

# Lie's Theorem

In what follows, we work in an algebraically closed ring of characteristic 0, e.g. over the complex numbers. All the Lie algebra considered in this section are finite-dimensional.

We study the question on the structure of representations of soluble Lie algebras. Let's first consider one-dimensional representations of a Lie algebra $$ L $$, which by definition is a Lie algebra homeomorphism

$$ \rho\colon L \to \mathfrak{gl}_1(k) \cong \mathbb{C}$$

so that $$ \rho[xy] = [\rho x, \rho y] $$ for all $$ x, y \in L $$. Since the Lie algebra structure on $$ \mathbb{C} $$ is abelian, this implies that $$ \rho[xy] = 0 $$. 

On the other hand, if we have a linear map $$ \rho \colon L \to \mathbb{C} $$ such that $$ \rho[xy] = 0 $$ for all $$ x, y \in L $$, then this defines a one-dimensional representation of $$ L $$, because
$$ \rho[xy] = 0 = [\rho x, \rho y] $$. Thus we have just proved the following fact.

**Preposition.** A linear map $$\rho \colon L \to \mathbb{C} $$ is a one-dimensional representation if and only if it vanishes on $$ L^2 $$.
{: .notice--info}


We now arrive at the main result of this very blog post, _Lie's theorem_, which states that any irreducible representation of a Lie algebra is one-dimensional.

**Lie's theorem.** If $$ L $$ is a soluble Lie algebra and $$ V $$ a finite-dimensional irreducible $$ L $$-module, then $$ \dim V = 1 $$.
{: .notice--danger}

Of course we take $$ V $$ to be a non-zero module.

**Proof.** We start with an observation. If $$ L $$ is a soluble Lie algebra, then $$ L^{2} \neq L $$, otherwise the derived series never vanishes. Indeed, since $$ L^2 = L^{(2)} $$ for any Lie algebra $$ L $$, if $$ L^{2} = L $$ then

$$
	L^{(3)} = [L^{(2)}, L^{(2)}] = [L,L] = L^{(2)},
$$

and so $$ L^{(k)} = L^{(2)} $$ for $$ k \geq 3 $$ by induction.

Thus we can find a subspace $$ I $$ of $$ L $$ such that $$ I \supseteq L^2 $$ and $$ \dim I = \dim L - 1$$. Moreover, $$ I $$ is an ideal of $$ L $$, since

$$
	[IL] \subseteq [LL] = L^2 \subseteq I.
$$

The proof of Lie's theorem is by induction on $$ \dim L $$. For the base case when $$ \dim L = 1 $$ and $$ V $$ is an irreducible $$ L $$-module, let $$ \lbrace e \rbrace $$ be a basis of $$ L $$. 
Consider the map $$\rho(e) \colon V \to V $$. It must have an eigenvector $$ v \in V $$, and so $$ \mathbb{C} v $$ is a submodule of $$ V $$. But $$ V $$ is irreducible, therefore $$ V = \mathbb{C} v $$ as needed.

Now suppose $$ \dim L > 1 $$ and $$ V $$ is an irreducible $$ L $$-module. We may view $$ V $$ as an $$ I $$-module, now take $$ W $$ to be an irreducible $$ I $$-submodule of $$ V $$. Since $$ I $$ has one less dimension than $$ L $$, we find that $$ \dim W = 1 $$ by induction.
Let $$ w $$ be a non-zero vector in $$ W $$. Then

$$
	yw = \lambda (y) w \quad\text{for all } y \in I
$$

where $$ \lambda $$ is the one-dimensional representation of $$ I $$ given by $$ W $$.

We now search for every vector in $$ V $$ that transforms in the same manner under $$ I $$ as those in $$ W $$. In other words, we consider the set

$$
	U = \lbrace u \in V : yu = \lambda(y) u \quad\text{ for all } y \in I \rbrace.
$$

Hence by definition $$ 0 \neq W \subseteq U \subseteq V $$.

We claim that $$ U $$ is an $$ L $$-submodule of $$ V $$. To see this, let $$ u \in U$$ and $$ x \in L $$. Then

$$
	y(xu) = x(yu) - [xy]u = \lambda(y)(xu) - \lambda[xy]u
$$

since $$ [xy] \in I $$. If we can show that $$ \lambda[xy] = 0 $$, then $$y(xu) = \lambda(y)(xu) $$ and then we shall have proved our claim. Since $$ V $$ is irreducible, it follows that $$ U = V $$, and so

$$
	yv = \lambda(y) v\quad\text{ for all } v \in V, y \in I.
$$

Since $$ \dim I = \dim L - 1$$, we can write $$ L = I \oplus \mathbb{C}x $$, the direct sum of subspaces. Consider an eigenvector $$ v $$ for $$ x $$ with eigenvalue $$ \eta $$. Then for every $$ y \in L $$, write $$y = w + ax $$, where $$ w \in L $$ and $$ a \in \mathbb{C} $$.
We then have

$$
	yv = (w + ax)v = wv + a(xv) = \lambda(w)v + a\eta x = (\lambda(w) + a \eta) x.
$$

Therefore $$ \mathbb{C}v $$ is a non-zero $$ L $$-submodule of $$ V $$. But then $$ V = \mathbb{C} v $$ by irreducibility. This finishes the proof.


As we have seen, everything is based on showing that $$ \lambda[xy] = 0 $$, so we do just that! First note that the decomposition $$ L = I \oplus \mathbb{C}x $$ does not depend on our claim, so we can use it. We then only need to show that
$$ \lambda[xy] $$ for this very $$ x $$ that gives rise to the decomposition.

Let $$ u $$ be any non-zero element of $$ U $$. Consider the sequence

$$
	v_0 = u, v_1 = xu, v_2 = xv_1 = x(xu), \dotsc,
$$

Since $$ V $$ is finite-dimensional, there exists the maximum index $$ p $$ such that $$v_0, \dotsc, v_p $$ is linearly independent. Now consider the action by any element $$ y \in I $$ on these vectors.
For $$ v_0 $$ we have

$$
	yv_0 = yu = \lambda(y)u = \lambda(y) v_0.
$$

We shall show that $$ yv_i = \lambda(y)v_i + \text{ a linear combinations of $v_0, \dotsc, v_{i - 1} $} $$. Indeed, by induction,

$$
	\begin{align}
	yv_i & = y(xv_{i - 1}) = x(yv_{i - 1}) - [xy]v_{i - 1} \\
	& = x(\lambda(y)v_{i -1} + \text{ a linear combinations of $v_0, \dotsc, v_{i - 2} $}) - [xy]v_{i - 1} \\
	& = \lambda(y)xv_{i - 1} + \text{ a linear combinations of $v_0, \dotsc, v_{i - 1} $}) - [xy]v_{i - 1} \\
	& = \lambda(y)v_i + \text{ a linear combinations of $v_0, \dotsc, v_{i - 1} $})
	\end{align}
$$

It can be show that the subspace $$ \langle v_0, \dotsc, v_n \rangle $$ is an $$ L $$-submodule of $$ V $$, just like how we have shown that $$ V = \mathbb{C} v $$. One can also argue using the fact that $$ V $$ is invariant under both $$ I $$ and $$\mathbb{C} x $$.

But $$ V $$ is irreducible, and so

$$
	V = \langle v_0, \dotsc, v_p \rangle.
$$

Now consider $$ [xy] \in I $$. We can compute the trace of $$ [xy] $$ using the fact that $$ v_0, \dotsc, v_p $$ form a basis of $$ V $$. It follows that

$$
	\operatorname{tr}_V [xy] = (p + 1) \lambda[xy].
$$

So $$ (p + 1)\lambda[xy] = \operatorname{tr} [xy] = \operatorname{tr}(xy) - \operatorname{tr}(yx) = 0$$. This proves the claim.

We end this section with a few corollaries of Lie's theorem. The first one of them pops up in the course of the proof.

**Corollary.** Let $$ L $$ be a soluble Lie algebra and $$ V $$ be a finite-dimensional irreducible $$ L $$-module. Then there is a basis of $$ V $$ such that every matrix representation of the action of elements of $$ L $$ on $$ V $$ is upper-triangular.
{: .notice--danger}

**Proof.** Follows from $$ yv_i = \lambda(y)v_i + \text{ a linear combinations of $v_0, \dotsc, v_{i - 1} $} $$. The basis we sought is $$ v_0, \dotsc, v_p $$.

**Corollary.** Let $$ L $$ be a soluble Lie algebra and $$ \dim L = n $$. Then there is a chain of ideals
$$
	0 = I_0 \subseteq I_1 \subseteq \dotsb \subseteq I_{n} = L
$$
with $$ \dim I_r = r $$. This is called a **complete flag** in $$ L $$.
{: .notice--danger}

**Proof.** Take $$ V $$ to be the adjoint $$ L $$-module. Consider the maximal chain of submodules of $$ L $$, which is the same thing as ideals of $$ L $$, and notice that any submodule with dimension bigger than 1 must be reducible.