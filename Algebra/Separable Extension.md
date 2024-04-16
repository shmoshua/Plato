#Definition #Algebra 

> [!definition]
> For a [[field]] $F$, 
> 1. a polynomial $g\in F[X]$ is called ***separable*** over $F$ if each of its irreducible factors has distinct roots in a splitting field.
> 2. an algebraic element $\alpha$ over $F$ is called ***separable*** over $F$ if $m_{\alpha,F}$ is separable over $F$.
> 3. an algebraic extension $K:F$ is called ***separable*** if every $\alpha\in K$ is separable.
---
##### Properties
> [!lemma] Lemma 1
> Let $L:K$ be a separable algebraic extension and $M$ an intermediate field. Then, both $L:M$ and $M:K$ are separable.

> [!proof]-
> Clearly, $M:K$ is separable by definition. Now, let $\alpha\in L$ and $m_{\alpha,K}$ and $m_{\alpha,L}$ be the minimal polynomials of $\alpha$ over $K,L$ respectively. Then, $m_{\alpha,M}|m_{\alpha,K}$ in $M[X]$.
> 
> As $\alpha$ is separable over $K$, $m_{\alpha,K}$ has distinct roots. Therefore, $m_{\alpha,M}$ also has distinct roots hence $L:M$ is separable.
---
##### Examples
> [!h] Example 1
> Let $\Phi_{p}(x):=x^{p-1}+\dots+1$. Then, the roots are all distinct as $\exp\left( \frac{2\pi ik}{p} \right)$ and it is separable.
---
> [!h] Example 2
> Consider $f(x):=x^p-t\in \mathbb{Z}_{p}(t)[X]$ for $p$ prime. Then, 
> 1. $f$ is irreducible.
> 2. $f$ is not separable over $\mathbb{Z}_{p}(t)$.

> [!proof]+
> Let $\alpha$ be a root of $f$. Then, $\alpha^p=t$ and: $$(x-\alpha)^p=x^p-\alpha^p=x^p-t$$If $\beta$ is another root, then $0=(\beta-\alpha)^p$ and $\alpha=\beta$.
> 
> Assume that $f$ is not irreducible and $f=gh$ where $\deg g,\deg h<\deg f$. Then, as $f(x)=(x-\alpha)^p$, $g(x)=(x-\alpha)^s$ for $0<s<p$ as the factorization is unique with $\alpha^s\in \mathbb{Z}_{p}(t)$. As $s$ and $p$ are relatively prime, there exists $a,b$ s.t. $$as+bp=1$$Then, $\alpha=\alpha^{as}\alpha^{bp}\in \mathbb{Z}_{p}(t)$. 