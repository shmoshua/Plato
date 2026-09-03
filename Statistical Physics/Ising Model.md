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
> 2. $S(\beta)=-\sum_{x} \mu_{\beta}(x)\ln \mu_{\beta}(x)$, i.e. it is the Shannon entropy.
> 3. $U(\beta)=\sum_{x}^{}\mu_{\beta}(x)E(x)$, i.e. the internal energy is the average energy. 
> 4. $F(\beta)=U(\beta)-\frac{1}{\beta}\cdot S(\beta)$, i.e. the free energy is the difference between internal energy and temperature times entropy.

> [!proof]+
> We have that:
> 1. Clear. 
> 2. We have: $$\frac{ \partial  }{ \partial \beta } F(\beta)= \frac{1}{\beta^{2}}Z(\beta)-\frac{1}{\beta}\frac{ \partial  }{ \partial \beta } Z(\beta)=\frac{1}{\beta^{2}}Z(\beta)+\frac{1}{\beta}Z(\beta)\sum_{x} E(x)\mu_{\beta}(x)$$Hence, $$S(\beta)=Z(\beta)\left( 1+\beta \sum_{x}E(x)\mu_{\beta}(x) \right)$$