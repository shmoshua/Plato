#Definition #MeasureTheory #FunctionalAnalysis 
> [!definition]
> For a [[measure space]] $(X,\Sigma)$, a function $\nu:\Sigma\to \mathbb{C}$ is a ***complex measure*** if:
> 1. $\nu(\varnothing)=0$ and
> 2. $\nu$ is [[Additive Functions|additive]].
---
##### Properties
> [!lemma] Theorem 1
> Let $(X,\Sigma)$ be a measure space, $\mu:\Sigma\to[0,+\infty]$ a non-negative finite measure and $\nu:\Sigma\to \mathbb{C}$ a complex measure s.t. $$\left| \nu(A) \right|\leq \mu(A)\quad \forall A\in \Sigma$$
> Then, $d\nu=\rho d\mu$ where $\left| \rho \right|\leq 1$. Moreover, if $\nu$ is positive, then $0\leq\rho\leq 1$

> [!proof]+
> Let $f=\sum_{a\in\mathbb{C}}^{}a\chi_{f^{-1}[\{ a \}]}$ be a [[simple function]]. Then, $$\left| \int_{X}^{} f \, d\nu  \right| \leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \left| \nu(f^{-1}[\{ a \}]) \right|\leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \mu(f^{-1}[\{ a \}])=\int_{X}\left| f \right|  \, d\mu  $$