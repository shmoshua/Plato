#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]] and $f_{0},f_{1}\in Y^X$ continuous maps. A ***homotopy*** $h$ from $f_{0}$ to $f_{1}$ is a continuous map: $$\begin{array}{cccc} {h:}&{X\times \mathbb{I}}&\to&{Y}\end{array}{}$$where $\mathbb{I}:=[0,1]$ s.t. 
> 1. $h(x,0)=f_{0}(x)$ for all $x\in X$.
> 2. $h(x,1)=f_{1}(x)$ for all $x\in X$.
> 
> $f_{0}$ and $f_{1}$ are called ***homotopic***, if such homotopy exists.
---
##### Examples
> [!h] Example 1
> Any two functions $f_{0},f_{1}:\mathbb{R}^n\to \mathbb{R}^m$ are homotopic with: $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times \mathbb{I}}&\to&{\mathbb{R}^m}\\&{(x,t)} &\mapsto & {(1-t)f_{0}(x)+tf_{1}(x)} \end{array}{}$$