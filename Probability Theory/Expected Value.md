#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]] and $X$ a [[random variable]]. The ***expected value*** of $X$ is given as: $$\mathbb{E}[X]:=\int_{\Omega}^{} X \, d\mathbb{P} $$where $X$ is positive or $X$ is real or complex and $\int_{\Omega}^{} \left| X \right| \, d\mathbb{P}<+\infty$.

- **Remark**: This can be extended to when $X\in \mathbb{R}^d$ or $X\in \mathbb{C}^d$ by taking the expectation component-wise.
---
##### Properties
> [!lemma] Proposition 1 (Tailsum Formula)
> Let $X:\Omega\to[0,+\infty]$ be a random variable. Then, 
> 1. $\mathbb{E}[X]=\int_{0}^{\infty} \mathbb{P}(X\geq x) \, dx$
> 2. if $X(\Omega)\subseteq \mathbb{Z}_{\geq 0}$, then $\mathbb{E}[X]=\sum_{k=1}^{\infty}\mathbb{P}(X\geq k)$

> [!proof]-
> We have that:
> 1. Using Fubini, $$\mathbb{E}[X]=\mathbb{E}\left[ \int_{0}^{\infty} \mathbb{1}_{\{ X\geq x \}} \, dx  \right] =\int_{0}^{\infty}\mathbb{E}[\mathbb{1}_{\{ X\geq x \}}]  \, dx=\int_{0}^{\infty} \mathbb{P}(X\geq x) \, dx  $$
> 2. We have: $$\mathbb{E}[X]=\mathbb{E}\left[ \sum_{k=1}^{\infty}\mathbb{1}_{{\{ X\geq k \}}} \right] =\sum_{k=1}^{\infty}\mathbb{P}(X\geq k)$$
---
> [!lemma] Proposition 2 
> Let $X:\Omega\to (E,\mathcal{E})$ be a random variable. For every measurable function $f:E\to[0,+\infty]$, $$\mathbb{E}[f(X)]=\int_{E}^{} f\, d\mathbb{P}_{X} $$
- **Remark**: This is equivalent to the expectation of $f$ as a random variable of a pushforward probability space $(E,\mathcal{E},\mathbb{P}_{X})$. 
- **Remark**: This can be extended to real- or complex-valued $f$ if $\mathbb{E}[\left| f(X) \right|]<+\infty$. 