#Definition #StatPhys

> [!definition]
> Let $G:=(V,E)$ be an undirected graph on $N$ nodes and $\Omega:=\{ \pm 1 \}^N$.  Then, 
> 1. the ***Boltzmann distribution*** is given by: $$\mu_{\beta}(x) \propto \exp(-\beta E(x))$$where the ***total energy*** $E(x):=-x^\top A_{G}x$.
- **Related definition**: We have that:
	1. ***free energy***: $F(\beta):=- \frac{1}{\beta}Z(\beta)$
	2. ***internal energy***: $U(\beta):= \frac{ \partial  }{ \partial \beta }(\beta F(\beta))$.
	3. ***shannon entropy*** $S(\beta):=\beta^{2} \frac{ \partial  }{ \partial \beta }F(\beta)$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. As $\beta\to \infty$, $\mu_{\beta}\to \text{Unif}(\arg\min_{x} E(x))$