#Definition #Algebra 

> [!definition]
> For a [[field]] $F$, 
> 1. a polynomial $g\in F[X]$ is called ***separable*** over $F$ if factors into distinct linear factors in its splitting field.
> 2. an [[Algebraic and Geometric Multiplicity|algebraic element]] $\alpha$ over $F$ is called ***separable*** over $F$ if $m_{\alpha,F}$ is separable over $F$.
> 3. an [[Algebraic and Transcendental Element|algebraic extension]] $K:F$ is called ***separable*** if every $\alpha\in K$ is separable.
- **Related definition**: For a field $F$ and $f(x):=\sum_{i=0}^{n}a_{i}x^i\in F[X]$, the ***derivative*** of $f$ is given as: $$f'(x):=\sum_{i=1}^{n}ia_{i}x^{i-1}$$
---
##### Properties
> [!lemma] Lemma 1
> Let $L:M:K$ and $L:K$ is separable. Then, 
> 1. both $L:M$ and $M:K$ are separable.

> [!proof]-
> Clearly, $M:K$ is separable by definition. 
> 
> Now, let $\alpha\in L$. As $\alpha\in L$ is algebraic over $K$, it is also algebraic over $M$ and we have that: $m_{\alpha,M}|m_{\alpha,K}$ in $M[X]$. As $\alpha$ is separable over $K$, $m_{\alpha,K}$ has distinct roots in its splitting field and so does $m_{\alpha,M}$. 
> 
---
> [!lemma] Proposition 2
> For a non-constant polynomial $f\in F[X]$, TFAE:
> 1. $f$ is not separable.
> 2. $f$ and $f'$ have a common root in its splitting field.

> [!proof]-
> We have:
> 1. (1=>2): if $f$ is not separable, for its splitting field $L$, there exists $\alpha\in L$ s.t. the multiplicity of $\alpha$ is $\geq 2$, i.e. $(x-\alpha)^2|f(x)$ in $L(x)$, i.e. $f(x)=(x-\alpha)^{2}g(x)$ for some $g(x)\in L[X]$. Hence, $$f'(x)=2(x-\alpha)g(x)+(x-\alpha)^{2}g'(x)=(x-\alpha)(2g(x)+(x-\alpha)g'(x))$$and $\alpha$ is a root of $f'$ as well.
> 2. (2=>1): if $\alpha$ is a root of $f,f'$ in some splitting field $L$, then $f(x)=(x-\alpha)g(x)$ in $L[X]$ and $f'(x)=(x-\alpha)g'(x)+g(x)$. However, as $(x-\alpha)|f'(x)$, $(x-\alpha)|g(x)$ and this proves the statement.

- **Corollary**: An irreducible polynomial $0\neq f$ is separable if and only if $\text{gcd}(f,f')=1$. 
---
> [!lemma] Theorem 3
> For any field $F$, 
> 1. an [[Integral Domain|irreducible polynomia]]l $f\in F[X]$ is separable if and only if $f'\not\equiv 0$ in $F[X]$.
> 1. if $\text{char }F=0$, then every irreducible polynomial is separable. 
> 2. if $\text{char }F=p$, then an irreducible $f$ is separable if and only if it is not a polynomial in $x^p$.

> [!proof]-
> We have:
> 1. Let $0\neq f\in F[X]$ be irreducible. Then, $f$ is separable if and only if $\gcd(f,f')=1$. If $f,f'$ are not relatively prime, then $\gcd(f,f')=g$ with $\deg(g)>1$ and as $f$ is irreducible, $g=cf$ for some $c\in F^\times$ and $f|f'$. However, as $\deg(f')<\deg f$, this can happen only if $f'=0$.
> 	
> 	Conversely, if $f'=0$, then $\gcd(f,f')=f$ is non-constant. Hence, $f$ is not separable by the corollary.
> 2. if $\text{char }F=0$, then for any irreducible polynomial $f\in F[X]$, $f$ is non-constant and $f'\neq 0$. Therefore, every irreducible polynomial is separable.
> 3. let $\text{char }F=p$. If $f$ is not separable, then $f'(x)=\sum_{i=1}^{n}ia_{i}x^{i-1}=0$, i.e. $ia_{i}=0$ for all $i\in [n]$. Hence, if $p\nmid i$, then $a_{i}=0$. Therefore, $$f(x)=a_{mp}x^{mp}+\dots+a_{p}x^p+a_{0}=g(x^p)$$where $g(x)=a_{mp}x^m+\dots+a_{0}$. 
> 
> 	Conversely, if $f(x)=g(x^p)$, then, $f'(x)=px^{p-1}g'(x^p)=0$ in $F$.
- **Corollary**: any field $F$ with $\text{char }F=0$ is separable.
---
> [!lemma] Proposition 4
> Every irreducible polynomial over a [[finite field]] $F$ is separable.

> [!proof]+
> Let $f\in F[X]$ be irreducible. Assume that $f$ is inseparable. Then,  $f(x)=g(x^p)$ where: $$g(x)=b_{n}x^n+\dots+b_{0}\in F[X]$$However, by [[Frobenius Homomorphism|Corollary]], $$g(x)=c_{n}^px^n+\dots+c_{0}^p\in F[X]$$Therefore, $$f(x)=g(x^p)=c_{n}^px^{np}+\dots+c_{0}^p=(c_{n}x^n+\dots+c_{0})^p$$and $f$ is reducible, which is a contradiction.
---
##### Examples
> [!h] Example 1
> Let $\Phi_{p}(x):=x^{p-1}+\dots+1$. Then, 
> 1. the roots are all distinct as $\exp\left( \frac{2\pi ik}{p} \right)$ and it is separable.
---
> [!h] Example 2
> Consider $f(x):=x^p-t\in \mathbb{Z}/p\mathbb{Z}(t)[X]$ for $p$ prime. Then, 
> 1. $f$ is not inseparable over $\mathbb{Z} / p\mathbb{Z}(t)$.
> 1. $f$ is irreducible.

> [!proof]-
> We have:
> 1. Let $\alpha$ be a root of $f$. Then, $\alpha^p=t$ and: $$(x-\alpha)^p=x^p-\alpha^p=x^p-t$$If $\beta$ is another root, then $0=(\beta-\alpha)^p$ and $\alpha=\beta$.
> 2. Assume that $f$ is not irreducible and $f=gh$ where $\deg g,\deg h<\deg f$. Then, for a root $\alpha$ of $f$ as $f(x)=(x-\alpha)^p$, $g(x)=(x-\alpha)^s$ for $0<s<p$ as the factorization is unique. Hence, we have that $\alpha^s\in \mathbb{Z} /p\mathbb{Z}(t)$. As $s$ and $p$ are relatively prime, there exists $a,b$ s.t. $$as+bp=1$$Then, $\alpha=\alpha^{as}\alpha^{bp}\in \mathbb{Z} /p\mathbb{Z}(t)$ and there exists $u(t),v(t)\in \mathbb{Z} / p\mathbb{Z}[t]$ s.t. $\alpha=\frac{u(t)}{v(t)}$. But as $\alpha^p=t$, $$u^p(t)-tv^p(t)=0$$which cannot happen as the terms are of different degree.
---
