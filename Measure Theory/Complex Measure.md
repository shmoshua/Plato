#Definition #MeasureTheory #FunctionalAnalysis 
> [!definition]
> For a [[measure space]] $(X,\Sigma)$, a function $\mu:\Sigma\to \mathbb{C}$ is a ***complex measure*** if:
> 1. $\mu(\varnothing)=0$ and
> 2. $\mu$ is [[Additive Functions|$\sigma$-additive]].
- **Remark**: Notice that in contrast to positive measures, $\sum_{n=1}^{}\mu(A_{n})\in \mathbb{C}$, the series has to converge, especially for any permutation of indices. Hence, $\sum_{n=1}^{}\left| \mu(A_{n}) \right|<+\infty$, i.e. it absolutely converges by Riemann.
- **Related definition**: For a complex measure $\mu:\Sigma\to \mathbb{C}$, the ***total variation*** of $\mu$ is a positive measure $\left| \mu \right|:\Sigma\to [0,+\infty]$ s.t. $$\left|  \right| (E):=\sup \left\{ \left.  \sum_{i=1}^{\infty}\left| \mu(E_{i}) \right|    \right|E=\bigsqcup_{i=1}^{\infty}E_{i},E_{i}\in \Sigma \right\}$$$\left| \mu(A) \right|\leq \left| \mu \right|(A)$ for all $A\in \Sigma$.
---
##### Properties
> [!lemma] Theorem 1
> Let $(X,\Sigma)$ be a measure space, $\mu:\Sigma\to[0,+\infty]$ a non-negative finite measure and $\nu:\Sigma\to \mathbb{C}$ a complex measure s.t. $$\left| \nu(A) \right|\leq \mu(A)\quad \forall A\in \Sigma$$
> Then, $d\nu=\rho d\mu$ where $\left| \rho \right|\leq 1$. Moreover, if $\nu$ is positive, then $0\leq\rho\leq 1$

> [!proof]-
> Let $f=\sum_{a\in\mathbb{C}}^{}a\chi_{f^{-1}[\{ a \}]}$ be a [[simple function]]. Then, $$\left| \int_{X}^{} f \, d\nu  \right| \leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \left| \nu(f^{-1}[\{ a \}]) \right|\leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \mu(f^{-1}[\{ a \}])=\int_{X}\left| f \right|  \, d\mu  $$
---
