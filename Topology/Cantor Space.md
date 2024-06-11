#Definition #Topology 

> [!definition]
> The ***Cantor space*** is a [[topological space]] defined as: $$C:=\{ (x_{n})_{n}: x_{n}\in \{ 0,1 \}\}$$with the following topology: $U\subseteq C$ is open if and only if for every $x\in U$, there exists a finite index set $I\subseteq \mathbb{N}$ s.t. $$\{ y\in C: y_{n}=x_{n},\forall n\in I \}\subseteq U$$
---
##### Properties
> [!lemma] Proposition 1
> $C$ is a topological space.
---
> [!lemma] Proposition 2
> Consider the map: $$\begin{array}{cccc} {b:}&{C}&\to&{[0,1]}\\&{x} &\mapsto & {\sum_{n=1}^{\infty}\frac{x_{n}}{2^i}} \end{array}{}$$Then, 
> 1. $b$ is surjective.
> 1. $b$ is continuous.
> 2. $b$ is not a homeomorphism.
---
> [!lemma] Proposition 3
> Consider the map: $$\begin{array}{cccc} {t:}&{C}&\to&{[0,1]}\\&{x} &\mapsto & {\sum_{n=1}^{\infty}\frac{2x_{n}}{3^i}} \end{array}{}$$Then, 
> 1. $t$ is injective.
> 2. $t$ is not surjective and $\text{Im }t$ is the [[Cantor set]].
> 3. $t$ is continuous and $t:C\to t(C)$ is a homeomorphism.
---