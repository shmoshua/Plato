#Definition #Algebra 

> [!definition]
> A [[field]] $K$ is called ***algebraically closed*** if every non-constant polynomial $f\in K[X]$ has a root in $K$. Then, an extension $K:F$ is the ***algebraic closure*** of $F$, denoted as $\overline{F}$, if:
> 1. $K$ is [[Algebraic and Transcendental Element|algebraic]] over $F$ and 
> 2. $K$ is algebraically closed.
- **Remark**: Let $F$ be algebraically closed. Then, as $F$ is algebraic over $F$, $\overline{F}=F$.
---
##### Properties
> [!lemma] Theorem 1
> Let $K$ be a field. Then, TFAE:
> 1. $K$ is algebraically closed. 
> 2. every non-constant polynomial $f\in K[X]$ splits over $K$.
> 3. every irreducible polynomial $f\in K[X]$ is linear.
> 4. $K$ has no proper algebraic extension.

> [!proof]-
> We have:
> 1. (1=>2): Let $f\in K[X]$ be a non-constant polynomial and $\alpha\in K$ a root of $f$. Then, $f(x)=(x-\alpha)g(x)$ with $g\in K[X]$. Then, we can proceed with induction.
> 2. (2=>3): Let $f$ be irreducible. Then, it is non-constant and splits over $K$. However, as $f$ is irreducible, $f$ is linear.
> 3. (3=>4): Let $L$ be an algebraic extension of $K$. Then, for $\alpha\in L$, the minimal polynomial $m_{\alpha,K}$ is irreducible and therefore linear. Hence, $m_{\alpha,K}(x)=x-\alpha$ and $\alpha\in K$.
> 4. (4=>1): Let $f\in K[X]$ be a non-constant polynomial. Then, $K(\alpha):K$ is an algebraic extension and $K(\alpha)=K$. Hence, $\alpha\in K$.
---
> [!lemma] Theorem 2
> We have: 
> 1. for any field $F$, there exists an algebraically closed field $K$ containing $F$.
> 2. for any algebraically closed field $K$ and its subfield $F$, $$\overline{F}=\{ \alpha\in K: \alpha \text{ is algebraic over }F\}$$
> 3. if $K_{1},K_{2}$ are two algebraic closures of $F$, then there is an isomorphism $\varphi:K_{1}\to K_{2}$ s.t. $\varphi|_{F}=\text{id}_{F}$.
---
##### Examples
> [!h] Example 1
> We have:
> 1. $\mathbb{C}$ is algebraically closed by [[Complex Polynomials|Fundamental Theorem of Algebra]].
> 2. $\mathbb{Q},\mathbb{R}$ are not algebraically closed.
> 3. $\mathbb{C}$ is the algebraic closure of $\mathbb{R}$.
> 4. $\mathbb{C}$ is not the algebraic closure of $\mathbb{Q}$.