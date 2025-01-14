#Definition #PAI 

> [!definition]
> Let $\mathcal{P}$ be a family of distributions and $\mathcal{Q}\subseteq \mathcal{P}$ a subfamily called ***variational family***. Then, 
> 1. the ***variational inference*** of $p\in \mathcal{P}$ is given by: $$\mathcal{q}^{*}\in \underset{ q\in \mathcal{Q} }{ \arg\min }\  D(q\|p)$$where $D(q\|p)$ is the [[relative entropy]] of $q$ and $p$. 

^baa2ac

- **Remark**: Common variational families are Gaussian distributions, Gaussian distributions with diagonal covariance, etc. ^b6c367
- **Remark**: One can compute $D(p\|q)$ too, but in general this is more computationally intensive.  ^473bab
---
##### Properties
> [!lemma] Proposition 1 (Variational Inference with Posterior and Gaussian Variational Family)
> Let $p:=p(\cdot|y)$ be the posterior we want to model using Gaussian variational family. Then, 
> 1. $q^{*}=\arg\max_{q\in \mathcal{Q}} \mathbb{E}_{\theta \sim q}[\log p(\theta,y)]+H(q)$
> 2. $q^{*}=\arg\max_{q\in \mathcal{Q}}\mathbb{E}_{\theta \sim q}[\log p(y|\theta)]-D(q\|p(\cdot))$ where $p(\cdot)$ is the prior. 
> 3. $\log p(y_{1:n})\geq D(q^{*}\|p)$

^8f7c5f

