#Definition #ML 

> [!definition]
> Let $\mathcal{Y}$ be a set called labels and $\mathcal{X}$ observations. Given a [[Conditional Probability|conditional distribution]] $p(y|x)$ for $y\in \mathcal{Y},x\in \mathcal{X}$, a set of actions $\mathcal{A}$ and a cost function $c:\mathcal{Y}\times \mathcal{A}\to \mathbb{R}$,
> 1. the ***Bayesian decision*** is defined as:$$a^{*}:=\underset{ a\in \mathcal{A} }{ \arg\min }\  \mathbb{E}[c(y,a)|x]$$

^64da66

---
##### Properties
> [!lemma] Proposition 1
> Given a Gaussian conditional distribution, i.e. $p(y|x)=\mathcal{N}(\mu,\sigma^{2})$ where $\mathcal{A}=\mathbb{R}$,
> 1. with the squared loss cost function $c(y,a):=(y-a)^{2}$, $$a^{*}=\mathbb{E}[y|x]=\mu$$
> 2. with the asymmetric cost $c(y,a)=c_{1}\max(y-a,0)+c_{2}\max(a-y,0)$ for $c_{1},c_{2}>0$, then: $$a^{*}=\mu+\sigma \Phi ^{-1}\left( \frac{c_{1}}{c_{1}+c_{2}} \right)$$where $\Phi$ is the standard normal CDF.

^2d18fd

> [!proof]-
> We have:
> 1. Observe that: $$\begin{align}\mathbb{E}[(y-a)^2|x]=\mathbb{E}[y^2-2ay+a^{2}|x]=\mathbb{E}[y^2|x]-2a\mathbb{E}[y|x]+a^{2}\end{align} $$Hence, $2a^{*}-2\mathbb{E}[y|x]=0$ and $a^{*}=\mathbb{E}[y|x]=\mu$.
> 2. We have that: $$\begin{align}0=\frac{d}{da}\mathbb{E}[c(y,a)|x]&=c_{1} \frac{d}{da}\int_{a}^{\infty} (y-a)p(y|x) \, dy +c_{2} \frac{d}{da}\int_{-\infty}^{a} (a-y)p(y|x) \, dy\\&=-c_{1} \int_{a}^{\infty} p(y|x) \, dy +c_{2} \int_{-\infty}^{a} p(y|x) \, dy \\&=-c_{1}(1-F(a))+c_{2}F(a)\end{align}$$Therefore, $F(a^{*})=\frac{c_{1}}{c_{1}+c_{2}}$ and as $F(a^{*})=\Phi\left( \frac{a^{*}-\mu}{\sigma} \right)$ we have that: $$a^{*}=\mu+\sigma \Phi ^{-1}\left( \frac{c_{1}}{c_{1}+c_{2}} \right)$$

^23b6bb

---
