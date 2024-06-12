#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]] and $\mathcal{U}$ a [[uniform structure]] on $X$. Then, $X$ is ***complete*** if every [[Uniform Structure|Cauchy filter]] of $X$ converges. 
---
##### Examples
> [!h] Example 1
> Any compact Hausdorff space is complete.

 > [!proof]-
 > We have the uniform structure: $$\mathcal{U}:=\{ A\in X\times X:  \exists U\text{ open s.t. }\Delta \subseteq U\subseteq A \}$$
 > Let $\mathcal{F}$ be a Cauchy filter. Let $A_{0}:=X\times X$. Then, there exists $(A_{n})_{n}\subseteq \mathcal{U}$ where $A_{n}^2\subseteq A_{n-1}$. Then, there exists $(U_{n})_{n}\subseteq \mathcal{F}$ s.t. $U_{n}\times U_{n}\subseteq A_{n}$.
 > 
 > Hence, 
 ---
 