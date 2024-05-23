#Definition #FunctionalAnalysis 
> [!definition]
> A [[Hausdorff space]] $X$ is ***locally compact***, if every point $x\in X$ has a compact neighborhood, i.e. there exists an open set $U$ and a compact set $K$, s.t. $x\in U\subseteq K$.
- **Remark**: This is equivalent to the [[Locally Compact Space|local compactness]] definition. (cf. [[Compact Space|Lemma 3]])
---
##### Properties
> [!lemma] Lemma 1
> Let $X$ be LCH. Then, 
> 1. for $K\subseteq X$ compact and $y\notin K$, there exists disjoint open sets $U,V\subseteq X$ s.t. $y\in U$, $K\subseteq V$ and $\overline{V}$ compact.
> 2. for $K\subseteq U\subseteq X$ with $K$ compact and $U$ open, there exists an open set $V\subseteq X$ with $\overline{V}$ compact s.t. $K\subseteq V\subseteq \overline{V}\subseteq U$.

> [!proof]-
> We have:
> 1. For $x\in K$, let $V_{x}$ be the open neighborhood with compact closure. Then, there exists an open neighborhood $U_{x}\ni y$ s.t. $U_{x}\cap V_{x}=\varnothing$. Then, $\{ V_{x}: x\in K \}$ is an open cover of $K$ and there exists $\{ x_{1},\dots,x_{n} \}\subseteq K$ s.t. $K\subseteq \bigcup_{j=1}^{n}V_{x_{j}}=:V$. Let $U:=\bigcap_{j=1}^{n}U_{x_{j}}$. Since, $\overline{V}\subseteq \bigcup_{j=1}^{n}\overline{V_{j}}$ which is compact, $V$ has compact closure.
> 2. For every $y\in U^c$, by 1, there exists open $V_{y}$, $W_{y}$ s.t. $K\subseteq V_{y}$, $y\in W_{y}$ and $\overline{V_{y}}$ is compact. Since $y\notin \overline{V_{y}}$, $$\bigcap_{y\in U^c}^{}U^c \cap \overline{V_{y}}=\varnothing$$and $U^c\cap \overline{V_{y}}$ is compact as a closed subset of a compact set. 
---
> [!lemma] Theorem 2 (Urysohn's Lemma)
> Let $X$ be a LCH space. Suppose $K\subseteq U\subseteq X$ with $K$ compact and $U$ open. Then, there exists a continuous function $f\in$ [[Continuous Function with Compact Support|$C_{c}(X)$]] s.t. 
> 1. $\text{Im }f\subseteq[0,1]$
> 2. $f(x)=1$ for all $x\in K$.
> 3. $\text{supp }f\subseteq U$

> [!proof]-
> By lemma 1, we first choose an open set $G$ with compact closure s.t. $K\subseteq G\subseteq \overline{G}\subseteq U$. We will construct a sequence of open sets $\{ V_{s} \}$ indexed by the dyadic rational numbers s in $(0,1)$ such that for each $t>s$,  $K\subseteq V_{t}\subseteq \overline{V}_{t}\subseteq V_{s}\subseteq G$. This is consequence to Lemma 1, i.e. $$K\subseteq V_{1/2}\subseteq \overline{V_{1/2}}\subseteq G$$Now, we define $f$ as: $$f(x):=\sup\{ s: x\in V_{s} \}$$Then, 
> 1. **Showing that $f(x)=1$ for all $x\in K$**:
>    for $x\in K$, $x\in V_{s}$ for all $s$ and hence $f(x)=1$.
> 1. **Showing that $\text{supp }f\subseteq U$:**
>    If $x\notin G$, then $f(x)=0$. Therefore, $\text{supp }f\subseteq \overline{G}\subseteq U$. 
> 2. **Showing that $f$ is continuous**:
>    It suffices to show that for all $\lambda$, $f^{-1}((\lambda,\infty))$ is open and that $f^{-1}([\lambda,\infty))$ is closed.
>    
>    First, we claim that $$f^{-1}((\lambda,\infty))=\bigcup_{s>\lambda}^{}V_{s}$$ which is open. To see this, note that if $f(x)>\lambda$ then for some $s>\lambda$, $x\in V_{s}$, and so $x$ belongs to the union on the right. On the other hand, if $x$ belongs to the union on the right, then $x\in V_{s}$ for some $s>\lambda$, and then $f(x)>\lambda$. 
>    
>    Second, we claim that $$f^{-1}([\lambda,\infty))=\bigcap_{s<\lambda}^{}\overline{V_{s}}$$To see this, note that if $f(x)\geq\lambda$, then for all $s<\lambda$, $x\in V_{s}$ and hence $s\in \overline{V_{s}}$  so $x$ belongs to the intersection on the right. On the other hand, if $x$ belongs to the intersection on the right, then for all $r<\lambda$, there is an $s>r$ so that $x\in V_{s}$. Since $\overline{V_{s}}\subseteq V_{r}$, $x\in V_{r}$ and $f(x)\geq r$. Since $r<\lambda$ is arbitrary, $f(x)\geq\lambda$.
---
> [!lemma] Lemma 4
> Let $X$ be locally compact Hausdorff. Then, $Y\subseteq X$ is locally compact if and only if $Y$ is open in $\overline{Y}$.
---
> [!lemma] Proposition 1
> For a compact set $K\subseteq X$, let: $$\|f\|_{K}=\sup_{x\in K}\left| f(x) \right| $$define a [[Seminorm|semi-norm]] on $C(X)$. Then, 
> 1. $\{ \|\cdot\|_{K}:K\subseteq X,\text{ compact} \}$ is sufficient. 
> 2. If there exists $\{ K_{n} \}_{n\geq 1}$ s.t. $X=\bigcup_{n\geq 1}^{}K_{n}$,  then $\{  \|\cdot\|_{K_{n}}\}_{n\geq 1}$ induces the topology of uniform convergence on compact sets in $C(X)$.

> [!proof]-
> We can see that $\{ p_{K_{n}} \}_{n\geq 1}$ is a sufficient countable family of semi-norms. Therefore, by [[Topological Vector Space with Seminorms|Proposition 4]], it is metrizable.
---
> [!lemma] Corollary 2
> $C(\mathbb{R}^d)$ is not normable for $d\geq 1$.

> [!proof]-
> Assume there exists a norm $\|\cdot\|$ that induces the topology. Then, $B_{<1}(0)$ is an open neighborhood of $0$. Therefore, there exists $\{ p_{K_{i}} \}_{i\in[\ell]}$ and $\varepsilon>0$ s.t. $$N(0,\{ p_{K_{i}} \}_{i\in[\ell]},\varepsilon)\subseteq B_{<1}(0)$$Let $K:=\bigcup_{i=1}^{\ell}K$. Then, $$\{ f\in C(\mathbb{R}^d):\text{supp}(f)\subseteq \mathbb{R}^d \backslash K \}\subseteq B_{<1}(0)$$which is nonsense.
---
> [!lemma] Proposition 1
> Let $X$ be a locally compact Hausdorff space and: $$I(E):=\{ f\in C_{0}(X):f|_{E}=0 \}\quad \forall E\subseteq X$$Then, $$\begin{array}{cccc} &{\{ E\subseteq X :E \text{ is closed}\}}&\to&{\{ \mathfrak{a}\subseteq C_{0}(X):\mathfrak{a}\text{ is a closed ideal} \}}\\&{E} &\mapsto & {I(E)} \end{array}{}$$is a bijection. Moreover, $I(E)$ is maximal if and only if $\left| E \right|=1$.
---
