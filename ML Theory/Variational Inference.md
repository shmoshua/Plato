#Definition #PAI 

> [!definition]
> Let $\mathcal{P}$ be a family of distributions and $\mathcal{Q}\subseteq \mathcal{P}$ a subfamily called ***variational family***. Then, 
> 1. the ***variational inference*** of $p\in \mathcal{P}$ is given by: $$\mathcal{q}^{*}\in \underset{ q\in \mathcal{Q} }{ \arg\min }\  D(q\|p)$$where $D(q\|p)$ is the [[relative entropy]] of $q$ and $p$. 
- **Remark**: Common variational families are Gaussian distributions, Gaussian distributions with diagonal covariance, etc.
- **Remark**: One can compute $D(p\|q)$ too, but in general this is more computationally intensive. 
---
##### Properties
> [!lemma] Proposition 1 (Variational Inference with Posterior and Gaussian Variational Family)
> Let $p:=p(\cdot|y)$ be the posterior we want to model using Gaussian variational family. Then, 
> 1. $q^{*}=\arg\max_{q\in \mathcal{Q}} \mathbb{E}_{\theta \sim q}[\log p(\theta,y)]+H(q)$
> 2. $q^{*}=\arg\max_{q\in \mathcal{Q}}\mathbb{E}_{\theta \sim q}[\log p(y|\theta)]-D(q\|p(\cdot))$ where $p(\cdot)$ is the prior. 
> 3. $\log p(y_{1:n})\geq D(q^{*}\|p)$

> [!proof]- 
> We have:
> 1. Let $p(\theta|y)=\frac{1}{z}p(\theta,y)$ for some constant $z$. Then: $$\begin{align}q^{*}&=\underset{ q\in \mathcal{Q} }{ \arg\min }\  \mathbb{E}_{\theta \sim q}\left[ \log \frac{z\cdot q(\theta)}{p(\theta,y)} \right]\\&=\underset{ q\in \mathcal{Q} }{ \arg\min }\  \mathbb{E}_{\theta \sim q}\left[\log z+\log q(\theta)-\log{p(\theta,y)} \right]\\&=\underset{ q\in \mathcal{Q} }{ \arg\min }  (-H(q)-\mathbb{E}_{\theta \sim q}\left[\log{p(\theta,y)} \right])\\&=\underset{ q\in \mathcal{Q} }{ \arg\max }(   \mathbb{E}_{\theta \sim q}\left[\log{p(\theta,y)} \right]+H(q))\end{align}$$
> 2. And for 2, $$\begin{align}q^{*}&=\underset{ q\in \mathcal{Q} }{ \arg\max }\   \mathbb{E}_{\theta \sim q}[\log p(y|\theta) +\log p(\theta )-\log q(\theta)]\\&=\underset{ q\in \mathcal{Q} }{ \arg\max }\   \mathbb{E}_{\theta \sim q}[\log p(y|\theta)]-D(q\|p(\cdot ))\end{align}$$
> 3. We have that: $$\begin{align}\log p(y_{1:n})&=\log \int_{\Theta}p(y|\theta)p(\theta)  \, d\theta\\&=\log \int_{\Theta}p(y|\theta)\frac{p(\theta)}{q(\theta)}q(\theta)  \, d\theta \\&=\log\mathbb{E}_{\theta \sim q}\left[ p(y|\theta)\frac{p(\theta)}{q(\theta)} \right]\\&\geq \mathbb{E}_{\theta \sim q}\left[ \log p(y|\theta)-\log \frac{q(\theta)}{p(\theta)} \right]\\&=\mathbb{E}_{\theta \sim q}\left[ \log p(y|\theta)\right] -D(q\|p)\end{align}$$where we use [[Expected Value|Jensen's inequality]]. 

---
> [!lemma] Lemma 2 (Reparametrization Trick)
> Let $\lambda$ be a random variable and $\varepsilon \sim \phi$ also a random variable that is independent of $\lambda$. If $g_{\eta}:\mathbb{R}^d\to \mathbb{R}^d$ is a differentiable and invertible function for all $\eta$ s.t. $\theta:=g_{\lambda}(\varepsilon)$, we have that: $$\mathbb{E}_{\theta \sim q_{\lambda}}[f(\theta)]=\mathbb{E}_{\varepsilon \sim \phi}[f(g_{\lambda}(\varepsilon))]$$for measurable $f:\mathbb{R}^d\to \mathbb{R}^n$

> [!proof]+
> Using $\varepsilon =g^{-1}_{\lambda}(\theta)$, we have: $$\begin{align}q_{\lambda}(\theta)&=\phi(\varepsilon)\cdot \left| \det(D_{\theta}g_{\lambda}^{-1}) \right| \\&=\phi(\varepsilon)\cdot \left| \det((D_{\varepsilon}g_{\lambda})^{-1}) \right|\\&=\phi(\varepsilon)\cdot \left| \det(D_{\varepsilon}g_{\lambda}) \right|^{-1}\end{align}$$Therefore, $$\mathbb{E}_{\theta \sim q_{\lambda}}[f(\theta)]=\int_{\Theta}^{} f(\theta) q_{\lambda}(\theta)\, d\theta=\int_{\Theta}^{} f(g_{\lambda}(\varepsilon)) \phi(\varepsilon)\cdot \left| \det(D_{\varepsilon}g_{\lambda}) \right|^{-1}\, d\theta= $$