#Definition #DifferentialGeometry 

> [!definition]
> Let $M$ be a [[smooth manifold]]. For $p\in M$, the ***tangent space*** is defined as: $$T_{p}M=\{ [x,v]:x \text{ chart around }p, v\in \mathbb{R}^m \}_{/\sim}$$where $[x,v]\sim[y,w]\iff d_{x(p)}(y\circ x^{-1})(v)=w$. We denote the equivalence class with $[x,v]_{p}$. 

- **Remark**: As $d_{\varphi(p)}(\psi \circ\varphi ^{-1})$ is invertible, $T_{p}M$ is a $m$-dimensional vector space.
- **Remark**: If $\gamma:(-1,1)\to M$ smooth with $\gamma(0)=p$. Then, $\gamma'(0):=\left[ x, \left. \frac{d}{dt}x(\gamma(t)) \right|_{t=0} \right]_{p}\in T_{p}M$.
- **Related definition**: For a [[smooth function]] $f:M\to \mathbb{R}$ and $[x,v]_{p}\in T_{p}M$, the ***directional derivative***  is given as:$$[x,v]_{p}f:= \left. \frac{d}{dt}(f\circ x ^{-1})(x(p)+tv) \right|_{t=0} $$This is analogous to defining $\gamma:(-1,1)\to \mathbb{R}^m,t\mapsto x(p)+tv$. 
- **Related definition**: Let $\left. \frac{ \partial  }{ \partial x^i } \right|_{p}:=[x,e_{i}]_{p}\in T_{p}M$. Then, for every $[x,v]_{p}\in T_{p}M$, $$[x,v]_{p}=\sum_{i=1}^{m}v^i[x,e_{i}]_{p}=\sum_{i=1}^{m}v^i\left. \frac{ \partial  }{ \partial \varphi^i } \right|_{p}$$ where $v^i\in \mathbb{R}$ are called the ***coefficients*** of $v$ in chart $x$.
- **Related definition**: $TM:=\bigsqcup_{p\in M}T_{p}M$
---
