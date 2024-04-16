#Definition #Algebra 
> [!definition]
> A ***finite field*** is a [[field]] that is finite.
---
##### Properties
> [!lemma] Theorem 1
> For a field $F$, 
> 1. any finite subgroup $G\leq F^{*}$ is [[Cyclic Groups|cyclic]].
> 2. if $F$ is finite, $F^{*}$ is cyclic.

> [!proof]-
> Let $n=e(G)$, the [[Exponent of a Group|exponent]] of $G$. Then, $\alpha^n=1$ for all $\alpha\in G$. Since $x^n-1$ has at most $n$ roots, $\left| G \right|\leq n$. But $n=e(G)\leq \left| G \right|$. However, by [[Exponent of a Group|Theorem 1]], there exists $g\in G$ with $\text{ord}(g)=e(G)$. This proves that $G$ is cyclic.
- **Corollary**: If $L:K$ is an extension of finite fields, then $L:K$ is [[Field Extension|simple]], since if $\braket{ \alpha  }=L^{*}$, then $L=K(\alpha)$.
---
> [!lemma] Theorem 2
> Every finite field $F$ is isomorphic to $\mathbb{F}_{p}[X] / (f(x))$ for some prime $p$ and irreducible monic $f\in \mathbb{F}_{p}[X]$

> [!proof]+
> Let $\alpha$ be the generator of $F^{*}$ and consider $E_{\alpha}:\mathbb{F}_{p}[X]\to F,g(x)\mapsto g(\alpha)$.
---
> [!lemma] Theorem 3
> Every irreducible polynomial $f\in \mathbb{F}_{p}[X]$ of degree $n$ divides $x^{p^n}-x$ and is separable.
---
> [!lemma] Theorem 4
> A subfield of $\mathbb{F}_{p^n}$has order $p^d$ where $d|n$ and there exists one such field for every divisor $d|n$.
---