#Definition #Topology 

> [!definition]
> Let $(X,d)$ be a [[Metric Space|metric space]]. A subset $A\subseteq X$ is ***compact***, if $(A,d|_{A\times A})$ is a [[Compact Metric Space|compact]] [[Metric Subspace|subspace]] of $X$.
---
##### Properties
> [!lemma] Proposition 1
> We have the following:
> 1. A closed subset of a compact space is compact.
> 2. A compact subset of any metric space is closed.
> 3. A finite union of compact sets is compact.

> [!proof]-
> We have that:
> 1. Given a covering $\{U_{i}\}_{i}$ of a closed subspace $Y\subseteq X$, we have that $\{ X\backslash Y \}\cup \{ U_{i} \}_{i}$ is an open covering of $X$. Therefore, some finite sub-collection $\mathcal{V}$ covers $X$. Then, $\mathcal{V}\backslash \{ X-Y \}$ is a finite sub-covering of $Y$.
> 2. Let $Y$ be a compact set in a metric space $(X,d)$. We will show that $X \backslash Y$ is open. Let $x\in X \backslash Y$. Then, for $a\in Y$, we define:
> 	- $U_{a}:= B(a, d(x,a) / 2)$
> 	- $V_{a}:= B(x, d(x,a) / 2)$
> 	  
> 	Then, $U_{a}\cap V_{a}=\varnothing$ by definition. Further, $\{ U_{a} \}_{a\in Y}$ is an open covering of $A$. Therefore, as $Y$ is compact, there is a finite set $S\subseteq Y$ s.t. $\{ U_{a} \}_{a\in S}$ is a covering of $Y$. Then, let $V=\bigcap_{a\in S}^{}V_{a}$. This is an open neighborhood of $x$ that is disjoint from $Y$, i.e. $V\subseteq X \backslash Y$. Therefore, $X \backslash Y$ is open.
> 	
>     Alternatively, for $x\in \overline{A}$, there exists a sequence $(x_{n})_{n}\subseteq A$ s.t. $\lim_{ n \to \infty }x_{n}=x$. However, as $A$ is compact, it is sequentially compact and there is a convergent subsequence $(x_{n_{i}})_{i}\subseteq A$ that converges to $a\in A$. As $a=x$, this shows that $x\in A$, i.e. $A = \overline{A}$. This proves that $A$ is closed.
>  3.  Let $C_{1},\dots,C_{N}$ be compact sets. Further, let $(U_{i})_{i}$ be an open covering of $\bigcup_{n=1}^{N}C_{n}$. Then, $(U_{i}\cap C_{n})_{i}$ is an open covering in $C_{n}$ and we have 
> 	 $$\mathcal{U_{n}}:=\{ U_{i}:U_{i}\cap C_{n}\text{ is in the finite subcovering of }C_{n} \}$$Then, $\bigcup_{n=1}^{N}\mathcal{U}_{n}$ is a finite sub-covering of $\bigcup_{n=1}^{N}C_{n}$.
---
> [!lemma] Proposition 2
> A subset $A\subseteq \mathbb{R}^n$ is compact if and only if it is closed and bounded.

> [!proof]-
> =>: From proposition 1, we have that $A$ is closed. Assume $A$ is not bounded. Then, there exists $(x_{n})\subseteq A$ s.t. $\left\| x_{n} \right\|> n$. However, as $A$ is compact, there is a subsequence $(x_{n_{k}})$ converging to a point in $A$, which is a contradiction. Therefore, $A$ is bounded.
> 
> <=: Let $A\subseteq \mathbb{R}^n$ be closed and bounded. Then, there exists $M\in\mathbb{R}_{+}$ s.t. $A \subseteq[-M,M]^n$. Then, for any $\varepsilon>0$, there exists a finite $\varepsilon$-net. Therefore, $A$ is totally bounded. Together with closedness, this implies that $A$ is compact.
---

