#Definition #ProbabilisticMethods 

> [!definition]
> Let $\mathcal{Y}$ be a set called labels and $\mathcal{X}$ observations. Given a [[Conditional Probability|conditional distribution]] $p(y|x)$ for $y\in \mathcal{Y},x\in \mathcal{X}$, a set of actions $\mathcal{A}$ and a cost function $c:\mathcal{Y}\times \mathcal{A}\to \mathbb{R}$,
> 1. the ***Bayesian decision*** is defined as:$$a^{*}:=\underset{ a\in \mathcal{A} }{ \arg\min }\  \mathbb{E}[c(y,a)|x]$$
---
##### Properties
> [!lemma] Proposition 1
> Given a Gaussian conditional distribution, i.e. $p(y|x)=\mathcal{N}(\mu,\sigma^{2})$ where $\mathcal{A}=\mathbb{R}$,
> 1. with the squared loss cost function $c(y,a):=(y-a)^{2}$, $$a^{*}=\mathbb{E}[y|x]=\mu$$
> 2. with the asymmetric cost $c(y,a)=c_{1}\max(y-a,0)+c_{2}\max(a-y,0)$ for $c_{1},c_{2}>0$, then: $$$$

> [!proof]+
> We have:
> 1. Observe that: $$\begin{align}\mathbb{E}[(y-a)^2|x]=\mathbb{E}[y^2-2ay+a^{2}|x]=\mathbb{E}[y^2|x]-2a\mathbb{E}[y|x]+a^{2}\end{align} $$Hence, $2a^{*}-2\mathbb{E}[y|x]=0$ and $a^{*}=\mathbb{E}[y|x]=\mu$.
> 2. Observe that: $$\mathbb{E}[c_{1}\max(y-a,0)+c_{2}\max(a-y,0)|x]=c_{1}\mathbb{E}[\max(y-a,0)|x]+c_{2}\mathbb{E}[\max(a-y,0)|x]$$Then, $$\begin{align}\mathbb{E}[\max(y-a,0)|x]&=\frac{1}{2}\mathbb{E}[y-a-\left| y-a \right| |x ]\\&=\frac{1}{2}\left( \mu-a-\mathbb{E}[\left| y-a \right| |x] \right)\end{align}$$
>    Therefore, $$\mathbb{E}[c(y,a)|x]=\frac{c_{1}}{2}(\mu-a-\mathbb{E}[\left| y-a \right| |x])+\frac{c_{2}}{2}(a-\mu-\mathbb{E}[\left| y-a \right||x ]) $$
>    where from [[Gaussian Distribution|Proposition 4]], $$\begin{align}\mathbb{E}[\left| y-a \right| |x]&=\sigma \sqrt{ \frac{2}{\pi} }+\frac{(\mu-a)\sqrt{ \pi }}{\sigma}\end{align}$$Therefore, $$-\frac{c_{1}}{2}+\frac{c_{1}\sqrt{ \pi }}{2\sigma}+\frac{c_{2}}{2}+\frac{c_{2}\sqrt{ \pi }}{2\sigma}=0$$
