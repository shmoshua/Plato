#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***second countable*** if $X$ has a countable [[Base of Topology|base]].
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a second countable space. Then, 
> 1. $X$ is [[Separable Space|separable]].

> [!proof]-
> Let $\{ U_{n} \}_{n}$ be the countable base. Then, we wlog assume that $U_{n}$ is non-empty and choose $x_{n}\in U_{n}$ and let $D:=\{ x_{n} \}_{n}$. We show that $D$ is dense in $X$.
> 
>  Let $V\subseteq X$ open. Then, there exists $U_{n}\subseteq V$ and $x_{n}\in V\cap D$. Therefore, $D$ is dense and countable.
---
> [!lemma] Proposition 2 (Compactness and Sequential Compactness)
> Let $X$ be a second countable space. Then, TFAE:
> 1. $X$ is [[Compact Space|compact]].
> 2. $X$ is sequentially compact.

> [!proof]+
> We have:
> 1. (1=>2): Let $X$ be compact and $(x_{n})_{n}\subseteq X$ be any sequence. Let $$\mathcal{F}:=\{ A\subseteq X: \exists N\geq 1, \forall n\geq N: x_{n}\in A \}$$be the elementary filter of $(x_{n})_{n}$ and $\mathcal{G}\supseteq \mathcal{F}$ the ultrafilter containing $\mathcal{F}$. Then, this converges to $x\in X$ and $\mathcal{F}_{x}\subseteq \mathcal{G}$ where $\mathcal{F}_{x}$ is the principal filter of $x$. 
>    
> 	As $X$ is second countable, it is first countable and $\mathcal{F}_{x}$ has a countable basis, say $\{ U_{i} \}_{i}$. We have $U_{i}\subseteq \mathcal{G}$ and for any $j$, $U_{i}\cap \{ x_{n}: n\geq j \}\neq \varnothing$. Therefore, modulo taking a subsequence, we can assume that $\mathcal{F}\supseteq\{ U_{i} \}_{i}$. Then, $\mathcal{F}\supseteq\mathcal{F}_{x}$ and $\mathcal{F}$ converges to $x$. Hence, $X$ is sequentially compact.
> 2. (2=>1): Let $\mathcal{B}$ be the countable basis of $X$ and $(U_{\alpha})_{\alpha \in A}$ an open cover of $X$. Define: $$\mathcal{B}_{0}:=\{ V\in \mathcal{B}|\  \exists U_{\alpha}:V \subseteq U_{\alpha}\}$$We claim that $\mathcal{B}_{0}\cap \mathcal{F}\neq \varnothing$ for every convergent filter $\mathcal{F}$. Let $\mathcal{F}\to x$. Indeed, since $(U_{\alpha})_{\alpha}$ is an open cover, there exists $V\in \mathcal{B}$ s.t. $x\in V\subseteq U_{\alpha}$ for some $\alpha$. Therefore, $V\in \mathcal{B}_{0}\cap \mathcal{F}_{x}$ and as $\mathcal{F}_{x}\subseteq \mathcal{F}$, we prove our claim.
>    
>    Let $\mathcal{B}_{0}=(B_{n})_{n\geq 1}$. Then, we claim that there must be $n$ s.t. $\bigcup_{i=1}^{n}B_{i}=X$. Assume otherwise. Then, for each $n$, we can choose $x_{n}\in X \backslash \bigcup_{i=1}^{n}B_{i}$ and by sequential compactness, we have a convergent subsequence $(y_{n})_{n}$. 
>    
>    Therefore, for the elementary filter $\mathcal{F}$ of $(y_{n})_{n}$, $\mathcal{B}_{0}\cap \mathcal{F}\neq \varnothing$. Therefore, there exists some $B_{n}$ s.t. there exists $N\geq 1$ with $y_{i}\in B_{n}$ for all $i\geq N$. Let $N':=\max\{ n,N \}$. Then we have: $$y_{i}=x_{n_{i}}\in X \backslash \bigcup_{m=1}^{n_{i}}B_{m}\subseteq X \backslash \bigcup_{m=1}^{i}B_{m},\quad \forall $$
---
##### Examples
> [!h] Example 1
> $\mathbb{R}^n$ is second countable with: $$\mathcal{B}:=\{ B_{<r}(x):x\in \mathbb{Q}^n,r\in \mathbb{Q} \}$$ as basis.
---
