#Definition #DifferentialGeometry

> [!definition]
> Let $M$ be a [[smooth manifold]]. A ***smooth curve*** is a [[smooth function]] $\gamma:(a,b)\to M$ where $I$ is an interval.
- **Related definition**: For $t_{0}\in (a,b)$, the ***tangent vector to the curve $\gamma$ at $t_{0}$*** is the vector: $$\dot{\gamma}(t_{0}):=d\gamma \left( \left. \frac{d}{dt} \right|_{t_{0}}  \right)\in \text{T}_{\gamma(t_{0})}M $$
---
##### Properties
> [!lemma] Proposition 1
> Let $v\in \text{T}_{p}M$. Then, there exists a smooth curve $\gamma$ s.t. $\dot{\gamma}(0)=v$.

> [!proof]-
> Let $(U,\varphi)$ be a chart centered at $p$, for which: $$v=d\varphi ^{-1}\left( \left. \frac{ \partial  }{ \partial \pi^1 }  \right|_{0}  \right) $$Then, for $\gamma(t)=\varphi ^{-1}(t,0,\dots,0)$, $\dot{\gamma}(0)=v$.
---
