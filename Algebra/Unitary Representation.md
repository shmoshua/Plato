#Definition #Example #FunctionalAnalysis 

> [!definition]
> Let $G$ be a group which we consider as a measure space w.r.t the counting measure. Then, for a [[Hilbert Space|Hilbert space]] $\mathcal{H}$, a ***unitary representation*** of $G$ is a group homomorphism $$\pi:G \to \text{U}(\mathcal{H})$$ 
> If $\mathcal{H}=$ [[Lp Space|$L^2(X)$]] for a set $X$, we define $\pi:G \to \mathcal{B}(\mathcal{H})$ as:
> $$(\pi(a)f)(x)=f(a^{-1}x)$$
- **Related definition**: A subspace $A\subseteq \mathcal{H}$ is ***invariant*** if $\pi(g)A\subseteq A$ for all $g\in G$.
- **Related definition**: A representation $(\pi,\mathcal{H})$ is ***irreducible*** if whenever $V\subseteq \mathcal{H}$ is closed invariant, either $V=(0)$ or $V=\mathcal{H}$.
- **Related definition**: For a unitary representation $(\pi,\mathcal{H})$, an ***intertwining operator*** is $T\in \mathcal{B}(\mathcal{H})$ s.t. $T$ commutes with $\pi(g)$ for all $g\in G$. $\text{Int}(\pi)$ denotes the algebra of intertwining operators, as a sub-$C^{*}$-algebra of $\mathcal{B}(\mathcal{H})$.
---

##### Properties
> [!lemma] Proposition 1
> For an invariant subspace $A$, $A^{\bot}$ is also an invariant subspace.

> [!proof]-
> For all $v\in A,w\in A^{\bot}$ and $g\in G$, $$\braket{ v , \pi(g)w } =\braket{ \pi(g)^{*}v , w } =\braket{ \pi(g)^{-1}v , w } =\braket{ \pi(g^{-1})v , w } =0$$

If $A\subseteq \mathcal{H}$ is a closed invariant subspace, $$\begin{array}{cccc} {\pi|_{A}:}&{G}&\to&{\text{U}(A)}\\&{g} &\mapsto & {\pi(g)|_A} \end{array}{}$$is a unitary representation of $G$. Since $A^{\bot}$ is also invariant as well, we get that: $$\mathcal{H}=A\oplus A^{\bot}$$and $\pi(g)=\pi(g)|_{A}\oplus \pi(g)|_{A^{\bot}}$.

---
Let $G=\text{SL}(2,\mathbb{Z})$ and $H=(\text{id}_{\mathcal{H}})$ with $\mathcal{H}:=\ell^{2}(\text{SL}(2,\mathbb{Z}))$ with $$(\lambda(g)f)(x)=f(g^{-1}x)$$Take $C_{00}(\text{SL}(2,\mathbb{Z}))$. This is an invariant subspace but it is not closed. Let $G$ be countable and $(\pi,\mathcal{H})$ any infinite dimensional unitary representation. Then, the linear span of $$\{  \pi(g)v:g\in G\}$$for any $0\neq v\in \mathcal{H}$is an invariant subspace of $\mathcal{H}$ which is not $(0)$. But it is also not $\mathcal{H}$ as $\mathcal{H}$ has an uncountable dimension. 

---
We have: $x=x_{1}+x_{2}$ where $x_{1}\in V$ and $x_{2}\in V^{\bot}$. Then, $x_{1}=\Pi_{V}(x)$ and $\pi(g)x_{1}=\Pi_{V}(\pi(g)x)$. Therefore, $\Pi_{V}\in \text{Int}(\pi).$

---
If $T\in \text{Int}(\pi)$, then $T^{*}\in \text{Int}(\pi)$. $T\pi(g)=\pi(g)T$, $\pi(g^{-1})T^{*}=\pi(g)^{*}T^{*}=T^{*}\pi(g)^{*}=T^{*}\pi(g^{-1})$ for all $g\in G$.

