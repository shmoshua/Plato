#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***filter*** $\mathcal{F}$ on $X$ is a collection of subsets of $X$ s.t. 
> 1. $\varnothing\notin \mathcal{F}$
> 2. If $A\subseteq \mathcal{F}$ and $A\subseteq B$, then $B\subseteq \mathcal{F}$.
> 3. For $A,B\in \mathcal{F}$, $A\cap B\in \mathcal{F}$
- **Related definition**: Let $X$ be a [[topological space]] and $x_{0}\in X$. For a filter $\mathcal{F}$ on $X$, ***$\mathcal{F}$ converges to $x_{0}$*** if $\mathcal{F}_{x_{0}}\subseteq \mathcal{F}$ from Example 1, i.e. for every neighborhood $U$ of $x_{0}$, there exists $V\in \mathcal{F}$ s.t. $V\subseteq U$.
- **Related definition**: Let $X,Y$ be a [[Topological Space|topological spaces]] and $y_{0}\in Y$. For a filter $\mathcal{F}$ on $X$, ***$f$ converges to $y_{0}$ along $\mathcal{F}$*** if $f_{*}(\mathcal{F})\to y_{0}$, i.e. for any neighborhood $U$ of $y_{0}$, there exists $V\in \mathcal{F}$ s.t. $f(V)\subseteq U$.
- **Related definition**: A filter $\mathcal{F}$ is an ***ultrafilter*** if for all $A\subseteq X$ either $A\in \mathcal{F}$ or $A^c\in \mathcal{F}$.
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
> [!lemma] Proposition 2
> Let $X$ be a [[topological space]] and $A\subseteq X$. For $x\in X$, the following are equivalent:
> 1. $x\in \overline{A}$
> 2. there exists a filter $\mathcal{F}$ on $A$ s.t. $i:A\hookrightarrow X$ converges to $x$ along $\mathcal{F}$.

> [!proof]-
> We have: 
> 1. (2=>1): Assume $\mathcal{F}$ is such a filter. Then, for any neighborhood $U$ of $x$, there exists $V\in \mathcal{F}$ s.t. $V\subseteq U$. However, by definition $V\subseteq A$. Therefore, $V\subseteq U\cap A$ and $V\neq \varnothing$. Therefore, $x\in \overline{A}$.
> 2. (1=>2): Let: $$\mathcal{F}:=\{ B\subseteq A: \exists U\in \mathcal{F}_{x},B=U\cap A \}$$We first show that $\mathcal{F}$ is a filter. As $U\cap A\neq \varnothing$, $\varnothing \notin \mathcal{F}$. For $B\in \mathcal{F}$, there exists $U\in \mathcal{F}_{x}$ with $U\cap A$. Then, for $B\subseteq D\subseteq A$, $D\cup U\in \mathcal{F}_{x}$ and $$(D\cup U)\cap A=D\cup B=D$$ Lastly, for $B,C\subseteq \mathcal{F}$ with $B=U\cap A$ and $C=V\cap A$, $$(U\cap V)\cap A=B\cap C$$It remains to show that $i$ converges to $x$ along $\mathcal{F}$. Let $V$ be a neighborhood of $x$. Then, $V\cap A\in \mathcal{F}$ and $f(V\cap A)=V\cap A \subseteq V$. This proves the statement.
---
> [!lemma] Lemma 3
> Let $\mathcal{A}\subseteq \mathcal{P}(X)$. The following are equivalent:
> 1. there exists a filter $\mathcal{F}\supseteq\mathcal{A}$.
> 2. $\mathcal{A}$ has the finite intersection property.

> [!proof]-
> Assume $\mathcal{A}$ has the finite intersection property. We define the following filter: $$\mathcal{F}:=\{ A\subseteq X: \exists A_{1},\dots,A_{n}\in \mathcal{A}: A\supseteq A_{1}\cap\dots \cap A_{n} \}$$
> 
> One can easily see that $\mathcal{F}$ is a filter. Further, $\mathcal{A}\subseteq \mathcal{F}$.
> 
> Conversely, suppose there exists a filter $\mathcal{F}\supseteq \mathcal{A}$. Take $A_{1},\dots,A_{n}\in \mathcal{A}$. Then, $A_{1}\cap\dots \cap A_{n}\in \mathcal{F}$. However, as $\varnothing\notin \mathcal{F}$, we have the finite intersection property.
---
> [!lemma] Theorem 4
> A filter $\mathcal{F}$ is an ultrafilter if and only if it is a maximal filter.

> [!proof]-
> Assume $\mathcal{F}$ is maximal and $A\notin \mathcal{F}$. Since $\mathcal{F}\cup \{ A \}$ is not a filter, $\mathcal{F}\cup \{ A \}$ doesn't have the finite intersection property. So there is $B\in \mathcal{F}$ with $B\cap A=\varnothing$. Hence, $B\subseteq A^c$ and $A^c\in \mathcal{F}$.
> 
> Conversely, assume that $\mathcal{F}$ is an ultrafilter and that there exists $\mathcal{F}\subsetneq\mathcal{G}$ where $\mathcal{G}$ is a filter. Then, there exists $A\in \mathcal{G} \backslash \mathcal{F}$ and $A^c\in \mathcal{F}$. Then, $A^c\in \mathcal{G}$ and as $\mathcal{G}\cup \{ A \}$ has the finite intersection property by Lemma 3, $A^c\cap A\neq \varnothing$, which is a contradiction.
---

---
##### Examples
> [!h] Example 1
> For a [[topological space]] $X$ and $x\in X$, the set of all neighborhoods $\mathcal{F}_{x}$ of $x$ is a filter.
---
> [!h] Example 2 (Frechet Filter)
> Let $X$ be an infinite set. $\mathcal{F}:=\{ A\subseteq X:A^c\text{ is finite} \}$ is a filter.
---
> [!h] Example 3
> Let $X=\mathbb{R}$. Then, $\mathcal{F}_{\infty}:=\{ A\subseteq \mathbb{R}: \exists t\in \mathbb{R}, [t,+\infty)\subseteq A \}$ is a filter. 
--- 
> [!h] Example 4 (Elementary Filter)
> Let $(x_{n})_{n}\subseteq X$. Then, the ***elementary filter*** of $(x_{n})_{n}$ is defined as: $$\mathcal{F}:=\{ A\subseteq X|\  \exists N\geq 1,\forall n\geq N: x_{n}\in A\}$$
---
> [!h] Example 5 (Direct Image)
> Let $f:X\to Y$ be a map and $\mathcal{F}$ a filter on $X$. Then, $$f_{*}(\mathcal{F}):=\{ B\subseteq Y: \exists A\in \mathcal{F}:f(A)\subseteq B \}$$
---
> [!h] Example 6 (Principal Filter)
> For all $x\in X$, $\mathcal{F}_{x}:=\{ A\subseteq X: x\in A \}$ is an ultrafilter.
---
