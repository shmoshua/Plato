#Definition #Topology 

> [!definition]
> Let $(X,d_{X})$ and $(Y,d_{Y})$ be [[Metric Space|metric spaces]]. A function $f:X \to Y$ is ***continuous at $x_{0}\in X$*** if for every $\varepsilon>0$, there exists $\delta>0$ s.t.$$d_{X}(x,x_{0})<\delta\implies d_{Y}(f(x),f(x_{0}))<\varepsilon$$

- **Equivalent Definition**: $f$ is continuous at $x_{0}\in X$, if for every neighborhood $V$ of $f(x_{0})$, there exists a neighborhood $U$ of $x_{0}$ s.t. $f(U)\subseteq V$.
- **Equivalent Definition**: $f$ is continuous at $x_{0}\in X$, if for every neighborhood $V$ of $f(x_{0})$, $f^{-1}(V)$ is a neighborhood of $x_{0}$ in $X$.
---
##### Properties
> [!lemma] Lemma 1 (Continuity Lemma)
> Let $X$ and $Y$ be metric spaces. For $f:X\to Y$, the following are equivalent.
> 1. $f$ is continuous.
> 2. for every open set $V\subseteq Y$, $f^{-1}(V)$ is open in $X$.
> 3. for every closed set $C \subseteq Y$, $f^{-1}(C)$ is closed in $X$.
> 4. for every $A\subseteq X$, $f(\overline{A})\subseteq \overline{f(A)}$

> [!proof]-
> We show that: 
> - (1=>4): Let $x_{0}\in \overline{A}$ and $V$ be any neighborhood of $f(x_{0})$. Then, $f^{-1}(V)$ is a neighborhood of $x_{0}$ in $X$. Then, from closure, there exists $x\in A \cap f^{-1}(V)$. Therefore, $f(x)\in f(A)\cap V$. So every neighborhood of $f(x_{0})$ contains a point in $f(A)$. Therefore, $f(x_{0})\in \overline{f(A)}$.
> - (4=>3): Let $C$ be a closed set in $Y$, and define $A:=f^{-1}(C)$. Then, $f(\overline{A})\subseteq \overline{f(A)}$. Now, $$f(A)=f(f^{-1}(C))=C \cap f(X)\subseteq C$$Therefore, $\overline{f(A)}\subseteq \overline{C}=C$. It follows that $f(\overline{A})\subseteq C$ and $\overline{A}\subseteq f^{-1}(C)=A$. Therefore, $A=\overline{A}$ and $A$ is closed.
> - (3=>2): For an open set $V\subseteq Y$, $Y \backslash V$ is closed. Therefore, $f^{-1}(Y \backslash V)$ is closed in $X$. Therefore, $X \backslash f^{-1}(V)$ is closed in $X$.  This means, $f^{-1}(V)$ is open in $X$.
> - (2=>1): For any $x_{0}\in X$, let $V$ be the direct neighborhood of $f(x_{0})$.  Then, there exists an open neighborhood $W$ of $f(x_{0})$ that is contained in $V$ and $f^{-1}(W)$ is open in $f^{-1}(V)$. Therefore, $f^{-1}(V)$ is a neighborhood of $x_{0}$. Therefore, $f$ is continuous at $x_{0}$. 
---
> [!lemma] Proposition 2
> Let $X$ and $Y$ be metric spaces. For $f:X \to Y$, $f$ is continuous at $x\in X$ if and only. if for every sequence $(x_{n})_{n}$ with $\lim_{ n \to \infty }x_{n}=x$, we have that $\lim_{ n \to \infty }f(x_{n})=f(x)$.

> [!proof]-
> Suppose that $f$ is  continuous at $x\in X$. Then, for every $\varepsilon>0$, there exists $\delta>0$ s.t. $d(x_{n},x)<\delta$ implies $d(f(x_{n}),f(x))<\varepsilon$. Then, there also exists $N\in \mathbb{N}$ s.t. $d(x_{n},x)<\delta$ for all $n\geq N$. Therefore, $d(f(x_{n}),f(x))<\varepsilon$ whenever $n\geq N$ and it follows that $\lim_{ n \to \infty }f(x_{n})=f(x)$.
> 
> Conversely, if $f$ is not continuous at $x_{0}$, then there exists $\varepsilon>0$ s.t. for all $\delta>0$, there exists a point $x_{0}\in X$ with $d(x_{0},x)<\delta$ but $d(f(x_{0}),f(x))\geq \varepsilon$. Then, by setting $\delta=1 / n$, we can construct $(x_{n})_{n}$ s.t. $d(x_{n},x)< \frac{1}{n}$ but $d(f(x_{n}),f(x))\geq \varepsilon$. Therefore, $(x_{n})_{n}\to x$ but $f(x_{n})\not\to f(x)$.

---
> [!lemma] Proposition 3
> Let $X$ and $Y$ be metric spaces. For a continuous function $f:X\to Y$ and a compact set $A\subseteq X$, $f(A)$ is compact.

> [!proof]-
> Let $(U_{i})_{i\in I}$ be an open covering of $f(A)$. Then, $(f^{-1}(U_{i}))_{i\in I}$ is an open covering of $A$ in $X$. As $A$ is compact, there exists a finite subset $J \subseteq I$ s.t. $$(f^{-1}(U_{i}))_{i\in J}$$ is still a covering of $A$. Then, $(U_{i})_{i\in J}$ forms a covering of $f(A)$.
> 
> Alternatively, consider $(f(x_{n}))_{n}\subseteq f(A)$. then, we have a sequence $(x_{n})_{n}$ that has a convergent subsequence $(x_{n_{k}})$ that converges to $a\in A$. Then, by proposition 2, $(f(x_{n_{k}}))_{k}\to f(a)\in f(A)$. Therefore, $f(A)$ is compact. 
---
> [!lemma] Corollary 4
> Let $X$ be a metric space and  and $f:X\to \mathbb{R}$ a continuous function. Then, for a compact set $A\subseteq X$, $f(A)$ is bounded, i.e. there exists $a,b\in A$ s.t. 
> 1. $f(a)=\inf _{x\in A}f(x)$
> 2. $f(b)=\sup_{x\in A}f(x)$

> [!proof]-
> By Proposition 3, $f(A)$ is compact in $\mathbb{R}$, hence closed and bounded. Then, any bounded set $f(A)\subseteq \mathbb{R}$ has $\sup_{x\in A}f(x)$ and $\inf_{x\in A}f(x)$ in $\overline{f(A)}$. However, as $f(A)$ is closed, this means that the supremum and infimum are in $f(A)$.
---
