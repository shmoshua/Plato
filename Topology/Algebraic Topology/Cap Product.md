#Definition #AlgebraicTopology 

> [!definition]
> Let $X$ be a [[topological space]] and $R$ a [[ring]]. 
> 1. The ***cap product*** is a map:$$\cap:S^p(X;R)\otimes_{R}  S_{n}(X)\to S_{n-p}(X),\quad  \varphi \otimes  c\mapsto ((\pi_{n-p}\otimes  \varphi)\circ  \Delta )c$$where $\Delta:\mathcal{S}_{*}(X)\to \mathcal{S}_{*}(X)\otimes_{R}\mathcal{S}_{*}(X)$ is a [[diagonal approximation]] over $R$ and the projection $\pi_{q}:\bigoplus_{j\in \mathbb{Z}}S_{j}(X)\to S_{q}(X)$.

---
##### Examples
> [!h] Example 1 (AW Diagonal Approximation)
> Let $\Delta:=\Delta^\text{AW}$ be the [[Diagonal Approximation|Alexander-Whitney diagonal approximation]]. Let $\varepsilon:S_{0}(X)\to R$ also be the augmentation. Then, we have:
> 1. $\varphi \cap \sigma=(-1)^{pq}\braket{ \varphi , {_{p}\lfloor\sigma} }\cdot\sigma\rfloor_{q}$ for $\varphi\in S^p(X)$ and $\sigma\in S_{n}(X)$
> 2.  $\varepsilon \cap c = c$.
> 3. $\varepsilon(\varphi \cap c)=\varphi(c)$ for $\varphi\in S^p(X)$ and $c\in S_{p}(X)$
> 4. $(\varphi \cup \psi)\cap c=\varphi \cap(\psi \cap c)$

> [!proof]+
> We have that:
> 1. Compute that: $$\varphi \cap \sigma=(\pi_{q}\otimes  \varphi)\circ  \Delta\sigma=(\pi_{q}\otimes  \varphi)\sum_{s+t=n}\sigma\rfloor_{s}\otimes {_{t}\lfloor\sigma}=(-1)^{pq}\sigma\rfloor_{q}\cdot \braket{ \varphi , {_{p}\lfloor\sigma} } $$
> 2. We have that: $$\varepsilon \cap c=\underbrace{ \braket{ \varepsilon , {_{0}\lfloor c} } }_{ =1 } \cdot c=c$$
> 3. We have that: $$\varepsilon(\varphi \cap c)=\varepsilon((-1)^{pq}\braket{ \varphi , _{p}\lfloor  } )$$