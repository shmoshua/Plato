#Definition #LieGroups 

> [!definition]
> Let $G,H$ be [[Topological Group|topological groups]]. A ***local homomorphism*** is a pair $(\varphi,U)$ where $e\in U\subseteq G$ and $\varphi:U\to H$ s.t. whenever $\{ x,y,xy \}\subseteq U$, $$\varphi(xy)=\varphi(x)\varphi(y)$$
> Additionally, if $\varphi:U\to\varphi(U)$ is a [[homeomorphism]], $(\varphi,U)$ is a ***local isomorphism***.
---
##### Properties
> [!lemma] Theorem 1 (Extension of Local Homomorphisms)
> If $G$ is a [[simply connected]] topological group, then any local homomorphism $\varphi:U\to H$ extends uniquely to a continuous homomorphism $G\to H$.

> [!proof]+
> We have:
> 1. **Defining the extension**:
>    As $G$ is simply connected, it is path-connected. For all $g\in G$, let $\gamma_{g}:[0,1]\to G$ be a path from $e$ to $g$. 