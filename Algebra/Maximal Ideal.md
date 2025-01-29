#Definition #Algebra
> [!definition]
> For a commutative [[Ring|ring]] $R$, an [[Ideal (Ring)|ideal]] $I\unlhd R$ is ***maximal***, if one of the following equivalent conditions hold:
> 1. $I\neq R$ and there exists no ideal $J$ s.t. $I\subsetneq J\subsetneq R$ or
> 2. $R / I$ is a [[field]].

^dce3dc

- **Remark**: every maximal ideal is a [[prime ideal]] as a field is an integral domain.
- **Related definition**: The set of all maximal ideals is called the ***maximal spectrum*** of $R$, denoted as $\text{mSpec } R$. ^1891d6
---
##### Properties
> [!lemma] Theorem 1 (Equivalent Definitions of Maximal Ideals)
> Let $R$ be a commutative ring and $I\unlhd R$ an ideal. Then, TFAE:
> 1. $I\neq R$ and there exists no ideal $J$ s.t. $I\subsetneq J\subsetneq R$ or
> 2. $R / I$ is a field.

^7d34ba

> [!proof]-
> We have:
> 1. (1=>2): Let $I\neq R$ s.t. there exists no ideal $J$ with $I\subsetneq J\subsetneq R$. Let $\pi:R \to R / I$ be the canonical projection. Then, $\pi$ is a surjective ring homomorphism and for any ideal $J\unlhd R / I$, $\pi ^{-1}(J)$ is an ideal of $R$ that contains $I$. Therefore, either $\pi ^{-1}(J)=I$, in which case $J=I$ and $\pi ^{-1}(J)=R$ which means $J=R / I$ as $\pi$ is surjective. Therefore, by [[Field|Proposition 1]], $R / I$ is a field.
> 2. (2=>1): Let $R / I$ be a field. Then, trivially $I\neq R$ and for any ideal $J\unlhd R$ with $I\subseteq J$, $\pi(J)\unlhd R / I$. Therefore, $\pi(J)=I$ or $\pi(J)=R/I$. This means that $J=I$ or $R=I$, which proves the statement. 

^fdff02

- **Corollary**: $R$ is a field if and only if $(0)\subseteq R$ is maximal.
---
> [!lemma] Theorem 2 (Every Ideal is contained in a Maximal Ideal)
> For a commutative ring $R$ and $I\unlhd R$ with $I\neq R$, 
> 1. $I$ is contained in some maximal ideal $J$.
> 2. every commutative ring $R\neq 0$ has a maximal ideal.

^05e5ce

> [!proof]-
> We have:
> 1. Let $\mathcal{M}:=\{ J\unlhd R :I\subseteq J,J\neq R\}$. The maximal elements in $\mathcal{M}$ are exactly the maximal ideals. Let $\mathcal{A}\subseteq \mathcal{M}$ be a totally ordered subfamily. If $\mathcal{A}=\varnothing$, then $I\in \mathcal{M}$ is an upper bound. Otherwise, $J':=\bigcup_{J\in \mathcal{A}}^{}J$ is an upper bound. 
>    
>    Hence, by [[Order|Zorn's lemma]], we have the statement.
> 2. Every commutative ring has a proper ideal.

^8f1aa6

---
> [!lemma] Proposition 3 (Maximal Ideals are Coprime)
> Let $R$ be a commutative ring and $P,Q\unlhd R$ be two distinct maximal ideals. Then, 
> 1. for any $m,n\in \mathbb{N}$, $P^n,Q^m$ are [[Coprime Ideal|coprime]]. 

> [!proof]-
> First we show that $P,Q$ are coprime. This is easy as $P+Q$ contains both $P$ and $Q$. Furthermore as they are distinct, they are strictly greater than both $P,Q$.  However, as they are maximal, $P+Q=R$. 
> 
> The rest follows from [[Coprime Ideal|Proposition 1]].
---
