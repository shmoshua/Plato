#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** is defined as: $$T_{p}M=\{ [\varphi,v]:\varphi \text{ chart around }p, v\in \mathbb{R}^m \}_{/\sim}$$where $[\varphi,v]\sim[\psi,w]\iff d_{\varphi(p)}(\psi \circ\varphi ^{-1})(v)=w$. We denote the equivalence class with $[\varphi,v]_{p}$. 

- **Remark**: As $d_{\varphi(p)}(\psi \circ\varphi ^{-1})$ is invertible, $T_{p}M$ is a $m$-dimensional vector space.
- **Remark**: If $\gamma:(-1,1)\to M$ smooth with $\gamma(0)=p$. Then, $\gamma'(0):=\left[ \varphi, \left. \frac{d}{dt}\varphi(\gamma(t)) \right|_{t=0} \right]_{p}\in T_{p}M$.
- **Related definition**: For a smooth function $f:M\to \mathbb{R}$ and $V:=[\varphi,v]\in T_{p}M$, $$Vf:= \left. \frac{d}{dt}(f\circ \varphi ^{-1})(\varphi(p)+tv) \right|_{t=0} $$
- **Remark**: Let $\left. \frac{ \partial  }{ \partial \varphi^i } \right|_{p}:=[\varphi,e_{i}]_{p}\in T_{p}M$. Then, for every $V\in T_{p}M$, $V=\sum_{i=1}^{m}v^i\left. \frac{ \partial  }{ \partial \varphi^i } \right|_{p}$ where $v^i$ are called the ***coefficients***.
- **Related definition**: $TM:=\bigsqcup_{p\in M}T_{p}M$
---