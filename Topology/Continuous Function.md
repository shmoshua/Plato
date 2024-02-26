#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. A map $f:X\to Y$ is ***continuous***, if for any open set $U\subseteq Y$, $f^{-1}(U)\subseteq X$ is open.
---
##### Properties
> [!lemma] Lemma 1
> For topological spaces $X,Y,Z$, $f:X\to Y,g:Y\to Z$ continuous maps and $A\subseteq X$, 
> 1. $g\circ f$ is continuous.
> 2. the inclusion $j:A\hookrightarrow X$ is continuous w.r.t. the [[Topological Space|subspace topology]].
> 3. the identity map $i:X\to X$ is continuous.
> 4. the restriction $f|_{A}:A\to Y$ is continuous.

> [!proof]-
> We have: 
> 1. Let $U\subseteq Z$ open. Then, $$(g\circ f)^{-1}(U)=f^{-1}(g^{-1}(U))$$As $g^{-1}(U)$ is open, $f^{-1}(g^{-1}(U))$ is open.
> 2. Let $U\subseteq X$ open. Then, $j^{-1}(U)=U\cap A$ which is open.
> 3. Take $A=X$ in 2.
> 4. $f|_{A}=f\circ j$ and by 1,2.
---
