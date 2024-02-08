#Definition #Example #FunctionalAnalysis 

> [!definition]
> Let $G$ be a group which we consider as a measure space w.r.t the counting measure. Then, for a [[Hilbert Space|Hilbert space]] $\mathcal{H}$, a ***unitary representation*** of $G$ is an operator $$\pi:G \to \text{U}(\mathcal{H},\mathcal{H})$$ 
> If $\mathcal{H}=$ [[Lp Space|$L^2(X)$]] for a set $X$, we define $\pi:G \to \mathcal{B}(\mathcal{H})$ as:
> $$(\pi(a)f)(x)=f(a^{-1}x)$$
---
##### Properties
**Example 1:** $\mathcal{H}=\ell^2(G,\mathbb{C})=\left\{  f:G\to \mathbb{C}\left|\sum_{a\in G}^{}\left| f(a) \right|^{2}<+\infty \right. \right\}$
> [!Lemma] Proposition 1
> For any $a\in G$, we have that:
> 1. $\pi(a)^{*}=\pi(a^{-1})$
> 2. $\pi$ is a group homomorphism
> 3. $\pi(a)$ is a unitary operator.

>[!proof]-
> We have:
> 1. 
>$$\braket{ \pi(a)f ,g  } =\sum_{x\in G}^{}|f(a^{-1}x)\overline{g(x)}|=\sum_{y\in G}^{}|f(x)\overline{g(ax)}|=\braket{ f , \pi(a^{-1})g } $$
> 2. it holds that: $$(\pi(ab)f)(x)=f(b^{-1}a^{-1}x)=(\pi(b)f)(a^{-1}x)=(\pi(a)\pi(b)f)(x)$$
> 3. $\pi(a)\pi(a)^*=\pi(a)\pi(a^{-1})=\pi(e)=\iota$.
---
> [!lemma] Proposition 2
> For $a\in G$, $\pi(a)$ admits an eigenfunction if and only if $a$ has a finite order in $G$.

>[!proof]-
>If $a$ has finite order, there exists $n\geq 1$ s.t. $\pi(a)^n=\text{Id}$. 

---
**Example 2**: For $(X,d)$ compact metric space, let $G\curvearrowright X$ by isometry, i.e. $d(gx,gy)=d(x,y)$. Further, assume that $G$ preserves the positive [[Borel Measure|Borel regular]] measure $\mu$ on $X$ with $\mu(X)<+\infty$. We define $\mathcal{H}=L^2(X,\mu)$.

> [!lemma] Proposition 3
> For every $g\in G$ and $f\in L^2(X,\mu)$, $\pi(g)$ is unitary and further, $$\left\| \pi(g)f \right\| ^{2}=\left\| f \right\| ^{2}$$

> [!proof]-
> $$\left\| \pi(g)f \right\|_{2} ^{2}=\int_{X}^{}\left| (\pi(g)f)(x) \right|^{2}   \, d\mu(x)=\int_{X}^{} \left| f(g^{-1}x) \right| ^{2} \, d\mu(x) =\int_{X}^{} \left| f(x) \right| ^{2} \, d\mu(x)=\left\| f \right\|_{2} ^{2}  $$
---
> [!lemma] Proposition 4
> Let $K\in C(X\times X,\mathbb{C})$ be a continuous kernel s.t. $K(gx,gy)=K(x,y)$. Then, for all $g\in G$ and $T_{K}$ an [[Integral Operator|integral operator]]:$$\pi(g)T_{K}=T_{K}\pi(g)$$

> [!proof]+
> $$\begin{align}(\pi(g)T_{K}f)(x)=(T_{K}f)(g^{-1}x)&=\int_{X}^{} f(y)K(g^{-1}x,y) \, d\mu(y)\\&=\int_{X}^{} f(y)K(x,gy) \, d\mu(y) \\&=\int_{X}^{} f(g^{-1}y)K(x,y) \, d\mu(y)\\&=\int_{X}^{} (\pi(g)f)(y)K(x,y) \, d\mu(y)\\&=(T_{K}\pi(g)f)(x) \end{align} $$
---
> [!lemma] Theorem 5
> $L^{2}(X,\mu)$ is a direct orthogonal sum of $\pi(G)$-invariant (irreducible) finite dimensional subspaces.
---
##### Examples
- If $G=\mathbb{Z}$, we have Fourier series.