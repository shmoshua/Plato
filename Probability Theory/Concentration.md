#Definition #AGAO 

> [!definition]

---
##### Properties
> [!lemma] Theorem 1 (Bernstein)
> Let $X_{1},\dots,X_{k}$ be independent, zero-mean real random variables iwth $\left| X_{i} \right|\leq R$. For $X:= \sum_{i}^{}X_{i}$ and $\sigma^{2}:= \text{Var}(X)$, we have: $$\mathbb{P}(\left| X \right| \geq t)\leq 2\exp \left( -\frac{t^{2}}{2Rt+4\sigma^{2}} \right),\quad \forall t>0 $$

> [!proof]+
> We have that for any $\theta>0$: $$\mathbb{P}(X\geq t)=\mathbb{P}(\exp(\theta X)\geq \exp(\theta t))\leq \exp(-\theta t)\mathbb{E}[\exp(\theta X)]$$Now, if $\theta\leq \frac{1}{R}$, then: $$\exp(z)\leq 1+z+z^{2},\quad \forall \left| z \right| \leq 1$$