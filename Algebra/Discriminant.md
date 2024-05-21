#Definition #Algebra 

> [!definition]
> Let $f\in K[X]$ be a degree $n$ polynomial with $\alpha_{1},\dots,\alpha_{n}$ as roots. The ***discriminant*** of $f$ is the value: $$D_{f}:=\left( \prod_{1\leq i<j\leq n}^{}(\alpha_{j}-\alpha_{i}) \right) ^{2}$$
---
##### Properties
> [!lemma] Theorem 1
> Let $K$ be a field with $\text{char }K\neq 2$. For $f\in K[X]$ of degree $n$ and its [[Splitting Field|splitting field]] $L_{f}:K$ of $f$,
> 1. if $D_{f}=0$, then $f$ has no repeated roots in $L_{f}$.
> 2. if $D_{f}\neq 0$ and $D$ has a square root in $K$, then $\text{Gal}(L_{f}:K)\subseteq A_{n}$.
> 3. if $D_{f}$ has no square roots in $K$, it has a square root in $L_{f}$ and $\text{Gal}(L_{f}:K)\not\subseteq A_{n}$.
---
##### Examples
> [!lh] Example 1
> For a reduced cubic polynomial $f(x)=x^3+qx+r$, $D_{f}=-4q^3-27r^{2}$.
> 1. for $f(x)=x^3-3x-1$, $D_{f}=81$ and by Theorem 1, $\text{Gal}(L_{f}:K)=A_{3}$.