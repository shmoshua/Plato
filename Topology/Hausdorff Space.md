#Definition #Topology 
> [!definition]
> A [[topological space]] $(X,\mathcal{T})$ is ***Hausdorff***, if for all $x,y\in X$ with $x\neq y$, there exist disjoint open neighborhoods of $x,y$.
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
###### Non-Hausdorff Spaces
> [!h] Non-example 1
> Let $X$ be infinite and: $$\mathcal{T}:=\{ U\subseteq X:X \backslash U\text{ is finite or }U=\varnothing \}$$Then, $(X,\mathcal{T})$ is not Hausdorff.

> [!proof]-
> Let $x,y\in X$ and $U\ni x$ open. Then, $X \backslash U$ is finite. Similarly, $V\ni y$ open with $X \backslash V$ finite. Then, $$X \backslash(U\cap V)=X \backslash U\cup X \backslash V$$which is finite. Therefore, $U\cap V\neq \varnothing$. 