> [!proof]- 
> We have:
> 1. Let $p(\theta|y)=\frac{1}{z}p(\theta,y)$ for some constant $z$. Then: $$\begin{align}q^{*}&=\underset{ q\in \mathcal{Q} }{ \arg\min }\  \mathbb{E}_{\theta \sim q}\left[ \log \frac{z\cdot q(\theta)}{p(\theta,y)} \right]\\&=\underset{ q\in \mathcal{Q} }{ \arg\min }\  \mathbb{E}_{\theta \sim q}\left[\log z+\log q(\theta)-\log{p(\theta,y)} \right]\\&=\underset{ q\in \mathcal{Q} }{ \arg\min }  (-H(q)-\mathbb{E}_{\theta \sim q}\left[\log{p(\theta,y)} \right])\\&=\underset{ q\in \mathcal{Q} }{ \arg\max }(   \mathbb{E}_{\theta \sim q}\left[\log{p(\theta,y)} \right]+H(q))\end{align}$$
> 2. And for 2, $$\begin{align}q^{*}&=\underset{ q\in \mathcal{Q} }{ \arg\max }\   \mathbb{E}_{\theta \sim q}[\log p(y|\theta) +\log p(\theta )-\log q(\theta)]\\&=\underset{ q\in \mathcal{Q} }{ \arg\max }\   \mathbb{E}_{\theta \sim q}[\log p(y|\theta)]-D(q\|p(\cdot ))\end{align}$$
> 3. We have that: $$\begin{align}\log p(y_{1:n})&=\log \int_{\Theta}p(y|\theta)p(\theta)  \, d\theta\\&=\log \int_{\Theta}p(y|\theta)\frac{p(\theta)}{q(\theta)}q(\theta)  \, d\theta \\&=\log\mathbb{E}_{\theta \sim q}\left[ p(y|\theta)\frac{p(\theta)}{q(\theta)} \right]\\&\geq \mathbb{E}_{\theta \sim q}\left[ \log p(y|\theta)-\log \frac{q(\theta)}{p(\theta)} \right]\\&=\mathbb{E}_{\theta \sim q}\left[ \log p(y|\theta)\right] -D(q\|p)\end{align}$$where we use [[Expected Value|Jensen's inequality]]. 

^26b614

---
> [!lemma] Lemma 2 (Reparametrization Trick)
> Let $\lambda$ be a random variable and $\varepsilon \sim \phi$ also a random variable that is independent of $\lambda$. If $g_{\eta}:\mathbb{R}^d\to \mathbb{R}^d$ is a $C_{1}$-diffeomorphism for all $\eta$ s.t. $\theta:=g_{\lambda}(\varepsilon)$, we have that: $$\mathbb{E}_{\theta \sim q_{\lambda}}[f(\theta)]=\mathbb{E}_{\varepsilon \sim \phi}[f(g_{\lambda}(\varepsilon))]$$for measurable $f:\mathbb{R}^d\to \mathbb{R}^n$.

^e5c51e

> [!proof]-
> Using $\varepsilon =g^{-1}_{\lambda}(\theta)$, we have: $$\begin{align}q_{\lambda}(\theta)&=\phi(\varepsilon)\cdot \left| \det(D_{\theta}g_{\lambda}^{-1}) \right| \\&=\phi(\varepsilon)\cdot \left| \det((D_{\varepsilon}g_{\lambda})^{-1}) \right|\\&=\phi(\varepsilon)\cdot \left| \det(D_{\varepsilon}g_{\lambda}) \right|^{-1}\end{align}$$Therefore, $$\begin{align}\mathbb{E}_{\theta \sim q_{\lambda}}[f(\theta)]&=\int_{\Theta}^{} f(\theta) q_{\lambda}(\theta)\, d\theta \\&=\int_{E}^{}f(g_{\lambda}(\varepsilon)) q_{\lambda}(g_{\lambda}(\varepsilon))\left| \det \text{D}_{\varepsilon}g_{\lambda} \right|  \, d\varepsilon\\&=\int_{E}^{}f(g_{\lambda}(\varepsilon)) \phi(\varepsilon) \, d\varepsilon \\&=\mathbb{E}_{\varepsilon \sim \phi}[f(g_{\lambda}(\varepsilon))]\end{align} $$

^e82d58

- **Corollary**: $\nabla_{\lambda}\mathbb{E}_{\theta \sim q_{\lambda}}[f(\theta)]=\nabla_{\lambda}\mathbb{E}_{\varepsilon \sim \phi}[f(g_{\lambda}(\varepsilon))]=\mathbb{E}_{\varepsilon \sim \phi}[\nabla_{\lambda}f(g_{\lambda}(\varepsilon))]$ ^719723
---
##### Examples
> [!h] Example 1 (Variational Inference for Bayesian Logistic Regression)
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ and $y_{1},\dots,y_{n}\in \{ \pm 1 \}$ the labels. Assume we have:
> 1. For all $x_{i}\in \mathbb{R}^d$ and $y_{i}\in \{ \pm 1 \}$, $$\mathbb{P}(Y_{i}=y_{i}|x_{i},w)=\sigma(y_{i}w^\top x_{i})$$ independently where $w\in \mathbb{R}^d$ parameter and $\sigma:\mathbb{R}\to \mathbb{R},x\mapsto \frac{1}{1-\exp(-x)}$ is the sigmoid function. 
> 1. Gaussian prior: $p(w)=\mathcal{N}(w;0,\sigma^{2}_{p}I)$ for $\sigma_{p}\in \mathbb{R}$.
> 
> With diagonal Gaussian variational family $\mathcal{Q}:=\{ \mathcal{N}(w;\mu,\Sigma):\Sigma \text{ is SPD}\}$, 
> 1. $\nabla_{C,\mu}L(C,\mu)=\nabla_{C,\mu}\mathbb{E}_{\varepsilon \sim \mathcal{N}(0,1)}[\log p(y|C\varepsilon+\mu)]-\nabla_{C,\mu}D(q_{C,\mu}\|p(\cdot))$ where $p$ is the prior and: $$L(C,\mu):=\mathbb{E}_{\theta \sim q_{C,\mu}}[\log p(y|\theta)]-D(q_{C,\mu}\|p(\cdot))$$and $q_{C,\mu}=\mathcal{N}(\mu,CC^\top)\in \mathcal{Q}$ given by the [[cholesky decomposition]].

^cd942b

- **Remark**: The first term can be approximated using Monte Carlo methods and Law of Large Numbers.  ^0bbd4c
---
