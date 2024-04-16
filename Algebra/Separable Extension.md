#Definition #Algebra 

> [!definition]
> For a [[field]] $F$, 
> 1. a polynomial $g\in F[X]$ is called ***separable*** over $F$ if each of its irreducible factors has distinct roots in a splitting field.
> 2. an algebraic element $\alpha$ over $F$ is called ***separable*** over $F$ if $m_{\alpha,F}$ is separable over $F$.
> 3. an algebraic extension $K:F$ is called ***separable*** if every $\alpha\in K$ is separable.
- **Related definition**: For a field $F$ and $f(x):=\sum_{i=0}^{n}a_{i}x^i\in F[X]$, the ***derivative*** of $f$ is given as: $$f'(x):=\sum_{i=1}^{n}ia_{i}x^{i-1}$$
---
##### Properties
> [!lemma] Lemma 1
> Let $L:K$ be a separable algebraic extension and $M$ an intermediate field. Then, both $L:M$ and $M:K$ are separable.

> [!proof]-
> Clearly, $M:K$ is separable by definition. Now, let $\alpha\in L$ and $m_{\alpha,K}$ and $m_{\alpha,L}$ be the minimal polynomials of $\alpha$ over $K,L$ respectively. Then, $m_{\alpha,M}|m_{\alpha,K}$ in $M[X]$.
> 
> As $\alpha$ is separable over $K$, $m_{\alpha,K}$ has distinct roots. Therefore, $m_{\alpha,M}$ also has distinct roots hence $L:M$ is separable.
---
> [!lemma] Proposition 2
> A non-constant polynomial $f\in F[X]$ has a root $\alpha$ with multiplicity $\geq 2$ in a splitting field if and only if $\alpha$ is a root of both $f$ and $f'$.

> [!proof]-
> Let $\alpha$ is a root of multiplicity $n\geq 2$ in a splitting field $K$. Then, $f(x)=(x-\alpha)^ng(x)\in K[X]$ and: $$f'(x)=n(x-\alpha)^{n-1}g(x)+(x-\alpha)^ng'(x)=(x-\alpha)(n(x-\alpha)^{n-2}g(x)+(x-\alpha)^{n-1}g'(x))$$Therefore, $\alpha$ is also a root of $f'$.
> 
> Conversely, if $\alpha$ is a root of both $f,f'$, then, $f(x)=(x-\alpha)h(x)\in K[X]$ and: $$f'(x)=h(x)+(x-\alpha)h'(x)$$As $(x-\alpha)|f'(x)$, $(x-\alpha)|h(x)$ and this proves the statement.
- **Corollary**: A polynomial $0\neq f$ is separable if and only if $\text{gcd}(f,f')=1$. 
---
> [!lemma] Theorem 3
> For any field $F$, an irreducible polynomial $f\in F[X]$ is separable if and only if $f'\not\equiv 0$ in $F[X]$. In particular, 
> 1. if $\text{char }F=0$, then every irreducible polynomial is separable and 
> 2. if $\text{char }F=p$, then $f$ is separable if and only if it is not a polynomial in $x^p$.

> [!proof]-
> Let $0\neq f\in F[X]$ be irreducible. Then, $f$ is separable if and only if $\text{gcd}(f,f')=1$. If $f,f'$ are not relatively prime, then since $f$ is irreducible, $f|f'$. However, as $\deg(f')<\deg f$, $f|f'$ can happen only if $f'=0$. 
> 
> Conversely, if $f'=0$, then $\gcd(f,f')=f$ is non-constant. Hence, $f$ is inseparable by the Corollary above. 
> 
> If $\text{char }F=0$, $f$ is not the constant polynomial and $f'\neq 0$. Therefore, every irreducible polynomial is separable.
> 
> If $\text{char }F\neq 0$ and assume $f'(x)=\sum_{i=1}^{n}ia_{i}x^{i-1}=0$. Then, $ia_{i}=0$ for all $i\in[n]$. Then, if $p\nmid i$, $a_{i}=0$. Therefore, $$f(x)=a_{mp}x^{mp}+\dots+a_{p}x^p+a_{0}=g(x^p)$$where $g(x)=a_{mp}x^m+\dots+a_{0}$. 
> 
> Conversely, if $f(x)=g(x^p)$, then, $f'(x)=px^{p-1}g'(x^p)=0$ in $F$.
---
##### Examples
> [!h] Example 1
> Let $\Phi_{p}(x):=x^{p-1}+\dots+1$. Then, the roots are all distinct as $\exp\left( \frac{2\pi ik}{p} \right)$ and it is separable.
---
> [!h] Example 2
> Consider $f(x):=x^p-t\in \mathbb{Z}_{p}(t)[X]$ for $p$ prime. Then, 
> 1. $f$ is irreducible.
> 2. $f$ is not separable over $\mathbb{Z}_{p}(t)$.

> [!proof]-
> Let $\alpha$ be a root of $f$. Then, $\alpha^p=t$ and: $$(x-\alpha)^p=x^p-\alpha^p=x^p-t$$If $\beta$ is another root, then $0=(\beta-\alpha)^p$ and $\alpha=\beta$.
> 
> Assume that $f$ is not irreducible and $f=gh$ where $\deg g,\deg h<\deg f$. Then, as $f(x)=(x-\alpha)^p$, $g(x)=(x-\alpha)^s$ for $0<s<p$ as the factorization is unique with $\alpha^s\in \mathbb{Z}_{p}(t)$. As $s$ and $p$ are relatively prime, there exists $a,b$ s.t. $$as+bp=1$$Then, $\alpha=\alpha^{as}\alpha^{bp}\in \mathbb{Z}_{p}(t)$ and there exists $u(t),v(t)\in \mathbb{Z}_{p}[t]$ s.t. $\alpha=\frac{u(t)}{v(t)}$. But as $\alpha^p=t$, $$u^p(t)-tv^p(t)=0$$which cannot happen as the terms are of different degree.
---
