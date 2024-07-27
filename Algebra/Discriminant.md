#Definition #Algebra 

> [!definition]
> Let $f\in K[X]$ be a degree $n$ polynomial with $\alpha_{1},\dots,\alpha_{n}$ as roots in its [[splitting field]]. The ***discriminant*** of $f$ is the value: $$D_{f}:=\left( \prod_{1\leq i<j\leq n}^{}(\alpha_{j}-\alpha_{i}) \right) ^{2}=:\delta_{f}^{2}$$
---
##### Properties
> [!lemma] Lemma 1
> Let $K$ be a field and $f\in K[X]$ a polynomial with $\alpha_{1},\dots,\alpha_{n}$ as roots in its splitting field $L_{f}$. Suppose $\sigma\in \text{Gal}(L:K)$. Then,
> $$\sigma(\delta_{f})=\begin{cases}\delta_{f}&\sigma|_{\text{R}(f)}\text{ is even}.\\-\delta_{f}&\sigma|_{\text{R}(f)}\text{ is odd}.\end{cases}$$

> [!proof]-
> Notice that for each transposition between two roots $\alpha_{k}$ and $\alpha_{\ell}$, the sign switches: Assume wlog that $k<\ell$. Then, 
> 
> $$\sigma(\delta_{f})=\prod_{1\leq i<j\leq n}^{}(\sigma(\alpha_{j})-\sigma(\alpha_{i}))=-\delta_{f}$$
> 
> Hence, the statement follows.
---
> [!lemma] Theorem 2
> Let $K$ be a field with $\text{char }K\neq 2$. For $f\in K[X]$ of degree $n$ and its [[Splitting Field|splitting field]] $L_{f}:K$ of $f$,
> 1. if $D_{f}=0$, then $f$ has a repeated roots in $L_{f}$.
> 2. if $D_{f}\neq 0$ then $K(\delta_{f})=\text{Fix}(\text{Gal}(L_{f}:K)\cap A_{n})$. Further, TFAE:
> 	1. $\text{Gal}(L_{f}:K)\subseteq A_{n}$.
> 	2. $\delta_{f}\in K$.
> 	3. $D_{f}$ has a square root in $K$.
> 	   

> [!proof]+
> We have:
> 1. if $f$ has no repeated roots, $\alpha_{j}-\alpha_{i}\neq 0$ for all $i,j$. Therefore, $D_{f}\neq 0$.
> 2. if $f$ has repeated roots then $D_{f} =0$. Hence, the $f$ is separable and notice that for $\sigma\in \text{Gal}(L_{f}:K)\cap A_{n}$ from Lemma 1, $\sigma(\delta_{f})=\delta_{f}$. Hence, $\delta_{f}\in \text{Fix}(\text{Gal}(L_{f}:K)\cap A_{n})$ and $K(\delta_{f})\subseteq \text{Fix}(\text{Gal}(L_{f}:K)\cap A_{n})$.
>    
>    Conversely, if 
---
##### Examples
> [!lh] Example 1
> For a reduced cubic polynomial $f(x)=x^3+qx+r$, $D_{f}=-4q^3-27r^{2}$.
> 1. for $f(x)=x^3-3x-1$, $D_{f}=81$ and by Theorem 1, $\text{Gal}(L_{f}:K)=A_{3}$.