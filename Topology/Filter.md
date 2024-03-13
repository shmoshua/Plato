#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***filter*** $\mathcal{F}$ on $X$ is a collection of subsets of $X$ s.t. 
> 1. $\varnothing\notin \mathcal{F}$
> 2. If $A\subseteq \mathcal{F}$ and $A\subseteq B$, then $B\subseteq \mathcal{F}$.
> 3. For $A,B\in \mathcal{F}$, $A\cap B\in \mathcal{F}$
- **Related definition**: Let $X$ be a [[topological space]] and $x_{0}\in X$. For a filter $\mathcal{F}$ on $X$, ***$\mathcal{F}$ converges to $x_{0}$*** if $\mathcal{F}_{x_{0}}\subseteq \mathcal{F}$ from Example 1, i.e. for every neighborhood $U$ of $x_{0}$, there exists $V\in \mathcal{F}$ s.t. $V\subseteq U$.
- **Related definition**: Let $X,Y$ be a [[Topological Space|topological spaces]] and $y_{0}\in Y$. For a filter $\mathcal{F}$ on $X$, ***$f$ converges to $y_{0}$ along $\mathcal{F}$*** if $f_{*}(\mathcal{F})\to y_{0}$, i.e. for any neighborhood $U$ of $y_{0}$, there exists $V\in \mathcal{F}$ s.t. $f(V)\subseteq U$.
---
##### Properties
> [!lemma] Lemma 1
> Let $X$ be a topological space. 
> 1. For $(x_{n})_{n}\subseteq X$, $x_{n}\to x$ if and only if the elementary filter of $(x_{n})_{n}$ converges to $x$.
> 2. For $f:\mathbb{R}^n\to \mathbb{R}^m$, $x_{0}\in \mathbb{R}^n$ and $y_{0}\in \mathbb{R}^m$, $f(x)\xrightarrow{x\to x_{0}} y$ if and only if $f$ converges to $y_{0}$ along $\mathcal{F}_{x_{0}}$.

> [!proof]-
> We have: 
> 1. $x_{n}\to x$ if and only if for all $U\in \mathcal{F}_{x}$, there exists $N\geq 1$ s.t. $x_{n}\in U$ for all $n\geq N$. This is equivalent to for all $U\in \mathcal{F}_{x}$, there exists $V\in \mathcal{F}$, the elementary filter, with $V\subseteq U$.
> 2. $f(x)\to y$ as $x\to x_{0}$ is equivalent to for all $\varepsilon>0$ there exists $\delta>0$ s.t. $$\|x-x_{0}\|<\delta\implies\|f(x)-y_{0}\|<\varepsilon$$Similarly, $f$ converges to $y_{0}$ along $\mathcal{F}_{x_{0}}$ if for any neighborhood $U$ of $y_{0}$, there exists a neighborhood $V$ of $x_{0}$ s.t. $f(V)\subseteq U$. As the open balls form a fundamental system of neighborhoods and the definitions coincide on the balls, we have that they are equivalent.
- **Remark**: Filters unify all kinds of limits.
---
##### Examples
> [!h] Example 1
> For a [[topological space]] $X$ and $x\in X$, the set of all neighborhoods $\mathcal{F}_{x}$ of $x$ is a filter.
---
> [!h] Example 2
> Let $X$ be an infinite set. $\mathcal{F}:=\{ A\subseteq X:X \backslash A\text{ is finite} \}$ is a filter.
---
> [!h] Example 3
> Let $X=\mathbb{R}$. Then, $\mathcal{F}_{\infty}:=\{ A\subseteq \mathbb{R}: \exists t\in \mathbb{R}, [t,+\infty)\subseteq A \}$ is a filter. 
--- 
> [!h] Example 4 (Elementary Filter)
> Let $(x_{n})_{n}\subseteq X$. Then, the ***elementary filter*** of $(x_{n})_{n}$ is defined as: $$\mathcal{F}:=\{ A\subseteq X|\  \exists N\geq 1,\forall n\geq N: x_{n}\in A\}$$
---
> [!h] Example 5 (Direct Image)
> Let $f:X\to Y$ be a map and $\mathcal{F}$ a filter on $X$. Then, $$f_{*}(\mathcal{F}):=\{ B\subseteq Y: \exists A\in \mathcal{F}:f(A)\subseteq B \}$$