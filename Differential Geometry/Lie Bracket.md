#Definition #DifferentialGeometry 

> [!definition]
> Let $V$ be a [[vector space]] and $A,B\in \text{End}(V)$. The ***bracket of $A$ and $B$*** is given by: $$[A,B]:=AB-BA\in \text{End}(V)$$
> For a [[Smooth Manifold|smooth manifold]] $M$ and $X,Y$ two [[Vector Field|smooth vector fields]], the ***bracket of $X$ and $Y$*** $[X,Y]\in\Gamma(\text{T}M)$ given by: $$L_{[X,Y]}=[L_{X},L_{Y}]$$where $L_{X}$ is the isomorphism in [[Vector Field|Proposition 2]].
---
##### Properties

> [!lemma] Proposition 1
> For $(U,\varphi)$ chart on $M$ at $p$, the local coordinates of $[X,Y]$ is given as $[X,Y]_{p}=\sum_{j=1}^{m}Z^j(p)\left. \frac{ \partial  }{ \partial x^j } \right|_{p}$ where: $$Z^j(p):=\sum_{i=1}^{m}X_{i}(p)\frac{ \partial Y_{j} }{ \partial x^i } (p)-Y_{i}(p)\frac{ \partial X_{j} }{ \partial x^i }(p) $$

> [!proof]-
> Let $(U,\varphi)$ be a chart on $M$ and $p,q\in U$. Then, $$X_{p}=\sum_{i=1}^{m}X^i(p)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p},\quad Y_{q}=\sum_{i=1}^{m}Y^i(q)\left. \frac{ \partial  }{ \partial x^i }  \right|_{q} $$Then, $$(L_{X}L_{Y})(f)(p)=\sum_{i=1}^{m}X_{i}(p)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p}(L_{Y}f)=\sum_{i=1}^{m}X_{i}(p) \frac{ \partial L_{Y}f  }{ \partial x^i }(p)$$where: $$\frac{ \partial L_{Y}f }{ \partial x^i } (p)=\sum_{j=1}^{m}\frac{ \partial  }{ \partial x^i }  \left( Y_{j}\cdot \frac{ \partial f }{ \partial x^j }  \right)(p)=\sum_{j=1}^{m}\frac{ \partial Y_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{j=1}^{m}Y_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p) $$Therefore, $$\begin{align}(L_{X}L_{Y})(f)(p)&=\sum_{i,j=1}^{m}X_{i}(p)\frac{ \partial Y_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{i,j=1}^{m}X_{i}(p)Y_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p)\\(L_{Y}L_{X})(f)(p)&=\sum_{i,j=1}^{m}Y_{i}(p)\frac{ \partial X_{j} }{ \partial x^i } (p)\frac{ \partial f }{ \partial x^j }(p)+\sum_{i,j=1}^{m}Y_{i}(p)X_{j}(p)\frac{ \partial^{2}f }{ \partial x^i\partial x^j } (p)\end{align}$$By Schwarz's Theorem, $$L_{[X,Y]}(f)(p)=\sum_{j=1}^{m}\underbrace{ \left( \sum_{i=1}^{m}X_{i}(p)\frac{ \partial Y_{j} }{ \partial x^i } (p)-Y_{i}(p)\frac{ \partial X_{j} }{ \partial x^i }(p)  \right) }_{ =:Z^j(p) } \frac{ \partial f }{ \partial x^j } (p)$$Therefore, $$[X,Y]_{p}=\sum_{j=1}^{m}Z^j(p) \left. \frac{ \partial  }{ \partial x^j } \right| _{p} $$
---