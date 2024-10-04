#Definition #ProbabilityTheory 

> [!definition]
> Let $X:\Omega\to \mathbb{R}^d$ be a [[random variable]]. The ***characteristic function*** of $X$ is the function : $$\Phi_{X}:\mathbb{R}^d\to \mathbb{C},\quad \xi\mapsto \mathbb{E}[\exp(i\braket{ \xi , X } )]=\int_{\mathbb{R}^d}^{} \exp(i\braket{ \xi , x } ) p(x)\, dx $$
- **Remark**: in other words, $\Phi_{X}$ is the Fourier transform of $\widehat{\mathbb{P}}_{X}$.
---
##### Properties
> [!lemma] Proposition 1 
> Let $(X_{1},X_{2})$ be a joint random variable. Then, 
> 1. $\Phi_{X_{1}}(\xi_{1})=\Phi_{(X_{1},X_{2})}(\xi_{1},0)$ and $\Phi_{X_{2}}(\xi_{2})=\Phi_{(X_{1},X_{2})}(0,\xi_{2})$

> [!proof]-
> We have: 
> 1. $$\Phi_{X_{1}}(\xi_{1})=\mathbb{E}[\exp(i \xi_{1}^\top X_{1})]=\mathbb{E}[\exp(i( \xi_{1}^\top X_{1}+0^\top X_{2}))]=\Phi_{(X_{1},X_{2})}(\xi_{1},0)$$
---
