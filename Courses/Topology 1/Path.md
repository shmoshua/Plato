#Definition #Topology 

> [!definition]
> Given a [[Topological Space]] $X$, a ***path*** on $X$ is a continuous map $\gamma\in C([0,1],X)$. It is said to be a path from $\gamma(0)$ to $\gamma(1)$. 
- **Related definition**: A path $\gamma$ is ***closed*** if $\gamma(0)=\gamma(1)$.
- **Related definition**: For two paths $\gamma_{1},\gamma_{2}$ on $X$ s.t. $\gamma_{1}(1)=\gamma_{2}(0)$, the ***composite path*** $\gamma_{1}*\gamma_{2}$ is given where: $(\gamma_{1}*\gamma_{2})(t)=\gamma_{1}(2t)\mathbb{1}_{[0, 1/ 2]}(t)+\gamma_{2}(2t-1)\mathbb{1}_{[1/ 2, 1]}(t)$.
- **Related definition**: For a path $\gamma$ on $X$, the ***reverse*** of the path is $\overline{\gamma}$ where $\overline{\gamma}(t)=\gamma(1-t)$.
- **Related definition**: Two paths $\gamma_{0},\gamma_{1}$ on $X$ are ***path-homotopic*** if there exists a homotopy $h:[0,1]\times[0,1]\to X$ s.t. $h(x,0)=\gamma_{0}(x)$, $h(x,1)=\gamma_{1}(x)$ and for all $t\in[0,1]$, $h(0,t),h(1,t)$ are constant.
---
##### Properties
> [!lemma] Proposition 1
> Let $X$ be a topological space. For $\gamma_{1},\gamma_{2}\in C([0,1],X)$:
> 1. $\gamma_{1}\sim\gamma_{2}\iff$$\gamma_{1}$ and $\gamma_{2}$ are path-homotopic forms an equivalence relation on $C([0,1],X)$
> 2. the composition of paths is well-defined modulo path-homotopy, i.e. for $\gamma_{0}\sim\gamma_{0}'$ and $\gamma_{1}\sim\gamma_{1}'$, with $\gamma_{0}(1)=\gamma_{1}(0)$, we have: $\gamma_{0}*\gamma_{1}\sim \gamma_{0}'*\gamma_{1}'$.

> [!proof]-
> We have that:
> 1. For $\gamma\in C([0,1],X)$, $h(x,t)=\gamma(x)$ is a path-homotopy from $\gamma$ to $\gamma$. Similarly, for a path homotopy $h$ from $\gamma_{0}$ to $\gamma_{1}$, $h'(x,t)=h(x,1-t)$ is a path homotopy from $\gamma_{1}$ to $\gamma_{0}$.
>    
>    Lastly, for homotopy $h$ from $\gamma_{0}$ to $\gamma_{1}$ and $h'$ from $\gamma_{1}$ to $\gamma_{2}$, $$h''(x,t)=\begin{cases}h(x,2t)&0\leq t\leq 1 /2\\h'(x,2t-1)&1 /2\leq t\leq 1\end{cases}$$is a homotopy from $\gamma_{0}$ to $\gamma_{2}$.
> 2. Obvious.
---
##### Examples
> [!h] Example 1
> If $C$ is the [[Cantor Space]], all paths on $C$ are constant.
---
> [!h] Example 2
> A [[Homotopy]] $h:X\times[0,1]\to Y$ from $f_{0}$ to $f_{1}$ is a path from $f_{0}$ to $f_{1}$ in $C(X,Y)$ w.r.t. [[Compact-Open Topology]], i.e. $$\gamma_{h}(t)(x)=h(x,t)$$
> 1. if $X$ is locally compact, $C(X\times [0,1],Y)\to C([0,1],C(X,Y))$ is a bijection.

> [!proof]-
> We have:
> 1. The continuity of $\gamma_{h}$ is given by [[Compact-Open Topology|Lemma 3.1]].
> 2. [[Compact-Open Topology|Lemma 3.3]].
---
