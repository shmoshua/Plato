#Definition #Algebra 

> [!definition]
> For a field $K$, for $n\in \mathbb{N}$ with $\text{char }K\nmid n$, the ***$n$-th roots of unity*** are defined as: $$\mu_{n}(K):=\{ \xi\in \overline{K}: \xi^n=1 \}=\text{ker}(\overline{K}^\times\to \overline{K}^\times,y\mapsto y^n)$$
- **Related Definition**: a ***primitive root*** is a generator of $\mu_{K}(n)$.
---
##### Properties

> [!lemma] Lemma 1
> We have:
> 1. $\mu_{\mathbb{Q}}(d)\subseteq \mu_{\mathbb{Q}}(n)$ if $d|n$.
> 2. if $\alpha\in \mu_{\mathbb{Q}}(d)\cap \mu_{\mathbb{Q}}(n)$ then $d|n$ or $n|d$.
---
##### Examples
> [!h] Example 1
> $\mu_{\mathbb{Q}}(n)=\{ \exp(2\pi i m / n):0\leq m<n \}$