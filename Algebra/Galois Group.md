#Definition #Algebra 
> [!definition]
> Let $K$ be a [[Field|subfield]] of $L$. An [[Ring Homomorphism|automorphism]] $\sigma\in \text{Aut}(L)$ is called a ***$K$-automorphism*** of $L$ is $$\sigma|_{K}=\text{id}_{K}$$Then, 
> 1. the ***Galois group  of $L:K$*** is the group of all $K$-automorphism of $L$, denotes as $\text{Gal}(L : K)$ or $\text{Aut}_{K}L$.
> 2. the ***Galois group of $f\in K[X]$*** is $\text{Gal}(L : K)$ where $L$ is the splitting field of $f$ over $K$.
---
##### Properties
> [!lemma] Theorem 1
> For a field extension $L:K$, the set of all $K$-automorphisms of $L$ forms a [[group]] with composition.

> [!proof]-
> If $\sigma,\gamma \in \text{Aut}_{K}L$, then clearly $\sigma \circ\gamma\in \text{Aut}(L)$ and if $k\in K$, $$(\sigma \circ \gamma)(k)=\sigma(\gamma(k))=\sigma(k)=k$$Further, $\text{id}_{L}\in \text{Aut}_{K}(L)$ and for $\sigma ^{-1}\in \text{Aut}(L)$, $$\sigma ^{-1}(k)=(\sigma ^{-1}\circ \sigma)(k)=k$$
---
##### Examples
> [!h] Example 1
> Let $\sigma\in \text{Gal}(\mathbb{C} :\mathbb{R})$ and $j:=\sigma(i)$. Then, 
> 1. 