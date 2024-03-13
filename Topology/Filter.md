#Definition #Topology 

> [!definition]
> Let $X$ be a set. A ***filter*** $\mathcal{F}$ on $X$ is a collection of subsets of $X$ s.t. 
> 1. $\varnothing\notin \mathcal{F}$
> 2. If $A\subseteq \mathcal{F}$ and $A\subseteq B$, then $B\subseteq \mathcal{F}$.
> 3. For $A,B\in \mathcal{F}$, $A\cap B\in \mathcal{F}$
- **Related definition**:
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