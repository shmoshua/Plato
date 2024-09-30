#Definition #ProbabilisticMethods 

> [!definition]
> Let $\mathcal{Y}$ be a set called labels and $\mathcal{X}$ observations. Given a [[Conditional Probability|conditional distribution]] $p(y|x)$ for $y\in \mathcal{Y},x\in \mathcal{X}$, a set of actions $\mathcal{A}$ and a cost function $c:\mathcal{Y}\times \mathcal{A}\to \mathbb{R}$,
> 1. the ***Bayesian decision*** is defined as:$$a^{*}:=\underset{ a\in \mathcal{A} }{ \arg\min }\  \mathbb{E}[c(y,a)|x]$$
---
##### Properties
> [!lemma] Proposition 1
> Given a Gaussian conditional distribution, i.e. $p(y|x)=\mathcal{N}(\mu,\sigma^{2})$ where $\mathcal{A}=\mathbb{R}$,
> 1. with the cost function $c(y,a):=(y-a)^{2}$, $$$$

> [!proof]+
> We have:
> 1. $\mathbb{E}[(y-a)^{2}|x]=\int_{\mathcal{Y}}(y-a)^{2}\cdot p(y|x) \, dy=\mu$.