#Definition #RepresentationTheory 

> [!definition]
> A [[representation]] $V$ of an [[Associative Algebra|associative $K$-algebra]] $A$  is ***semisimple*** if it is a direct sum of [[Representation|irreducible representations]].
---
##### Properties
> [!lemma] Proposition 1
> Let $\{ V_{i} \}_{1\leq i\leq m}$ be irreducible finite-dimensional pairwise non-isomorphic representations of $A$, and let $W$ be a subrepresentation of $$V:=\bigoplus_{i=1}^mn_{i}V_{i} $$Then, 
> 1. $W$ is isomorphic to $\bigoplus_{i=1}^mr_{i}V_{i}$ where $r_{i}\leq n_{i}$ and 
> 2. the inclusion $\phi:W\to V$ is a direct sum of inclusions $\phi_{i}:r_{i}V_{i}\to n_{i}V_{i}$ given by multiplication: $$\phi_{i}(v_{1},\dots,v_{r_{i}})=(v_{1},\dots,v_{r_{i}})X_{i}$$for $X_{i}\in \text{M}_{r_{i},n_{i}}(K)$.

> [!proof]-
> We will prove by induction over $n:=\sum_{i=1}^{m}n_{i}$. If $n=1$, the statement is clear.
> 
> Assume that $W$ is non-zero and fix an irreducible representation $P\subseteq W$, which exists per [[Representation|Proposition 1]]. Now by [[Representation Homomorphism|Schur's lemma]], $P$ is isomorphic to $V_{i}$ for some $i$ and the inclusion $$\phi|_{P}:P\to V$$
> Now note that the group $G_{i}:=\text{GL}_{n_{i}}(K)$ acts on $n_{i}V_{i}$ by $(v_{1},..,v_{n_{i}})\to(v_{1},\dots,v_{n_{i}})g_{i}$ and therefore acts on the set of subrepresentations of $V$, preserving the property we need to establish: namely, under the action of $g_{i}$, the matrix $X_{i}$ goes to $X_{i}g_{i}$, while the matrices $X_{j}$, $j\neq i$, don’t change. Take $g_{i}\in G_{i}$ such that $(q_{1},..,q_{n_{i}})g_{i}=(1,0,\dots,0)$. Then $Wg_{i}$ contains the first summand $V_{i}$ of $n_{i}V_{i}$ (namely, it is $Pg_{i}$); hence $Wg_{i}=V_{i}\oplus W'$, where $W'\subseteq n_{1}V_{1}\oplus\dots \oplus(n_{i}-1)V_{i}\oplus\dots \oplus n_{m}V_{m}$ is the kernel of the projection of $Wg_{i}$ to the first summand $V_{i}$ along the other summands. Thus the required statement follows from the induction assumption.
---
> [!lemma] Corollary 2
> Let $V$ be an irreducible finite dimensional representation of $A$ and let $v_{1},\dots,v_{n}\in V$ be any linearly independent vectors. Then, for any $w_{1},\dots,w_{n}\in V$, there exists $a\in A$ s.t. $av_i=w_{i}$

> [!proof]-
> Assume otherwise. Then, for $f:A\to nV,a\mapsto(av_{1},\dots,av_{n})$ the image $\text{Im }f$ is a proper subrepresentation and corresponds to an $r \times n$ matrix $X$ with $r<n$.
> 
> Therefore, there exists $u_{1},..,u_{r}\in V$ s.t. $(u_{1},\dots,u_{r})X=(v_{1},\dots,v_{n})$. This shows that $v_{1},\dots,v_{n}$ are not linearly independent which is a contradiction.
---
> [!lemma] Theorem 3 (Density Theorem)
> We have: 
> 1. Let $V$ be an irreducible finite dimensional representation of $A$. Then, $\rho:A\to \text{End}(V)$ is surjective.
> 2. Let $V:=\bigoplus_{i=1}^rV_{i}$ where $V_{i}$ are irreducible finite-dimensional non-isomorphic representations of $A$. Then, $$\bigoplus _{i=1}^r\rho_{i}:A\to\bigoplus _{i=1}^r\text{End}(V_{i})$$is surjective.

> [!proof]-
> We have: 
> 1. Let $B=\rho(A)$. Let $c\in \text{End}(V)$, let $v_{1},\dots,v_{n}$ be a basis of $V$, and let $w_{i}=cv_{i}$. By Corollary 2, there exists $a\in A$ such that $av_{i}=w_{i}$. Then $a$ maps to $c$, so $c\in B$.
> 2. Let $B_{i}:=\rho_{i}(A)$ and let $B:=\bigoplus _{i=1}^r\rho_{i}(A)$. Recall that as a representation of $A$, $\bigoplus _{i=1}^r\text{End}(V_{i})$ is semisimple: it is isomorphic to $\bigoplus _{i=1}^r d_{i}V_{i}$, where $d_{i}=\text{dim}V_{i}$. Then, by Proposition 1, $B=\bigoplus _{i=1}^rB_{i}$. On the other hand, 1 implies that $B_{i}=\text{End}(V_{i})$. Thus 2 follows.
---
