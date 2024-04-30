#Definition #Algebra 

> [!definition]
> A [[field extension]] $L:K$ is ***Galois***, if $L:K$ is [[Separable Extension|separable]] and [[Normal Extension|normal]].
---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be finite. Then, the following are equivalent:
> 1. $L:K$ is Galois.
> 2. $\left| \text{Gal}(L:K) \right|=[L:K]$

> [!proof]-
> Assume that $L:K$ is Galois. Then, it is separable and $$\left| \text{Hom}_{K}(L,\overline{L}) \right| =[L:K]$$Also, as $L:K$ is normal, $$\text{Hom}_{K}(L,\overline{L})=\text{Hom}_{K}(L,L)=\text{Aut}_{K}(L)=\text{Gal}(L:K)$$
---
> [!lemma] Theorem 2
> Let $L$ be a field and $G\leq \text{Aut}(L)$ a finite subfield of $\text{Aut}(L)$. Let $L_{0}:=\text{Fix}(G)=L^G=\phi(G)$. Then, $$[L:L_{0}]=[L:L^G]=\left| G \right| $$

> [!proof]+
> First, suppose that $[L:L^G]=:m<n=:\left| G \right|$. Let $\{ w_{1},\dots,w_{m} \}$ be the basis of $L$ over $L_{0}$. Let $G=\{ \sigma_{1},\dots,\sigma_{n} \}$ and consider the system: $$\sigma_{1}(w_{j})y_{1}+\dots+\sigma_{n}(w_{j})y_{m}=0$$for all $j\in [m]$. Then, as there are more unknowns than the number of equations, there exists a non-trivial solution $y_{i}\in L$. Therefore, we have that: $$y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n}=0$$
---
##### Examples
> [!h] Example 1 (Finite Fields)
> Every extension $L:K$ of finite fields is Galois. Then, $$\text{Gal}(L:K)\cong \mathbb{Z} / {[L:K]\mathbb{Z}}$$
---
