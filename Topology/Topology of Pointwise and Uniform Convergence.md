#Definition #Topology 

> [!definition]
> For a set $X$ and the function space $\mathcal{F}(X)=\{ f:X\to \mathbb{C} \}$,
> 1. the ***topology of pointwise convergence*** $\mathcal{T}_{p}$ has $U\subseteq \mathcal{F}(X)$ is open if and only if for all $f\in U$, there exists $x_{0}\in X$ and $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X):\left| f(x_{0})-g(x_{0}) \right| <\varepsilon \}\subseteq U$$
> 2. the ***topology of uniform convergence*** $\mathcal{T}_{u}$ has $U\subseteq \mathcal{F}(X)$ is open if and only if for all $f\in U$, there exists $\varepsilon >0$ s.t. $$\{ g\in \mathcal{F}(X):\sup_{x\in X}\left| f(x)-g(x) \right| <\varepsilon \}\subseteq U$$
- **Remark**: $\mathcal{T}_{u}\subseteq \mathcal{T}_{p}$
- **Remark**: $C(X)\subseteq \mathcal{F}(X)$  is closed in $\mathcal{T}_{u}$ but not in general for $\mathcal{T}_{p}$.
---
##### Properties
> [!lemma] Lemma 1
> 