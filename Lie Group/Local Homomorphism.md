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
>    As $G$ is simply connected, it is path-connected. For all $g\in G$, let $\gamma_{g}:[0,1]\to G$ be a path from $e$ to $g$. Choose a partition of $[0,1]$ into subintervals $I_{k}:=[t_{k-1},t_{k}]$, for $k=1,\dots,n$, with the property that if $s,t\in I_{k}$, $\alpha(s)^{-1}\alpha(t)\in U$.
>    
>    For $x_{k}:=\alpha(t_{k})$, we get: $g=(x_{0}^{-1}x_{1})(x_{1}^{-1}x_{2})\dots(x_{n-1}^{-1}x_{n})$. Then, $$\varphi_{\alpha}(g):=\varphi(x_{0}^{-1}x_{1})\varphi(x_{1}^{-1}x_{2})\dots\varphi(x_{n-1}^{-1}x_{n})$$which is independent of the choice of the partition: Assume we take $I_{k}$ and write $[t_{k-1},t_{k}]=[t_{k-1},t]\cup[t,t_{k}]$. Then, since $t\in I_{k}$, $\alpha(t_{k-1})^{-1}\alpha(t),\alpha(t)^{-1}\alpha(t_{k})\in U$ and: $$\varphi(\alpha(t_{k-1})^{-1}\alpha(t_{k}))=\varphi(\alpha(t_{k-1})^{-1}\alpha(t))\varphi(\alpha(t)^{-1}\alpha(t_{k}))$$
> 2. **Showing the extension $\varphi$ is well-defined**: