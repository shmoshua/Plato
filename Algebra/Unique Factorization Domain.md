#Definition #Algebra 

> [!definition]
> Let $R$ be an [[integral domain]]. $R$ is a ***unique factorization domain (UFD)***, if every $r\in R\backslash\{ 0 \}$ and $r\notin R^{*}$ has the following properties:
> 1. $r$ can be written as a product of [[Integral Domain|irreducibles]]: $r=s_{1}\dots s_{n}$
> 2. the decomposition in 1 is unique up to associates and renumbering.
---
##### Properties
> [!lemma] Proposition 1
> Let $R$ be a unique factorization domain and let $r\in R \backslash\{ 0 \}$ s.t. $r\notin R^{*}$. Then, $r$ is [[Integral Domain|irreducible]] if and only if $r$ is [[Integral Domain|prime]].

> [!proof]+
> We have that every prime element is irreducible by [[Integral Domain|Lemma 2]]. Conversely, let $r$ be irreducible and $a,b\in R$ s.t. $r|ab$, i.e. there exists $c\in R$ s.t. $rc=ab$. 
> 1. **Case 1: if $c=0$**:
>    Then, $ab=0$ and as $R$ is an integral domain, $a=0$ or $b=0$. This means $r|a$ or $r|b$.
> 2. **Case 2: if $c\neq 0$ and $a\in R^{*}$ or $b\in R^{*}$**:
> Wlog assume that $a\in R^{*}$. Then, $a^{-1}cr=b$ and $r|b.$
> 3. **Case 3: if $c\in R$ and $a\not\in R^{*}$ and $b\not\in R^{*}$**:
>    Then, $a=p_{1}\dots p_{\alpha}$ and $b=q_{1}\dots q_{\beta}$. Therefore, $$rc=p_{1}\dots p_{\alpha}q_{1}\dots q_{\beta}$$
> 4. **Case 4: if $a,b,c\not\in R$**:
>    Then, $a=p_{1}\dots p_{\alpha}$ and $b=q_{1}\dots q_{\beta}$. Therefore, $$rc=p_{1}\dots p_{\alpha}q_{1}\dots q_{\beta}$$