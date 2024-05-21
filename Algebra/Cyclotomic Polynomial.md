#Definition #Algebra 

> [!definition]
> The ***$n$-th cyclotomic polynomial*** $\Phi_{n}(x)$ is the polynomial in $K[X]$ whose roots are exactly the [[Roots of Unity|$n$-th primitive roots of unity]].
---
##### Properties
> [!lemma] Lemma 1
> We have that $x^n-1=\prod_{d|n}^{}\Phi_{n}(x)$.

> [!proof]-
> $$x^n-1=\prod_{\alpha\in\mu_{K}(n)}^{}(x-\alpha)=\prod_{d|n}^{}\prod_{\alpha\in \mu_{K}(d),\text{primitive}}(x-\alpha)=\prod_{d|n}^{}\Phi_{d}(x)$$
---
> [!lemma] Theorem 2
> The cyclotomic polynomial $\Phi_{n}(x)$ is a monic irreducible polynomial in $\mathbb{Z}[X]$ of degree $\varphi(n)$ 
---
