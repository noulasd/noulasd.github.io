---
layout: post
title:  "Understanding Group Actions on Sets"
date:   2021-08-03 11:55:04 +0300
categories: Algebra
permalink: Understanding-Group-Actions-on-Sets.html
---

Usually when a math student encounters the definition of group action for the first time in an introductory abstract algebra or group theory class, they get really confused about it. That's for a good reason as the definition seems quite random at first, introducing a binary operation between a group and a set. So let's see what's really going on.

We can start with some simple examples. Let's consider the additive group $$(\mathbb{Z}, +)$$ and the set $$\mathbb{Q}$$ of the rational numbers. If we pick for example the integer $$x=2$$ from our group then for every rational $$q \in \mathbb{Q}$$ we can define the binary operation $$*$$ between our group and our set such as:


$$ 2*q = 2q$$


where on the right side is the usual multiplication. So nothing really fancy happening in this example, right? We should notice, however, that the random integer $$2$$ we picked (any other element from our group works just fine) **permutes** every rational (every element of our set) to another rational (another element of our set). 



Keep the word permutation in mind. Let's consider now the symmetrical group $$S_n$$ of $$n$$ elements and the set $$ [n] = \{1,2,\ldots,n\}$$. We fix an element $$\sigma \in S_n$$ and thus for every $$i \in [n]$$ we can define the binary operation $$*$$ between our group and our set such as:


$$\sigma * i = \sigma (i)$$

We are literally just permuting the elements of $$[n]$$ the way $$\sigma$$ does. But $$\sigma$$ is by definition a permutation of $$[n]$$ so this whole example is just a tautology. In a sense, the group element we choose permutes in it's own way the elements of our set. That is what's really happening. Let's revisit the formal definition now.


$$ \text{Definition. Let } G \text{ be a group and } X \neq \varnothing \text{ a set. A (left) group action of } G $$
$$ \text{ on the set } X \text{ is a function } G \times X \rightarrow X, (g,x) \mapsto g*x \quad \text{ such that: } $$ 


$$1_G * x = x \quad \text{ for all } x \in X.$$

$$(g_1 \cdot g_2) * x = g_1 * (g_2 * x)  \quad \text{ for all } x \in X \text{ and } g_1,g_2 \in G.$$

So what do these conditions mean? Let's take our first example into account again. If we permute a rational $$q$$ by $$2$$ and then permute the rational $$2q$$ by $$3$$ it has to be the same as permuting $$q$$ by $$6$$ from the very beginning. Of course, in this example when we say permute we really mean multiply. So the second condition pretty much says that the way $$g_2$$ will permute $$g_1 *x $$ must be the same as the way the group element $$g_2 g_1$$ will permute $$x$$.


Now, what about the first condition? This one implies that the identity element of our group should map any element of our set to itself. What this means is the identity element induces the identity permutation of the set X. But wait! now if you think about it, every element $$g \in G$$ induces a permutation of the set $$X$$.

What we really are defining is a group homomorphism $$\rho : G \rightarrow S_X$$ where $$S_X$$ is the symmetrical group of the elements of $$X$$. The homomorphism $$\rho$$ takes an element $$g \in G$$ and maps it to a permutation $$\rho_g :X \rightarrow X $$ which is defined as $$\rho_g (x) = g * x$$. The reader should try to verify that indeed $$\rho$$ is a group homomorphism and every $$\rho_g$$ is indeed a permutation of $$X$$. 




We can see that this group homomorphism and our group action are pretty much the same thing. For every group homomorphism $$\rho : G \rightarrow S_X$$ we can define a group action on $$X$$ by $$g* x = \rho (g) (x)$$.

Let us now consider some more interesting examples.





In Galois theory we deal with roots of polynomials over fields and these fields usually contain $$\mathbb{Q}$$. Lets consider the polynomial $$x^4 +3$$. This polynomial splits completely over $$K = \mathbb{Q}(a,\zeta_4)$$ where $$a = i\sqrt[4]{3}$$ and $$\zeta_4$$ is a primitive 4th root of unity. We have the factorization:

$$x^4 + 3 = (x-a)(x- \zeta_4 a)(x-\zeta^2_4 a) (x-\zeta^3_4 a) = (x-a)(x-ia)(x+a)(x+ia)$$

Lets consider our set $$X$$ to be the roots of this polynomial and our group in this example will be

$$G = Gal(K/\mathbb{Q}) = \{\sigma : K \rightarrow K | \quad \sigma \text{ is an automorphism of } K, \quad \sigma(q) = q \quad \forall q \in \mathbb{Q} \}$$

where the group operation is the usual composition of functions. Therefore, our group action this time is simply:




$$G \times X \longrightarrow X$$


$$(\sigma , x) \longmapsto \sigma(x)$$



So we are pretty much permuting the roots of the polynomial. Another way to see this is if $$b$$ is a root of a polynomial with coefficients over $$\mathbb{Q}$$ such as:

$$a_n b^n + a_{n-1} b^{n-1} + \ldots + a_1 b + a_0 = 0$$

then applying an automorphism $$\sigma$$ such that $$\sigma(q) = q$$ for every $$q \in \mathbb{Q}$$ we will get:

$$ a_n (\sigma(b))^n + \ldots + a_1 \sigma(b) + a_0 = \sigma(0) = 0 $$

and therefore $$\sigma(b)$$ is another root of the same polynomial! But we are not really permuting the roots in every possible way. Since $$\zeta_4 = i$$ and $$i^2 = -1$$ is a rational number, then $$\sigma(i)^2 = \sigma(i^2) = \sigma(-1) = -1$$. So we can only map $$i$$ to itself or to $$-i$$. Since $$a^4 = 3$$ we can pretty much map $$a$$ only to itself, $$-a, ia,-ia$$. Taking for granted the standard fact in Galois Theory that the $$\mathbb{Q}$$-automorphisms of $$K$$ are fully defined by where they map the elements $$a,\zeta_4$$, we get that our group $$G$$ is isomorphic to $$D_4$$ the dihedral group with 8 elements.

One could argue this underlying group action, this way of permuting roots of polynomials, is the essense of Galois Theory. If $$X$$ is the set of roots of an irreducible polynomial in $$\mathbb{Q}[x]$$ then $$Gal(\mathbb{Q}(X)/\mathbb{Q})$$ is isomorphic to a subgroup of $$S_n$$ where $$n$$ is the number of distinct roots. Just like in our previous example! $$G\simeq D_4 \simeq <(1234),(12)(34)> \leq S_4$$.

In all this lies the reason why we cant solve 5th degree polynomials with radicals. Polynomials of degree 5 induce groups $$Gal(K/\mathbb{Q})$$ that are isomorphic to subgroups of $$S_5$$. Depending which subgroup we are talking about, problems arise along with the fact that the group $$S_5$$ is not solvable. If there was a formula solving all 5th degree polynomials, well that would contradict the previous fact.

Now another interesting group action for the end of this post. With a taste of combinatorics. The dihedral group 4 $$D_4$$ we mentioned previously is the group of symmetries of the square. The group presentation is $$D_4 = <a,b: a^4 = b^2 = e, ab = ba^{-1}>$$. So we could say the groups elements are $$\{e,a,a^2,a^3,b,ba,ba^2,ba^3\}$$. What does this mean visually?


![texture theme preview](images/rotations.gif)



![texture theme preview](images/reflexion.gif)




[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
