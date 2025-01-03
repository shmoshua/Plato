#Definition #AlgebraicTopology 

> [!definition]
> Let $G$ be an [[abelian group]]. A ***singular homology*** $H(\cdot;G)$ with [[Homology Theory|coefficients group]] $G$ is defined as follows. For $X$ a [[topological space]]:
> 1. $\mathcal{S}(X;G)$ is the graded abelian group with $S_{p}(X;G):=\bigoplus_{\sigma:\Delta_{p}\to X}G\sigma$.
> 2. $\partial:S_{p}(X;G)\to S_{p-1}(X;G)$ extending $\partial(g\sigma):=\sum_{i=0}^{p}(-1)^ig \sigma \circ F_{i}^p$ where for all [[p-Simplex|singular $p$-simplex]] $\sigma:\Delta_{p}\to X$:$$(-1)^ig:=\begin{cases}g&i\text{ is even}\\-g&i\text{ is odd}\end{cases}$$and $F_{i}^p:\Delta_{i-1}\to\Delta_{i}$ is the [[p-Simplex|$i$-th face map]].
> 3. $H_{p}(X,G):=H_{p}(\mathcal{S}(X;G))$ and for $A\subseteq X$, $H_{p}(X,A;G):=H_{p}(\mathcal{S}(X,A;G))$ where $\mathcal{S}(X,A;G):=\mathcal{S}(X;G) / \mathcal{S}(A;G)$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\partial^{2}=0$, i.e. $\mathcal{S}(X;G)$ is a [[chain complex]].

> [!proof]+
> We have:
> 1. For singular $p$-simplex $\sigma:\Delta_{p}\to X$, we have that: $$\partial(\partial\sigma)=\partial\left( \sum_{i=0}^{p}(-1)^i g \sigma \circ F_{i}^p \right)=\sum_{i=0}^{p}(-1)^ig\partial(\sigma \circ F_{i}^p)$$