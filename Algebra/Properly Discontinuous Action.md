#Definition #Algebra 

> [!definition]
> Let $G$ be a [[topological group]] and $X$ a [[Topological Space]]. Then, a [[group action]] $G\curvearrowright X$ is ***properly discontinuous*** if every point $x\in X$ has an open neighborhood $U\ni x$ s.t. $$gU\cap U=\varnothing,\quad \forall g\neq e$$ 
---
##### Properties
> [!lemma] Theorem 1
> Let $M$ be a [[smooth manifold]] and $G\leq \text{Diff}(M)$. If $G\curvearrowright M$ is a properly discontinuous action, 
> 1. $M/G$ is a smooth manifold.
> 2. $\pi:M\to M / G$ is a [[Covering Space|smooth covering space]].
---
##### Examples
> [!h] Example 1 (Examples of Theorem 1)
> We have:
> 1. $S^n / \{ \text{id}_{S^n}, -\text{id}_{S^n}\}\cong S^n / Z_{2}\cong \mathbb{R}\mathbb{P}^n$
> 2. $\mathbb{R}^2 / \mathbb{Z}^2 \cong \mathbb{T}^2$
> 3. $\mathbb{R}^2 / G$ where $G=\braket{ \gamma,\delta  }$ with $\gamma(x,y)\mapsto(x,y+1)$ and $\delta(x,y)=(x+1,-y)$. Then, $\mathbb{R}^{2} / G$ is the Klein bottle.
> 4. $S^3 / \{ \pm 1 \}\cong \text{SO}(3)\cong \mathbb{R}\mathbb{P}^3$.