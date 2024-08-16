#Definition #FunctionalAnalysis 

> [!definition]
> Let $(X,d_{X})$ be a [[Metric Space|metric space]]. 
> 1. a function $f:Y\to X$ for a metric space $Y$ is ***uniformly continuous*** if for all $\varepsilon>0$, there exists $\delta>0$ s.t. $$d_{Y}(x,y)<\delta\implies d_{X}(f(x),f(y))<\varepsilon,\quad \forall x,y\in Y$$
> 1. a function $f:G\to X$ is called ***left (right) uniformly continuous*** if for all $\varepsilon>0$, there exists a neighborhood $V$ of $e_{G}$ s.t. $$d_{X}(f(x),f(y))<\varepsilon, \quad \forall y^{-1}x\in V \quad (\text{resp. }xy^{-1}\in V)$$
- **Remark**: This implies that $d(f(gx),f(gy))<\varepsilon$ for all $y^{-1}x\in V,g\in G$; this is why it is called *left* uniformly continuous.
---
##### Properties

