#Definition #Topology 

> [!definition]
> A [[topological space]] $X$ is ***path-connected*** if for all $x,y\in X$, there exists a [[path]] $\gamma:[0,1]\to X$ from $x$ to $y$.
---
##### Properties
> [!lemma] Proposition 1
> Any path-connected space $X$ is [[Connected Space|connected]].

> [!proof]-
> Let $f:X\to \{ 0,1 \}$ be a continuous function. Assume $f$ is not constant and let $x,y\in X$ s.t. $f(x)=0$ and $f(y)=1$. Let $\gamma:[0,1]\to X$ be a path from $x$ to $y$. Then, $f\circ\gamma$ is continuous and $\{ 0,1 \}$ is connected, which is a contradiction. Therefore, $f$ is constant. 
---
##### Examples
> [!h] Example 1
> $\mathbb{R}^n$ is path-connected.
---