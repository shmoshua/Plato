#Definition #Topology 

> [!definition]
> A [[Topological Space]] $X$ is ***path-connected*** if for all $x,y\in X$, there exists a [[Path]] $\gamma:[0,1]\to X$ from $x$ to $y$.
- **Related Definition**: For any $X$, we can define an equivalence relation: $x \sim y$ if and only if there is a path from $x$ to $y$. Then, the equivalence classes are ***path-components*** of $X$.
---
##### Properties
> [!lemma] Proposition 1
> For any path-connected space $X$,
> 1. $X$ is [[Connected Space|connected]].
> 2. for any $f:X\to Y$ continuous, $f(X)$ is path-connected.

> [!proof]-
> We have:
> 1. Let $f:X\to \{ 0,1 \}$ be a continuous function. Assume $f$ is not constant and let $x,y\in X$ s.t. $f(x)=0$ and $f(y)=1$. Let $\gamma:[0,1]\to X$ be a path from $x$ to $y$. Then, $f\circ\gamma$ is continuous and $\{ 0,1 \}$ is connected, which is a contradiction. Therefore, $f$ is constant. 
> 2. Let $x,y\in X$ and $\gamma$ the path from $x$ to $y$. Then, $f\circ\gamma$ is a path from $f(x)$ to $f(y)$. 
---
> [!lemma] Lemma 2
> For any space $X$ and $x\in X$, the path component of $x$ in $X$ is contained in the connected component of $x$. 
---
> [!lemma] Theorem 3
> Let $X$ be a topological space. 
> 1. if $X$ is [[Connected Space|connected]] and [[Locally Path-Connected Space|locally path-connected]], then $X$ is path-connected.

> [!proof]-
> Let $X$ be non-empty and choose $x\in X$. We define $V$ to be the path-component of $x$, i.e. $$V:=\{ y\in X: \exists \gamma \text{ path}:\gamma(0)=x,\gamma(1)=y \}$$Then, 
> 1. **$V$ is open**:
>    Let $y\in V$. Then, there exists a path-connected neighborhood $U\ni y$. Wlog we may assume that $U$ is open. Then, for any $z\in U$, there exists a path from $y$ to $z$ and hence, there exists a path from $x$ to $z$. In other words, $U\subseteq V$ and $V$ is open.
>2. **$V$ is closed**:
>   Let $y\notin V$. Then, there exists a path-connected neighborhood $U\ni y$ and we claim that $V\cap U=\varnothing$. Otherwise, if $z\in V\cap U$, there exists a path from $x$ to $z$ and again from $z$ to $y$. Therefore, $y\in V$, which is a contradiction.
> 
> Therefore, as $V$ is non-empty, we have by connectedness that $V=X$. Hence, $X$ is path-connected.
- **Corollary**: Every connected topological manifold is path-connected.
---
##### Examples
> [!h] Example 1
> $\mathbb{R}^n$ is path-connected.
---
##### Non-Examples
> [!h] Non-Example 1
> Consider $$C=\{ (0,1) \}\cup \bigcup_{n\geq 1}^{}\left( \left\{  \frac{1}{n}  \right\}\times[0,1] \right)\cup([0,1]\times\{ 0 \})\subseteq \mathbb{R}^{2}$$
> 1. $C$ is connected.
> 2. $C$ is not path-connected.

> [!proof]-
> We have that:
> 1. Firstly, one can easily show that $C \backslash \{ (0,1) \}$ is connected. Indeed, $(\{ 1 / n \}\times[0,1])\cup([0,1]\times \{ 0 \})$ is connected as they share a point $(1/n, 0)$ and $C\backslash\{ (0,1) \}$ is a union of all such connected components with $[0,1]\times \{ 0 \}$ as intersection. 
>    
>    Let $U_{1}\sqcup U_{2}=C$ be open sets in $C$ with $(0,1)\in U_{1}$ wlog. As $U_{1}$ is open, $U_{1}\cap (C \backslash \{ (0,1) \})\neq \varnothing$ and by connectedness of $C \backslash\{ (0,1) \}$, $U_{2}\cap C\backslash\{ (0,1) \}=\varnothing$. However, as $(0,1)\in U_{1}$, $U_{2}\cap C=\varnothing$. This shows the statement.
> 2. $Y$ is not empty as $0\in Y$. We also know that $\{ (0,1) \}$ is closed in $C$. Therefore, $Y$ is closed by continuity.
> 3. We see that $V=B_{<\varepsilon}((0,1))\cap C$ where the ball is with respect to the norm $\|(x,y)\|:=\left| x \right|+\left| y \right|$. Therefore, $V$ is open as a continuous preimage of an open set in $C$ and $\gamma ^{-1}(V)$ is open in $[0,1]$. Assume that $t_{0}\in Y$. Then, as $(0,1)\in V$, $t_{0}\in \gamma ^{-1}(V)$ and there exists $a,b\in \mathbb{R}$ s.t. $t_{0}\in(a,b)\cap[0,1]\subseteq \gamma ^{-1}(V)$. Therefore, $\gamma((a,b)\cap[0,1])\subseteq V$.
> 4. $(a,b)\cap[0,1]$ is connected and $\gamma$ is continuous. Therefore, $\gamma((a,b)\cap[0,1])$ is connected.
> 5. We show that the connected component of $(0,1)$ in $V$ is $\{ (0,1) \}$. Let $C_{(0,1)}$ be the connected component of $(0,1)$ and assume there was another point $p\in C_{(0,1)}\subseteq V$. As $\varepsilon< 1/2$, we have that $p=(1 / n,z)$ for some $n\geq 2$. Then, it is easy to see that $C_{(0,1)}$ is not connected by splitting it at $\frac{1}{n+1}<k< \frac{1}{n}$ into two disjoint non-empty open subsets. Therefore, $C_{(0,1)}=\{ (0,1) \}$ and as $\gamma(t_{0})=(0,1)$ and $\gamma((a,b)\cap[0,1])$ is connected, $(0,1)\in\gamma((a,b)\cap[0,1])\subseteq C_{(0,1)}=\{ (0,1) \}$, which proves the statement.
> 6. For any $t_{0}\in Y$, we have found an open neighborhood $U$ of $t_{0}$ in $[0,1]$ s.t. $U\subseteq Y$. Therefore, $Y$ is open in $[0,1]$. 
> 7. As $[0,1]$ is connected and $Y\subseteq[0,1]$ is both open and closed, $Y=[0,1]$. Therefore, there cannot be a path $\gamma$ from $(0,1)$ to any other point.
---
