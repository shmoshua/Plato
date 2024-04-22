#Definition #RepresentationTheory 
> [!definition]
> Let $V_{1},V_{2}$ be two [[Representation|representations]] of an [[associative algebra]] $A$. A ***homomorphism*** or an ***intertwining operator*** $\phi:V_{1}\to V_{2}$ is a linear operator s.t. $$\phi(av)=a\phi(v),\quad\forall a\in A,v\in V_{1}$$
- **Related definition**: $\text{Hom}_{A}(V_{1},V_{2})$ denotes the space of all homomorphisms between $V_{1},V_{2}$.
- **Related definition**: A homomorphism $\phi$ is a ***representation isomorphism***, if it is a vector space isomorphism. Then, $V_{1}$ and $V_{2}$ are called ***isomorphic***.
---
##### Properties
> [!lemma] Proposition 1
> Let $\phi:V_{1}\to V_{2}$ be a representation isomorphism. Then, $\phi ^{-1}$ is also a  representation isomorphism.

> [!proof]-
> We have that for all $a\in A$ and $v\in V_{2}$, $$\phi (a\phi ^{-1}(v))=a\phi(\phi ^{-1}(v))=av=\phi(\phi ^{-1}(av))$$Therefore, $a\phi ^{-1}(v)=\phi ^{-1}(av)$.
---
> [!lemma] Proposition 2 (Schur's Lemma)
> Let $V_{1},V_{2}$ be representations of $A$ over any field $K$ (not necessarily [[Algebraic Closure|algebraically closed]]). Further $\phi:V_{1}\to V_{2}$ be a non-trivial representation homomorphism. Then, 
> 1. if $V_{1}$ is irreducible, $\phi$ is injective.
> 2. if $V_{2}$ is irreducible, $\phi$ is surjective.
> 3. if both $V_{1}$ and $V_{2}$ are irreducible, $\phi$ is an isomorphism.
