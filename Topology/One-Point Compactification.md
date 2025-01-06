#Definition #Topology #FunctionalAnalysis 

> [!definition]
> For a [[Topological Space|topological space]], the ***one-point/Alexandroff compactification*** of $X$ is the topological space $\alpha X:=X\cup \{ \infty \}$ where:
> 1. For any $U$ open in $X$, $U$ is open in $\alpha X$.
> 3. For any $K$ closed and compact in $X$, $(X \backslash K)\cup \{ \infty \}$ is open in $\alpha X$.
- **Remark**: if $X$ is Hausdorff, then condition 3 only requires compactness. 
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. The topology on $\alpha X$ is well-defined.
> 2. $\alpha X$ is [[Compact Space|compact]].
> 3. the inclusion $i:X\to\alpha X$ is an open embedding.
> 4. if $X\cong Y$ then $\alpha X\cong \alpha Y$.

> [!proof]-
> We have that:
> 1. It is sufficient to see that:
> 	1. the union and finite intersection of $(X \backslash K)\cup \{ \infty \}$ are closed among themselves.
> 	2. for $U,K\subseteq X$ where $U$ open and $K$ closed and compact in $X$, the union and intersection of $U$ and $(X \backslash K)\cup \{ \infty \}$ is again one of the two kinds. 
> 
> 	We have for finite $I$,
> 	1. $$\bigcap_{i\in I}^{}(X \backslash K_{i}) \cup \{ \infty \}=\left( X \backslash \bigcup_{i\in I}^{}K_{i} \right) \cup \{ \infty \},\quad \bigcup_{\lambda\in \Lambda}^{}(X \backslash K_{\lambda})\cup \{ \infty \}= \left( X \backslash \bigcap_{\lambda\in \Lambda}^{}K_{\lambda} \right) \cup \{ \infty \} $$
> 	2. $$U\cap((X \backslash K)\cup \{ \infty \})=(X \backslash C)\cap(X \backslash K)=X \backslash (C \cup K)$$
> 	3. $$U\cup((X \backslash K)\cup \{ \infty \})=(X \backslash C)\cup(X\backslash K)\cup \{ \infty \}=(X \backslash (C\cap K))\cup \{ \infty \}$$
> 2. Let $(U_{i})_{i\in I}$ be an open cover of $\alpha X$. Then, there exists $i_{\infty}$ with $\infty\in U_{i_{\infty}}$. Hence, there exists a compact closed subset $K$ with $X \backslash K\subseteq U_{i_{\infty}}$. Further, $\{ U_{i}: U_{i}\subseteq X \}$ is an open cover of $K$. Hence, there exists finite $J\subseteq I$ s.t. $\{ U_{i} \}_{i\in J}$ is a cover of $K$. This shows that $\{ U_{i} \}_{i\in J}\cup \{ U_{i_{\infty}} \}$ is a finite subcover of $\alpha X$.
> 3. For $U\subseteq X$ open, $i^{-1}(U)=U$, which is open. For $K\subseteq X$ closed and compact, $i^{-1}(X \backslash K\cup \{ \infty \})=X \backslash K$ which is open. Hence, $i$ is continuous. Further, by definition the map is open. Lastly, we have that $i$ is injective. Hence, $i$ is an embedding. 
> 4. Let $\psi:X\to Y$ be the homeomorphism. Then, we define: $$\Psi:\alpha X\to\alpha Y,\quad x\mapsto \begin{cases}\psi (x)&x\neq \infty\\\infty&x=\infty\end{cases}$$Let $U\subseteq Y$ be open. Then, $\Psi ^{-1}(U)=\psi ^{-1}(U)$ which is open. For $K\subseteq Y$ closed and compact, $\Psi ^{-1}(Y \backslash K\cup \{ \infty \})=X  \backslash \psi ^{-1}(K)\cup \{ \infty \}$ where $\psi ^{-1}(K)$ is compact. Hence, $\Psi$ is continuous and by symmetry, $\Psi$ is a homeomorphism.
>    
---
###### Hausdorff Spaces
> [!lemma] Proposition 1
> Let $X$ be a Hausdorff space.
> 1. if $X$ is locally compact, $\alpha X$ is compact Hausdorff.
> 2. if $X$ is compact, $\alpha X$ is compact Hausdorff with an addition of a discrete point $\{ \infty \}$.

