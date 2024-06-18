#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]]. For a topological space $Y$, a continuous map $f:Y\to X$ is a ***covering space of $X$*** if for all $x\in X$, there exists an open neighborhood $U\ni x$, a non-empty discrete space $D$ and a homeomorphism $\Phi:f^{-1}(U)\to U\times D$ s.t. $$\begin{CD}f^{-1}(U)@>\Phi>> U\times D\\@VfVV@VV\text{pr}_{1}V\\U&=&U\end{CD}$$commutes, i.e. $f=\text{pr}_{1}\circ\Phi$ on $f^{-1}(U)$. 
---
##### Examples
> [!h] Example 1
> We have:
> 1. $S^1\to S^1,z\mapsto z^n$ is a covering space with $D=\{ 1,\dots,n \}$.
> 2. $\mathbb{R}\to S^1,t\mapsto \exp(2\pi i t)$ is a covering space with $D=\mathbb{Z}$.