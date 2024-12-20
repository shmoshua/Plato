> [!definition]
> Let $\mathbb{R}^\infty:=\bigoplus_{i\geq 0}\mathbb{R}$ be the direct sum. Then,
> 1. The ***standard $p$-simplex*** is given as: $$\Delta_{p}:=\left\{  \sum_{i=0}^{p}\lambda_{i}e_{i}: \lambda_{i}\geq 0,\sum_{i=0}^{p}\lambda_{i}=1  \right\}=\text{ConvexHull}(e_{0},\dots,e_{p})$$endowed with the [[subspace topology]] from $\mathbb{R}^{p+1}$.
- **Related definition**: For $v_{0},\dots,v_{p}\in \mathbb{R}^\infty$, 
---
##### Properties
> [!lemma] Proposition 1
> For all $x\in \Delta_{p}$, 
> 1. the barycentric coordinates $\lambda_{i}$ are unique.

> [!proof]+
> We have that:
> 1. Assume we have $\lambda_{i}$ and $\xi_{i}$ both barycentric coordinates. Then, $$\sum_{i=0}^{p}(\lambda_{i}-\xi_{i})e_{i}=0$$Then, from linear independence, $\lambda_{i}=\xi_{i}$ for all $i\in[p]$.