#Definition #Topology 

> [!definition]
> Given a [[topological space]] $X$, a ***path*** on $X$ is a continuous map $\gamma:[0,1]\to X$. It is said to be a path from $\gamma(0)$ to $\gamma(1)$. 
- **Related definition**: A path $\gamma$ is ***closed*** if $\gamma(0)=\gamma(1)$.
- **Related definition**: For two paths $\gamma_{1},\gamma_{2}$ on $X$ s.t. $\gamma_{1}(1)=\gamma_{2}(0)$, the ***composite path*** is given as $\gamma_{1}\gamma_{2}$ where: $\gamma(t)=\gamma_{0}(2t)\mathbb{1}_{[0, 1/ 2]}(t)+\gamma_{1}(2t-1)\mathbb{1}_{[1/ 2, 1]}(t)$.
- **Related definition**: For a path $\gamma$ on $X$, the ***reverse*** of the path is $\overline{\gamma}$ where $\overline{\gamma}(t)=\gamma(1-t)$.
---
##### Examples
> [!h] Example 1
> If $C$ is the [[Cantor space]], all paths on $C$ are constant.
---
> [!h] Example 2
> A [[homotopy]] $h:X\times[0,1]\to Y$ from $f_{0}$ to $f_{1}$ is a path from $f_{0}$ to $f_{1}$ in $C(X,Y)$ w.r.t. compact-open topology, i.e. $$\gamma_{h}(t)(x)=h(x,t)$$