---
> [!lemma] Theorem (Schur's Lemma)
> The unitary representation $(\pi,\mathcal{H})$ is irreducible if and only if $\text{Int}(\pi)=\mathbb{C}\cdot \text{id}_{\mathcal{H}}$.

> [!proof]-
> If $(\pi,\mathcal{H})$ is not irreducible and $V\subseteq \mathcal{H}$ is a closed invariant subspace s.t. $0\subsetneq V\subsetneq\mathcal{H}$. Then, $\Pi_{V}\in \text{Int}(\pi)$. This cannot be $\lambda \cdot \text{id}_{\mathcal{H}}$.
> 
> Conversely, assume there exists $T\in \text{Int}(\pi)$ s.t. $T\notin \mathbb{C}\cdot \text{ id}_{\mathcal{H}}$. Then, either $T_{1}:=\frac{1}{2}(T+T^{*})$ or $T_{2}:=\frac{1}{2i}(T-T^{*})$ is not in $\mathbb{C}\cdot \text{id}_{\mathcal{H}}$ as $T=T_{1}+iT_{2}$. Therefore, there exists $S=S^{*}\in \text{Int}(\pi)$ and $S\notin \mathbb{C}\cdot \text{id}_{\mathcal{H}}$. 
> 
> However, we claim that $\left| \text{Sp}(S) \right|\geq 2$. Let $E$ be the resolution of identity defined on the Borel sets of $\text{Sp}(S)$ with $$S=\int_{\text{Sp}(S)}\lambda  \, dE(\lambda) $$ Assume that $\text{Sp}(S)=\{ \lambda_{0} \}$. Then, $$\text{id}_{\mathcal{H}}=E(\text{Sp}(S))=E(\{ \lambda_{0} \})=\Pi_{\mathcal{H}_{\lambda_{0}}}$$Therefore, $\mathcal{H}=\mathcal{H}_{\lambda_{0}}$ and $S=\lambda_{0}\text{id}_{\mathcal{H}}$ which is a contradiction.
> 
> Let $\lambda_{1}\neq\lambda_{2}\in \text{Sp}(S)$ and $V_{i}\ni \lambda_{i}$ be open subsets of $\text{Sp}(S)$ with $V_{1}\cap V_{2}=\varnothing$. (Real numbers are Hausdorff). Then, 
> 1. $E(V_{1})\neq 0$ and $E(V_{2})\neq 0$
> 2. $0=E(\varnothing)=E(V_{1}\cap V_{2})=E(V_{1})E(V_{2})$ (projections orthogonal to each other)
> 3. Since $\pi(g)$ commutes with $S$, it commutes with $E(V_{1})$ and $E(V_{2})$.
>    
> Consider $V:=\text{Im }E(V_{1})$. Then, $V$ is $\pi(g)$-invariant and $0\subsetneq V\subsetneq \mathcal{H}$, as: $$\pi(g)V=\pi(g)E(V_{1})\mathcal{H}=E(V_{1})\pi(g)\mathcal{H}=E(V_{1})\mathcal{H}$$
---
##### Examples
> [!h] Example 1
> Let $H<G$ and $\mathcal{H}:=\ell^2(G / H)$. Then, 
> 1. $\pi:G\to \text{U}(\mathcal{H})$ where $(\pi(g)f)(xH)=f(g^{-1}xH)$ is a unitary representation.
> 2. Assume $G / H$ is finite. $\mathbb{C}\cdot \chi_{G / H}\subseteq \ell^{2}(G / H)$  is an invariant subspace.

> [!proof]+

---


**Example 1:** $\mathcal{H}=\ell^2(G,\mathbb{C})=\left\{  f:G\to \mathbb{C}\left|\sum_{a\in G}^{}\left| f(a) \right|^{2}<+\infty \right. \right\}$
> [!Lemma] Proposition 1
> For any $a\in G$, we have that:
> 1. $\pi(a)^{*}=\pi(a^{-1})$
> 2. $\pi$ is a group homomorphism
> 3. $\pi(a)$ is a unitary operator.

>[!proof]-
> We have:
> 1. 
>$$\braket{ \pi(a)f ,g  } =\sum_{x\in G}^{}|f(a^{-1}x)\overline{g(x)}|=\sum_{y\in G}^{}|f(x)\overline{g(ax)}|=\braket{ f , \pi(a^{-1})g } $$
> 2. it holds that: $$(\pi(ab)f)(x)=f(b^{-1}a^{-1}x)=(\pi(b)f)(a^{-1}x)=(\pi(a)\pi(b)f)(x)$$
> 3. $\pi(a)\pi(a)^*=\pi(a)\pi(a^{-1})=\pi(e)=\iota$.
---
> [!lemma] Proposition 2
> For $a\in G$, $\pi(a)$ admits an eigenfunction if and only if $a$ has a finite order in $G$.

>[!proof]-
>If $a$ has finite order, there exists $n\geq 1$ s.t. $\pi(a)^n=\text{Id}$. 

---
**Example 2**: For $(X,d)$ compact metric space, let $G\curvearrowright X$ by isometry, i.e. $d(gx,gy)=d(x,y)$. Further, assume that $G$ preserves the positive [[Borel Measure|Borel regular]] measure $\mu$ on $X$ with $\mu(X)<+\infty$. We define $\mathcal{H}=L^2(X,\mu)$.

> [!lemma] Proposition 3
> For every $g\in G$ and $f\in L^2(X,\mu)$, $\pi(g)$ is unitary and further, $$\left\| \pi(g)f \right\| ^{2}=\left\| f \right\| ^{2}$$

> [!proof]-
> $$\left\| \pi(g)f \right\|_{2} ^{2}=\int_{X}^{}\left| (\pi(g)f)(x) \right|^{2}   \, d\mu(x)=\int_{X}^{} \left| f(g^{-1}x) \right| ^{2} \, d\mu(x) =\int_{X}^{} \left| f(x) \right| ^{2} \, d\mu(x)=\left\| f \right\|_{2} ^{2}  $$
---
> [!lemma] Proposition 4
> Let $K\in C(X\times X,\mathbb{C})$ be a continuous kernel s.t. $K(gx,gy)=K(x,y)$. Then, for all $g\in G$ and $T_{K}$ an [[Integral Operator|integral operator]]:$$\pi(g)T_{K}=T_{K}\pi(g)$$

> [!proof]-
> $$\begin{align}(\pi(g)T_{K}f)(x)=(T_{K}f)(g^{-1}x)&=\int_{X}^{} f(y)K(g^{-1}x,y) \, d\mu(y)\\&=\int_{X}^{} f(y)K(x,gy) \, d\mu(y) \\&=\int_{X}^{} f(g^{-1}y)K(x,y) \, d\mu(y)\\&=\int_{X}^{} (\pi(g)f)(y)K(x,y) \, d\mu(y)\\&=(T_{K}\pi(g)f)(x) \end{align} $$
---
> [!lemma] Theorem 5
> $L^{2}(X,\mu)$ is a direct orthogonal sum of $\pi(G)$-invariant (irreducible) finite dimensional subspaces.
---
##### Examples
- If $G=\mathbb{Z}$, we have Fourier series.