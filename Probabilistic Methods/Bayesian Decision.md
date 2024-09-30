#Definition #ProbabilisticMethods 

> [!definition]
> Let $\mathcal{Y}$ be a set called labels and $\mathcal{X}$ observations. Given a conditional distribution $p(y|x)$ for $y\in \mathcal{Y},x\in \mathcal{X}$, a set of actions $\mathcal{A}$ and a cost function $c:\mathcal{Y}\times \mathcal{A}\to \mathbb{R}$,
> 1. the Ba
> 
> We have: $$a^{*}=\underset{ a\in \mathcal{A} }{ \arg\min }\  \mathbb{E}[C(y,a)|X]$$
---
##### Properties
> [!lemma] Proposition 1
> We have:
> 1. $a^{*}=\mathbb{E}[Y|x]=\int   \, dx$