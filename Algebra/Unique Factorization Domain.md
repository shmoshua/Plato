#Definition #Algebra 

> [!definition]
> Let $R$ be an [[integral domain]]. $R$ is a ***unique factorization domain (UFD)***, if every $r\in R\backslash\{ 0 \}$ and $r\notin R^{*}$ has the following properties:
> 1. $r$ can be written as a product of [[Integral Domain|irreducibles]]: $r=s_{1}\dots s_{n}$
> 2. the decomposition in 1 is unique up to associates and renumbering.
- **Remark**: In a UFD $R$, $a,b\in R$ with $a=up_{1}^{e_{1}}\dots p_{n}^{e_{n}},b=vp_{1}^{f_{1}}\dots p_{n}^{f_{n}}$ with $e_{i},f_{i}\geq 0$ and $u,v\in R^{*}$, $$\text{gcd}(a,b)=p_{1}^{\min\{ e_{1},f_{1} \}}\dots p_{n}^{\min\{ e_{n},f_{n} \}}$$However, $\text{gcd}(a,b)$ is not necessarily a linear combination of $a,b$ (compare it with [[Principal Ideal Domain|Theorem 3]])
- **Remark**: $\mathbb{Z}[2i]$ is an integral domain that is not a UFD.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a unique factorization domain and let $r\in R \backslash\{ 0 \}$ s.t. $r\notin R^{*}$. Then, $r$ is [[Integral Domain|irreducible]] if and only if $r$ is [[Integral Domain|prime]].

> [!proof]-
> We have that every prime element is irreducible by [[Integral Domain|Lemma 2]]. Conversely, let $r$ be irreducible and $a,b\in R$ s.t. $r|ab$, i.e. there exists $c\in R$ s.t. $rc=ab$. 
> 1. **Case 1: if $c=0$**:
>    Then, $ab=0$ and as $R$ is an integral domain, $a=0$ or $b=0$. This means $r|a$ or $r|b$.
> 2. **Case 2: if $c\neq 0$ and $a\in R^{*}$ or $b\in R^{*}$**:
> Wlog assume that $a\in R^{*}$. Then, $a^{-1}cr=b$ and $r|b.$
> 3. **Case 3: if $c\in R$ and $a\not\in R^{*}$ and $b\not\in R^{*}$**:
>    Then, $a=p_{1}\dots p_{\alpha}$ and $b=q_{1}\dots q_{\beta}$. Therefore, $$rc=p_{1}\dots p_{\alpha}q_{1}\dots q_{\beta}$$As $rc$ is irreducible, by the unique factorization, either $rc\sim p_{i}$ or $rc\sim q_{j}$ for some $i$ or $j$. Therefore, $rc|a$ or $rc|b$ and $r|a$ or $r|b$.
> 4. **Case 4: if $a,b,c\not\in R$**:
>    Then, $a=p_{1}\dots p_{\alpha}$, $b=q_{1}\dots q_{\beta}$ and $c=\ell_{1}\dots \ell_{m}$. Then, $$r\ell_{1}\dots \ell_{m}=p_{1}\dots p_{\alpha}q_{1}\dots q_{\beta}$$and by unique factorization, $r\sim p_{i}$ or $r\sim q_{j}$ for some $i,j$. Therefore, $r|a$ or $r|b$.
---
> [!lemma] Theorem 2
> Every [[principal ideal domain]] is a unique factorization domain.

- **Remark**: $\mathbb{Z}[X]$ is a unique factorization domain, but not a principal ideal domain.
---
> [!lemma] Proposition 3
> In a unique factorization domain $R$, let $0\neq x\in R$. Then, the following are equivalent.
> 1. $x$ is [[Integral Domain|prime]].
> 2. $x$ is [[Integral Domain|irreducible]].
> 3. $(x)$ is a [[prime ideal]].


> [!proof]-
> We have:
> - (1<=>2): Proposition 1
> - (2<=>3): [[Integral Domain|Lemma 2]]
- **Remark**: Unlike in PIDs, not every non-zero prime ideals are maximal ideals in UFD, e.g. $(X)\subseteq \mathbb{Z}[X]$
	1. $(X)$ is prime: $\mathbb{Z}[X]  / (X)\cong \mathbb{Z}$ which is an integral domain.
	2. $(X)$ is not maximal: $(X)\subsetneq(2,X)\subsetneq \mathbb{Z}[X]$ or $\mathbb{Z}[X]  / (X)\cong \mathbb{Z}$ is not a field.
---
> [!lemma] Lemma 4
> Let $R$ be a unique factorization domain. Every non-constant polynomial $f\in R[X]$ can be written as $f=cg$ where:
> 1. $c$ is unique up to units in $R$.
> 2. $g$ is [[Polynomial Ring|primitive]] and unique up to units.
> 3. $\deg f=\deg g$

> [!proof]-
> Let $f(x)=a_{0}+a_{1}x+a_{2}x^{2}+\dots+a_{n}x^n$ and let $c:=c(f)$. Then, $a_{i}=cb_{i}$ for some $b_{i}\in R$ and: $$f(x)=c\cdot (b_{0}+b_{1}x+b_{2}x^{2}+\dots+b_{n}x^n)$$
> $g(x)$ is primitive, as if there is any irreducible $r$ that divides all $b_{i}$s, then $c|cr$, which is the contradiction to the maximality of $c$.
> 
> For uniqueness, suppose $f(x)=dh(x)$ where $h(x)\in R[X]$ is primitive. Any irreducible factor of $c$ must divide $h(x)$ and vice versa. Therefore, $c=du$ for some $u\in R^{*}$ and $ug(x)=h(x)$ as claimed.
---
> [!lemma] Lemma 5 (Gauss' Lemma)
> Let $R$ be a unique factorization domain. Then, the product of two primitive polynomials in $R[X]$ is primitive.

> [!proof]+
> Let $f(X)=a_{0}+a_{1}X+\dots +a_{n}X^n$ and $g(X)=b_{0}+b_{1}X+\dots+b_{m}X^m$ for $a_{n},b_{m}\neq 0$ be two primitives. Let $$h(X):=f(X)g(X)=c_{0}+c_{1}X+\dots+c_{m+n}X^{m+n}$$
---
> [!lemma] Lemma 4
> Let $R$ be an integral domain. Then, $R$ is a unique factorization domain if and only if $R[X]$ is a unique factorization domain.

> [!proof]+
> We have: 
> 1. Since $R[X]$ is a UFD, the constant polynomials have to be factored uniquely. However, due to degree concerns, the factorization in $R[X]$ is a factorization in $R$.
---