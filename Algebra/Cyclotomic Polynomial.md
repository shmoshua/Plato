#Definition #Algebra 

> [!definition]
> The ***$n$-th cyclotomic polynomial*** $\Phi_{n}(x)$ is the polynomial in $K[X]$ whose roots are exactly the [[Roots of Unity|$n$-th primitive roots of unity]].
---
##### Properties
> [!lemma] Lemma 1
> We have that $x^n-1=\prod_{d|n}^{}\Phi_{d}(x)$.

> [!proof]-
> $$x^n-1=\prod_{\alpha\in\mu_{K}(n)}^{}(x-\alpha)=\prod_{d|n}^{}\prod_{\alpha\in \mu_{K}(d),\text{primitive}}(x-\alpha)=\prod_{d|n}^{}\Phi_{d}(x)$$
---
> [!lemma] Theorem 2
> For $n\geq 1$, 
> 1. $\Phi_{n}(x)$ is a monic irreducible polynomial in $\mathbb{Z}[X]$ of degree $\varphi(n)$. 
> 2. $[\mathbb{Q}(\xi_{n}):\mathbb{Q}]=\varphi(n)$
> 3. The map: $$(\mathbb{Z} / n\mathbb{Z})^\times\to \text{Gal}(\mathbb{Q}(\xi_{n}):\mathbb{Q}), \quad a\text{ mod }n\mapsto (\xi_{n}\mapsto \xi_{n}^a)$$is a group isomorphism.

> [!proof]-
> We prove this using induction. 
> 1. If $n=1$, then $\Phi_{1}(x)=x-1$ and it is monic irreducible of degree $\varphi(1)=1$.
> 2. if $n>1$, then, $$\Phi_{n}(x)\cdot \underbrace{ \prod_{d|n,d<n}^{}\Phi_{d}(x) }_{ =:f }=x^n-1$$As $f$ is a monic polynomial 
> 3. 
---
