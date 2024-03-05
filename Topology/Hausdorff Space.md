#Definition #Topology 
> [!definition]
> A [[topological space]] $(X,\mathcal{T})$ is ***Hausdorff***, if for all $x,y\in X$ with $x\neq y$, there exists open sets $U,V\in \mathcal{T}$ s.t. 
> 1. $x\in U$, 
> 2. $y\in V$ and
> 3. $U\cap V=\varnothing$.
---
##### Examples
> [!h] Example 1
> Any [[metric space]] is Hausdorff.

> [!proof]-
> Let $x\neq y$. Then, $\delta:=d(x,y)>0$. Therefore, $B_{< \delta /2}(x),B_{< \delta /2}(y)$ are the two desired open sets.
---
> [!h] Example 2
> The [[topology of pointwise and uniform convergence]] is Hausdorff.
---
