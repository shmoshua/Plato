#Definition #DifferentialGeometry 

> [!definition]
> Let $V$ be a [[vector space]] and $A,B\in \text{End}(V)$. The ***bracket of $A$ and $B$*** is given by: $$[A,B]:=AB-BA\in \text{End}(V)$$
> For a [[Smooth Manifold|smooth manifold]] $M$ and $X,Y$ two [[Vector Field|smooth vector fields]], the ***bracket of $X$ and $Y$*** $[X,Y]\in\Gamma(\text{T}M)$ given by: $$L_{[X,Y]}=[L_{X},L_{Y}]$$where $L_{X}$ is the isomorphism in [[Vector Field|Proposition 2]].
---
##### Properties

Let $(U,\varphi)$ be a chart on $M$ and $p,q\in U$. Then, $$X_{p}=\sum_{i=1}^{m}X^i(p)\left. \frac{ \partial  }{ \partial x^i }  \right|_{p},\quad Y_{q}=\sum_{i=1}^{m}Y^i(q)\left. \frac{ \partial  }{ \partial x^i }  \right|_{q} $$Then, $$(L_{X}L_{Y})(f)(p)=\sum_{i=1}^{m}X_{i}(p)\frac{ \partial (L_{Y}(f)\circ \varphi ^{-1}) }{ \partial x^i } (\varphi(p))$$