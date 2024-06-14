#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]] and $f_{0},f_{1}\in Y^X$ continuous maps. A ***homotopy*** $h$ from $f_{0}$ to $f_{1}$ is a continuous map: $h:X\times[0,1]\to Y$ s.t. 
> 1. $h(x,0)=f_{0}(x)$ for all $x\in X$.
> 2. $h(x,1)=f_{1}(x)$ for all $x\in X$.
> 
> $f_{0}$ and $f_{1}$ are called ***homotopic***, if such homotopy exists.
---
##### Properties
> [!lemma] Proposition 1
> For topological spaces $X,Y,Z$, 
> 1. $f\sim g \iff f$ and $g$ are homotopic forms an equivalence relation on $C(X,Y)$. We denote with $[X,Y]$ the set of equivalence classes. 
> 2. Homotopy is compatible with composition: let $f_{1},f_{2}\in C(X,Y)$ and $g_{1},g_{2}\in C(Y,Z)$ s.t. $f_{1}\sim f_{2}$ and $g_{1}\sim g_{2}$. Then, $g_1\circ f_{1} \sim g_{2}\circ f_{2}$.

> [!proof]-
> We have:
> 1. For any $f\in C(X,Y)$, $h(x,t)=f(x)$ is a homotopy from $f$ to $f$. If $f\sim g$ with homotopy $h$, $h(x,t)=h(x,1-t)$ gives a homotopy from $g$ to $f$. Finally, let $f_{0}\sim f_{1}$ and $f_{1}\sim f_{2}$ with homotopy $h_{1}$ and $h_{2}$ respectively. Then, $$h(x,t)=\begin{cases}h_{0}(x,2t)&0\leq t\leq \frac{1}{2}\\h_{1}(x,2t-1)& \frac{1}{2}\leq t\leq 1\end{cases}$$and $f_{0}\sim f_{2}$.
> 2. Let $h$ and $h'$ be the respective homotopies. Then, define: $$h''(x,t):=h'(h(x,t),t)$$which is continuous and: $h''(x,0)=h'(h(x,0),0)=g_{1}(f_{1}(x))$ and $h''(x,1)=h'(h(x,1),1)=g_{2}(f_{2}(x))$
---
##### Examples
> [!h] Example 1
> Any two functions $f_{0},f_{1}:\mathbb{R}^n\to \mathbb{R}^m$ are homotopic with: $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times \mathbb{I}}&\to&{\mathbb{R}^m}\\&{(x,t)} &\mapsto & {(1-t)f_{0}(x)+tf_{1}(x)} \end{array}{}$$
---
