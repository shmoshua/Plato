#Definition #DifferentialGeometry  

> [!definition]
> Let $M,N$ be [[Smooth Manifold|smooth manifolds]]. Then, a map $f:M\to N$ is called a ***diffeomorphism*** if: 
> 1. $f$ is bijective.
> 2. $f,f^{-1}$ are [[Smooth Function|smooth]].
- **Related definition**: For a diffeomorphism $f:M\to N$, $M,N$ are ***diffeomorphic***.
- **Remark**: if $f$ is a diffeomorphism, $d_{p}f$ is an isomorphism.
---
##### Properties
> [!lemma] Lemma 1
> We have that:
> 1. if $M$ and $N$ are diffeomorphic, they have the same dimension.
> 2. a diffeomorphism $f:M\to N$ is a [[Homeomorphism]].
> 3. $\text{Diff}(M):=\{ f:M\to M|f \text{ is a diffeomorphism} \}$ is a group.

> [!proof]-
> We have:
> 1. Obvious.
> 2. Follows from [[Smooth Function|smooth functions being continuous]].
> 3. $\text{id}_{M}$ is a diffeomorphism, for a diffeomorphism $f$, $f^{-1}$ is diffeomorphism and of course the composite of diffeomorphisms is a diffeomorphism.
---
> [!lemma] Lemma 2
> For $f:M\to N$, TFAE:
> 1. $f$ is a diffeomorphism.
> 2. $f$ is bijective and $d_{p}f$ is bijective for all $p\in M$.
> 3. $f$ is bijective and $f$ is a local diffeomorphism.

> [!proof]-
> We have:
> 1. (1=>2): Clear.
> 2. (2=>3): By [[Local Diffeomorphism|inverse function theorem]].
> 3. (3=>1): From [[Local Diffeomorphism|Proposition 2.6]].
---
##### Examples
> [!h] Example 1
> If $(M,\mathcal{X})$ is a smooth manifold, $x:U\to x(U)$ is a [[diffeomorphism]]. 