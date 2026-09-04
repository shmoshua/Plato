#Definition #StatPhys

> [!definition]
> Let $G:=(V,E)$ be an undirected graph on $N$ nodes and $\Omega:=\{ \pm 1 \}^N$.  Then, 
> 1. the ***Boltzmann distribution*** is given by: $$\mu_{\beta}(x) \propto \exp(-\beta E(x))$$where the ***total energy*** $E(x):=-x^\top A_{G}x$.
- **Related definition**: We have that:
	1. ***free energy***: $F(\beta):=- \frac{1}{\beta}\ln Z(\beta)$
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

> [!proof]-
> We have that:
> 1. Clear. 
> 2. We have: $$\frac{ \partial  }{ \partial \beta } F(\beta)= \frac{1}{\beta^{2}}\ln Z(\beta)-\frac{1}{\beta}\frac{ \partial  }{ \partial \beta } \ln Z(\beta)=\frac{1}{\beta^{2}}\ln Z(\beta)+\frac{1}{\beta}\sum_{x} E(x)\mu_{\beta}(x)$$Hence, $$S(\beta)=\ln Z(\beta)+ \sum_{x}\beta E(x)\mu_{\beta}(x)=-\sum_{x}\mu_{\beta}(x)\left(  -\beta E(x)-\ln Z(\beta)\right) =-\sum_{x}^{}\mu_{\beta}(x)\ln \mu_{\beta}(x)$$
> 3. We have: $$U(\beta)=F(\beta)+\frac{1}{\beta}\ln Z(\beta)+\sum_{x}E(x)\mu_{\beta}(x)=\sum_{x}E(x)\mu_{\beta}(x)$$
> 4. We have that: $$U(\beta)-\frac{1}{\beta}S(\beta)=\frac{1}{\beta}\sum_{x}^{}\mu_{\beta}(x)(\beta E(x)+\ln \mu_{\beta}(x))=\frac{1}{\beta}\sum_{x}^{}\mu_{\beta}(x)(-\ln Z(\beta))=-\frac{1}{\beta}\ln Z(\beta)$$
---
> [!lemma] Proposition 2 (Upper Bound on Gap)
> Let $M:=\min_{x} E(x)$. Then, $$\mathbb{E}_{\mu_{\beta}}E - M\le  \frac{n\ln 2}{\beta}$$

> [!proof]-
> We have that: $$Z(\beta)=\sum_{x}^{}\exp(-\beta E(x)) \geq \exp(-\beta M)$$Then, $\log Z_{\beta} \geq -\beta M$. Therefore, we have that from 1.4: $$-\beta M\leq\ln Z(\beta)=-\beta \cdot \mathbb{E}_{\mu_{\beta}}E+S(\beta)\le -\beta \cdot \mathbb{E}_{\mu_{\beta}}E+n\ln 2$$This proves the statement.
- **Corollary**: If we choose $\beta \sim 1/\varepsilon$, we can get $\varepsilon n$-close to optimal in expectation.