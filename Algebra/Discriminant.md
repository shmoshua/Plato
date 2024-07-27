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

> [!proof]-
> We have:
> 1. if $f$ has no repeated roots, $\alpha_{j}-\alpha_{i}\neq 0$ for all $i,j$. Therefore, $D_{f}\neq 0$.
> 2. if $f$ has repeated roots then $D_{f} =0$. Hence, the $f$ is separable and $L_{f}:K$ is Galois. Notice that for $\sigma\in \text{Gal}(L_{f}:K)\cap A_{n}$ from Lemma 1, $\sigma(\delta_{f})=\delta_{f}$. Hence, $\delta_{f}\in \text{Fix}(\text{Gal}(L_{f}:K)\cap A_{n})$ and $K(\delta_{f})\subseteq \text{Fix}(\text{Gal}(L_{f}:K)\cap A_{n})$.
>    
>    Conversely, we have that for $\sigma\in \gamma(K(\delta_{f}))$ as $\sigma|_{K}=\text{id}_{K}$, $\sigma\in \text{Gal}(L_{f}:K)$ and as $\sigma(\delta_{f})=\delta_{f}$, $\sigma\in A_{n}$. Hence, $\gamma(K(\delta_{f}))\subseteq \text{Gal}(L_{f}:K)\cap A_{n}$ and we have the statement.
> 
> 	Therefore, $$\text{Gal}(L_{f}:K)\subseteq A_{n}\iff K(\delta_{f})=K\iff\delta_{f}\in K\iff D_{f}\text{ has a square root in }K$$
---
##### Galois Group of Order 3 and 4
> [!lemma] Theorem 1 (Galois Group for Order 3 Polynomials)
> Let $f(x)\in K[X]$ be irreducible cubic. Then, $$\text{Gal}(L_{f}:K)=\begin{cases}A_{3}&D_{f}\text{ is square}. \\
S_{3}&\text{otherwise}\end{cases}$$


> [!proof]+
> Assume that $D_{f}\neq 0$. Let $\alpha$ be a root of $f$. As $f$ is irreducible, $[K(\alpha):K]=3$. But as $K(\alpha)\subseteq L_{f}$, we have that $3|[L:K]$ and as $f$ is separable and $L:K$ is Galois, 
---
##### Examples
> [!lh] Example 1
> For a reduced cubic polynomial $f(x)=x^3+qx+r$, $D_{f}=-4q^3-27r^{2}$.
---
> 1. for $f(x)=x^3-3x-1$, $D_{f}=81$ and by Theorem 1, $\text{Gal}(L_{f}:K)=A_{3}$.
> Let $f\in \mathbb{Q}[X]$ be an irreducible cubic. Then,
> 1. $f$ has exactly one real root if and only if $D_{f}<0$. In this case $\text{Gal}(L_{f}:K)\cong S_{3}$.
> 2. $f$ has three real roots if and only if $D_{f}>0$. In this case either $\delta_{f}\in \mathbb{Q}$ and $\text{Gal}(L_{f}:K)\cong A_{3}$ or $\delta_{f}\notin \mathbb{Q}$ and $\text{Gal}(L_f:K)\cong S_{3}$.