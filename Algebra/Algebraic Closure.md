#Definition #Algebra 

> [!definition]
> A [[field]] $K$ is called ***algebraically closed*** if every polynomial $f\in K[X]$ has a root in $K$. Then, an extension $K:F$ is the ***algebraic closure*** of $F$, denoted as $\overline{F}$, if:
> 1. $K$ is [[Algebraic and Transcendental Element|algebraic]] over $F$ and 
> 2. $K$ is algebraically closed.
---
##### Properties
> [!lemma] Theorem 1
> Let $K$ be a field. Then, the following are equivalent:
> 1. every non-constant polynomial $f\in K[X]$ has at least one root in $K$.
> 2. every non-constant polynomial $f\in K[X]$ splits over $K$.
> 3. every irreducible polynomial $f\in K[X]$ is linear.
> 4. $K$ has no proper algebraic extension.

> [!proof]-
> We have:
> - 1=>2: Let $f(x)=(x-\alpha)f'(x)$ where $\alpha\in K$. Then, $f'\in K[X]$ and we can proceed with induction.
> - 2=>3: Let $f$ be irreducible. Then it is non-constant and splits over $K$. However, as $f$ is irreducible, $f$ is linear.
> - 3=>4: Let $L$ be an algebraic extension of $K$. For $\alpha\in L$, the minimal polynomial $m_{\alpha,K}$ is irreducible and therefore linear. Then, $x-\alpha\in K$ and $\alpha\in K$.
> - 4=>1: Let $f$ be a non-constant polynomial. Then, $K(\alpha):K$ is an algebraic extension therefore, $K(\alpha)=K$, i.e. $\alpha\in K$.
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
> 1. $\mathbb{C}$ is algebraically closed.
> 2. $\mathbb{Q},\mathbb{R}$ are not algebraically closed.
> 3. $\mathbb{C}$ is the algebraic closure of $\mathbb{R}$.
> 4. $\mathbb{C}$ is not the algebraic closure of $\mathbb{Q}$.