#Definition #FunctionalAnalysis 

> [!definition]
> For a [[Group|group]] $G$ and a $\mathbb{K}$-vector space $V$, a ***linear representation*** of $G$ on $V$ is a [[group homomorphism]] $\rho:G\to \text{GL}(V)$, i.e.$$\rho(g_{1}g_{2})=\rho(g_{1})\rho(g_{2}),\quad \forall g_{1},g_{2}\in G$$
- **Related Definition**: The ***dimension/degree/rank*** of $\rho$ is $\text{dim}(\rho):=\text{dim }V$.
- **Remark**: A representation $\rho:G\to \text{GL}(V)$ can also be viewed as a [[group action]] $G \curvearrowright V$ given as: $$(g,v)\mapsto \rho(g)v$$
---
##### Examples
> [!h] Example 1 (Regular Representations)
> For a group $G$, let $\mathcal{F}(G)$ define the set of all functions $f:G \to \mathbb{K}$ for a field $\mathbb{K}$. Then, 
> 1. **Left-regular representation**: $\rho:G\to \mathcal{F}(G)$, where$$(\rho(g)f)(x)=f(g^{-1}x)$$
> 2. **Right-regular representation**: $\rho:G\to \mathcal{F}(G)$, where$$(\rho(g)f)(x)=f(xg)$$
> 3. $\rho:G\times G\to \mathcal{F}(G)$, where$$(\rho(g,h)f)(x)=f(g^{-1}xh)$$