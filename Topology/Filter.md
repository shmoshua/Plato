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
> 3. For $f:\mathbb{R}^n\to \mathbb{R}^m$, $x_{0}\in \mathbb{R}^n$ and $y_{0}\in \mathbb{R}^m$, $f(x)\xrightarrow{x\to x_{0}} y_{0}$ if and only if $f$ converges to $y_{0}$ along $\mathcal{F}_{x_{0}}$.

> [!proof]-
> We have: 
> 1. $x_{n}\to x$ if and only if for all $U\in \mathcal{F}_{x}$, there exists $N\geq 1$ s.t. $x_{n}\in U$ for all $n\geq N$. This is equivalent to for all $U\in \mathcal{F}_{x}$, there exists $V\in \mathcal{F}$, the elementary filter, with $V\subseteq U$.
> 2. $f(x)\to y$ as $x\to x_{0}$ is equivalent to for all $\varepsilon>0$ there exists $\delta>0$ s.t. $$\|x-x_{0}\|<\delta\implies\|f(x)-y_{0}\|<\varepsilon$$Similarly, $f$ converges to $y_{0}$ along $\mathcal{F}_{x_{0}}$ if for any neighborhood $U$ of $y_{0}$, there exists a neighborhood $V$ of $x_{0}$ s.t. $f(V)\subseteq U$. As the open balls form a fundamental system of neighborhoods and the definitions coincide on the balls, we have that they are equivalent.

^e13c1f

- **Remark**: Filters unify all kinds of limits.
---
> [!lemma] Proposition 2
> Let $X$ be a [[topological space]] and $A\subseteq X$. For $x\in X$, the following are equivalent:
> 1. $x\in \overline{A}$
> 2. there exists a filter $\mathcal{F}$ on $A$ s.t. $i:A\hookrightarrow X$ converges to $x$ along $\mathcal{F}$.

^1b9394

> [!proof]-
> We have: 
> 1. (2=>1): Assume $\mathcal{F}$ is such a filter. Then, for any neighborhood $U$ of $x$, there exists $V\in \mathcal{F}$ s.t. $V\subseteq U$. However, by definition $V\subseteq A$. Therefore, $V\subseteq U\cap A$ and $V\neq \varnothing$. Therefore, $x\in \overline{A}$.
> 2. (1=>2): Let: $$\mathcal{F}:=\{ B\subseteq A: \exists U\in \mathcal{F}_{x},B=U\cap A \}$$We first show that $\mathcal{F}$ is a filter. As $U\cap A\neq \varnothing$, $\varnothing \notin \mathcal{F}$. For $B\in \mathcal{F}$, there exists $U\in \mathcal{F}_{x}$ s.t. $U\cap A$. Then, for $B\subseteq D\subseteq A$, $D\cup U\in \mathcal{F}_{x}$ and $$(D\cup U)\cap A=D\cup B=D$$ Lastly, for $B,C\subseteq \mathcal{F}$ with $B=U\cap A$ and $C=V\cap A$, $$(U\cap V)\cap A=B\cap C$$It remains to show that $i$ converges to $x$ along $\mathcal{F}$. Let $V$ be a neighborhood of $x$. Then, $V\cap A\in \mathcal{F}$ and $i(V\cap A)=V\cap A \subseteq V$. This proves the statement.

^00e800

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
> [!lemma] Lemma 4
> Let $f:X\to Y$ be a [[Continuous Function|continuous function]] and a filter $\mathcal{F}$ on $X$ converges to $x_{0}$. Then, $f_{*}(\mathcal{F})$ converges to $f(x)$.

> [!proof]-
> Let $U$ be an open neighborhood of $f(x_{0})$. Then, $f^{-1}(U)$ is an open neighborhood of $x$ in $X$ and there exists $V\in \mathcal{F}$ s.t. $V\subseteq f^{-1}(U)$. Therefore, $U\in f_{*}(\mathcal{F})$.
---
> [!lemma] Lemma 5
> Let $\mathcal{F}$ be a filter on $\prod_{i\in I}^{}X_{i}$. Then, $\mathcal{F}$ converges to $x=(x_{i})_{i}$ if and only if $(\pi_{i})_{*}(\mathcal{F})$ converges to $x_{i}$ for all $i\in I$.

^0214a6

> [!proof]-
> As $\pi_{i}$ is continuous, by Lemma 4, $(\pi_{i})_{*}(\mathcal{F})$ converges to $\pi_{i}(x)=x_{i}$.
> 
> Conversely, assume that $(\pi_{i})_{*}(\mathcal{F})$ converges to $x_{i}$ for all $i\in I$. Let $U$ be a neighborhood of $x$. Then, there exists a finite $J\subseteq I$ and open $U_{j}\subseteq X_{j}$ neighborhood of $x_{j}$ for $j\in J$ s.t. $$\bigcap_{j\in J}^{}\pi_{j}^{-1}(U_{j})\subseteq U$$As $(\pi_{j})_{*}(\mathcal{F})\to x_{i}$, we have that $\pi ^{-1}_{j}(U_{j})\in \mathcal{F}$ and thereby $\bigcap_{j\in J}^{}\pi_{j}^{-1}(U_{j})\in \mathcal{F}$.
---
##### Examples
> [!h] Example 1
> For a [[topological space]] $X$ and $x\in X$, the set of all neighborhoods $\mathcal{F}_{x}$ of $x$ is a filter.
---
> [!h] Example 2 (Frechet Filter)
> Let $X$ be an infinite set. Then, for the Frechet filter $\mathcal{F}:=\{ A\subseteq X: X\backslash A\text{ is finite} \}$:
> 1. $\mathcal{F}$ is a filter.
> 2. $\mathcal{F}\subseteq \mathcal{G}$ where $\mathcal{G}$ is some ultrafilter from Lemma 5.
> 3. The ultrafilter $\mathcal{G}$ is not a principal filter.
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
