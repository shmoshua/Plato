> [!definition]
> Let $\mathbb{R}^\infty:=\bigoplus_{i\geq 0}\mathbb{R}$ be the direct sum. Then,
> 1. The ***standard $p$-simplex*** is given as: $$\Delta_{p}:=\left\{  \sum_{i=0}^{p}\lambda_{i}e_{i}: \lambda_{i}\geq 0,\sum_{i=0}^{p}\lambda_{i}=1  \right\}=\text{ConvexHull}(e_{0},\dots,e_{p})$$endowed with the [[subspace topology]] from $\mathbb{R}^{p+1}$.
- **Related definition**: For $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, 
	1. the ***affine $p$-simplex*** is a map $[v_{0},\dots,v_{p}]:\Delta_{p}\to \mathbb{R}^\infty,\sum_{i=0}^{p}\lambda_{i}e_{i}\mapsto \sum_{i=0}^{p}\lambda_{i}v_{i}$.
	2. the ***$i$-th face map*** $F_{i}^p:=[e_{1},\dots,\widehat{e_{i}},\dots,e_{p}]:\Delta_{p-1}\hookrightarrow \Delta_{p}$
---
##### Properties
> [!lemma] Proposition 1
> For all $x\in \Delta_{p}$, 
> 1. the barycentric coordinates $\lambda_{i}$ are unique.
> 2. for any $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, $[v_{0},\dots,v_{p}]$ is continuous.
> 3. $F^p_{i}\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)=\sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}$
> 4. $F^{p+1}_{j}\circ F_{i}^p=F_{i+1}^{p+1}\circ F_{j}^p$ if $j\leq i$.

> [!proof]+
> We have that:
> 1. Assume we have $\lambda_{i}$ and $\xi_{i}$ both barycentric coordinates. Then, $$\sum_{i=0}^{p}(\lambda_{i}-\xi_{i})e_{i}=0$$Then, from linear independence, $\lambda_{i}=\xi_{i}$ for all $i\in[p]$.
> 2. Obvious.
> 3. By construction.
> 4. We have that: $$\begin{align}F^{p+1}_{j}\left( F_{i}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right) \right)&=F^{p+1}_{j}\left( \sum_{k=0}^{i-1}\lambda_{k}e_{k}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+1}\right)\\&=\sum_{k=0}^{j-1}\lambda_{k}e_{k}+\sum_{k=j}^{i-1}\lambda_{k}e_{k+1}+\sum_{k=i}^{p-1}\lambda_{k}e_{k+2}\\&\end{align}$$$$F_{i+1}^{p+1}\left( F_{j}^p\left( \sum_{k=0}^{p-1}\lambda_{k}e_{k} \right)  \right) =F^{p+1}_{i+1}\left( \sum_{k=0}^{} \right) $$