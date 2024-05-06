#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***contractible*** if $f_{0}:=\text{id}_{X}$ is [[Homotopy|homotopic]] to a constant map. 
---
##### Examples 
> [!h] Example 1 (Rn)
> $\mathbb{R}^n$ is contractible for $n\geq 0$. For $y\in \mathbb{R}^n$, we have the homotopy, $$\begin{array}{cccc} {h:}&{\mathbb{R}^n\times \mathbb{I}}&\to&{\mathbb{R}^n}\\&{(x,t)} &\mapsto & {(1-t)x+ty} \end{array}{}$$So is any non-empty star-shaped subset of $\mathbb{R}^n$. 
---
> [!h] Example 2
> $S^1$ is not contractible.

> [!proof]+
> Assume that $S^1$ is contractible and $h$ is a homotopy with $h(x,0)=x$ and $h(x,1)=x_{0}\in S^1$ for all $x\in S^1$. By composing it with a rotation, we may assume that $x_{0}=-1$. 
> 
> Then, the map: $$\begin{array}{cccc} {\varphi:}&{S^1 \backslash\{ -1 \}}&\to&{(-\pi,\pi)}\\&{z} &\mapsto & {\text{arg}(z)}\\&{e^{it}} &\gets & {t} \end{array}{}$$is a homeomorphism.
> 
> We claim that there exists a continuous function $\tilde{f_{0}}:S^1\to \mathbb{R}$ s.t. $\text{id}_{S^1}=\exp(i\tilde{f_{0}})$