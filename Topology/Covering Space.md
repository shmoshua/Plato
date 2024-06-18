#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]]. For a topological space $Y$, a continuous map $f:Y\to X$ is a ***covering space of $X$*** if for all $x\in X$, there exists an open neighborhood $U\ni x$, a non-empty discrete space $D$ and a homeomorphism $\Phi:f^{-1}(U)\to U\times D$ s.t. $$\begin{CD}f^{-1}(U)@>\Phi>> U\times D\\@VfVV@VV\text{pr}_{1}V\\U&=&U\end{CD}$$commutes, i.e. $f=\text{pr}_{1}\circ\Phi$ on $f^{-1}(U)$. 
- **Related definition**: If $D$ is the same for all $x\in X$, $f$ is called a ***$D$-covering***. If additionally $D$ is finite, then the ***degree*** of $f$ is given as $\text{deg}(f)=\left| D \right|$.
- **Remark**: if $X,Y$ are [[Connected Space|connected spaces]], $f:Y\to X$ is a covering space only if it is a homeomorphism.
- **Related definition**: for any $x\in X$, $f^{-1}(\{ x \})$ is called the ***fiber over $x$***, if the covering map $f$ identifies with $\text{pr}_{1}:U\times D\to U$ where $U\ni x$ is given as above, i.e. $f^{-1}(\{ x \})$ is in bijection with $D$.
---
##### Properties
> [!lemma] Theorem 1
> Let $X$ be a topological space and $G$ a [[Topological Group|discrete group]] with a continuous group action $G \curvearrowright X$. 
> 1. If for all $x\in X$ there exists an open neighborhood $U\ni x$ s.t. $gU\cap U= \varnothing$ for all $g\neq e$, the map: $$p:X\to$$
---

##### Examples
> [!h] Example 1
> We have:
> 1. $S^1\to S^1,z\mapsto z^n$ is a covering space with $D=\{ 1,\dots,n \}$.
> 2. $\mathbb{R}\to S^1,t\mapsto \exp(2\pi i t)$ is a covering space with $D=\mathbb{Z}$.