#Definition #FunctionalAnalysis 

> [!definition]
> Let $(X,\mathcal{U})$ and $(Y,\mathcal{V})$ be two [[Topological Space|topological spaces]] with a [[uniform structure]]. Then, 
> 1. a function $f: X\to Y$ is ***uniformly continuous*** if for any $A\in \mathcal{V}$, there exists $B\in \mathcal{U}$ s.t. $$(x,y)\in B \implies (f(x),f(y))\in A,\quad \forall x,y\in X$$


---
##### Properties

![[Haar Measure#^9177e0]]
![[Haar Measure#^9eb745|p]]

---
##### Examples
> [!h] Example 1 (Topological group)
>  Let $X$ be a metric space. A function $f:G\to X$ is called ***left (right) uniformly continuous*** if for all $\varepsilon>0$, there exists a neighborhood $V$ of $e_{G}$ s.t. $$d_{X}(f(x),f(y))<\varepsilon, \quad \forall y^{-1}x\in V \quad (\text{resp. }xy^{-1}\in V)$$

- **Remark**: This implies that $d(f(gx),f(gy))<\varepsilon$ for all $y^{-1}x\in V,g\in G$;;this is why it is called *left* uniformly continuous.
---