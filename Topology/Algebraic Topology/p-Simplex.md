> [!definition]
> Let $\mathbb{R}^\infty:=\bigoplus_{i\geq 0}\mathbb{R}$ be the direct sum. Let $X$ be a [[topological space]]. Then,
> 1. The ***standard $p$-simplex*** is given as: $$\Delta_{p}:=\left\{  \sum_{i=0}^{p}\lambda_{i}e_{i}: \lambda_{i}\geq 0,\sum_{i=0}^{p}\lambda_{i}=1  \right\}=\text{ConvexHull}(e_{0},\dots,e_{p})$$endowed with the [[subspace topology]] from $\mathbb{R}^{p+1}$.
> 2. A ***singular $p$-simplex*** in $X$ is a continuous map $\sigma:\Delta_{p}\to X$
> 3. A ***singular $p$-chain*** in $X$ is a finite formal sum of singular $p$-simplices. $S_{p}(X)$ denotes the group of singular $p$-chains (or equivalently, the free abelian group of singular $p$-simplices)
- **Related definition**: For $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, 
	1. the ***affine $p$-simplex*** is a map $[v_{0},\dots,v_{p}]:\Delta_{p}\to \mathbb{R}^\infty,\sum_{i=0}^{p}\lambda_{i}e_{i}\mapsto \sum_{i=0}^{p}\lambda_{i}v_{i}$.
	2. the ***$i$-th face map*** $F_{i}^p:=[e_{1},\dots,\widehat{e_{i}},\dots,e_{p}]:\Delta_{p-1}\hookrightarrow \Delta_{p}$
	3. the ***$i$-th face map of a singular $p$-simplex*** $\sigma$, is $\sigma^{(i)}:=\sigma \circ F_{i}^p:\Delta_{p-1}\to X$
	4. the ***boundary of a singular $p$-simplex*** $\sigma$, $$\partial_{p}\sigma:=\sum_{i=0}^{p}(-1)^i\sigma^{(i)}$$
	5. the ***boundary operator*** is then given by linearly extending the boundary for simplices: $\partial_{p}:S_{p}(X)\to S_{p-1}(X)$.
---
##### Properties
> [!lemma] Proposition 1
> For all $x\in \Delta_{p}$, 
> 1. the barycentric coordinates $\lambda_{i}$ are unique.
> 2. for any $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, $[v_{0},\dots,v_{p}]$ is continuous.
> 3. $F^p_{i}\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)=\sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}$
> 4. $F^{p+1}_{j}\circ F_{i}^p=F_{i+1}^{p+1}\circ F_{j}^p$ if $j\leq i$.
> 5. We have that: $$F_{j}^{p+1}\circ F_{i}^p=\begin{cases}[e_{0},\dots,\widehat{e_{i}},\dots,\widehat{e_{j}},\dots,e_{p}]&i<j\\ [e_{0},\dots,\widehat{e_{j}},\dots,\widehat{e_{i+1}},\dots,e_{p}]&j\leq i\end{cases}$$

> [!proof]-
> We have that:
> 1. Assume we have $\lambda_{i}$ and $\xi_{i}$ both barycentric coordinates. Then, $$\sum_{i=0}^{p}(\lambda_{i}-\xi_{i})e_{i}=0$$Then, from linear independence, $\lambda_{i}=\xi_{i}$ for all $i\in[p]$.
> 2. Obvious.
> 3. By construction.
> 4. We have that: $$\begin{align}F^{p+1}_{j}\left( F_{i}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right) \right)&=F^{p+1}_{j}\left( \sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}\right)\\&=\sum_{k=0}^{j-1}\lambda_{k}e_{k}+\sum_{k=j}^{i-1}\lambda_{k}e_{k+1}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+2}\\&\end{align}$$$$F_{i+1}^{p+1}\left( F_{j}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)  \right) =F^{p+1}_{i+1}\left( \sum_{k=0}^{} \right) $$
> 5. From 3 and 4.
---
> [!lemma] Lemma 2 (Boundary Lemma)
> We have that:
> 1. $\partial_{p}\circ\partial_{p+1}=0$