> [!proof]-
> Let $x\neq y\in \alpha X$. If $x$ is $\infty$ wlog, then $y\in X$ and there exists a compact neighborhood $K$ of $y$. Let $U\subseteq K$. Then, $V:=\{ \infty \}\cup(X \backslash K)$ is an open neighborhood of $x$ and $U\cap V=\varnothing$. 
> 
> If $x,y\in X$, then as $X$ is Hausdorff, there exists disjoint neighborhoods $U,V$ of $x,y$.
---
> [!lemma] Theorem 2
> Let $X$ be compact Hausdorff and $x_{0}\in X$. Then, 
> 1. $X\cong \alpha(X \backslash \{ x_{0} \})$ where $X \backslash \{ x_{0} \}$ is LCH.

> [!proof]-
> We have that:
> 1. Consider the function: $$\psi:X\to\alpha(X \backslash \{ x_{0} \}),\quad x\mapsto \begin{cases}\infty&x=x_{0}\\x&x\neq x_{0}\end{cases}$$we show that this is a homeomorphism. It is easy to see that $\psi$ is a bijection. As $X$ is compact and $\alpha(X \backslash \{ x_{0} \})$ Hausdorff, it suffices to show that $\psi$ is continuous. We have that for $U\subseteq X \backslash \{ x_{0} \}$ open, as $X \backslash \{ x_{0} \}$ is open in $X$, $U\subseteq X$ is open. For $K\subseteq X \backslash \{ x_{0} \}$ compact, then $K\subseteq X$ is compact and closed. Hence, $X \backslash K$ is open and:$$\psi ^{-1}(X \backslash K\cup \{ \infty \})=X \backslash K\cup \{ x_{0} \}=X \backslash K$$
>    Lastly, $X \backslash \{ x_{0} \}$ is LCH as an open subspace of a compact Hausdorff space (cf. [[Compact Space|Proposition 2]]).
---

##### Examples
> [!h] Example 1
> We have that:
> 1. $S^n$ is homeomorphic to $\alpha\mathbb{R}^n:=\mathbb{R}^n\cup \{ \infty \}$
> 2. for any $A\in \text{GL}(n,\mathbb{R})$, $\widehat{A}:\mathbb{R}^n\cup \{ \infty \}\to \mathbb{R}^n\cup \{ \infty \}$ by $\widehat{A}|_{\mathbb{R}^n}=A$ and $\widehat{A}(\infty)=\infty$ is a homeomorphism.

^170aa2

> [!proof]-
> We have:
> 1. Let $N:=(0,\dots,0,1)\in S^n$ and let $\pi:S^n \backslash \{ N \}\to \mathbb{R}^n$ be the stereographic projection defined as: $$\pi(x)=\frac{1}{1-x_{n+1} }(x_{1},\dots,x_{n})$$Notice that $\pi$ is continuous and has the continuous inverse: $$\pi ^{-1}:\mathbb{R}^n\to S^n \backslash \{ N \},\quad (x_{1},\dots,x_{n})\mapsto \frac{1}{\|x\|^2+1}(2x_{1},\dots,2x_{n},\|x\|^{2}-1)$$Now, let $f:\mathbb{R}^n\cup \{ \infty \}\to S^n$ where $f|_{\mathbb{R}^n}=\pi ^{-1}$ and $f(\infty)=N$. Then, of course $f$ is continuous for every $x\in \mathbb{R}^n$ and at $\infty$, we have that for every $U\ni N$, $f^{-1}(U)=\pi(U \backslash \{ N \})\cup \{ \infty \}$. Notice that $\pi(U \backslash \{ N \})^c=\pi(S^n \backslash U)$ which is compact. Hence, $f$ is a homeomorphism.
> 2. Follows similarly as the argument in 1 as $A$ is a homeomorphism.

^e9411e

---
