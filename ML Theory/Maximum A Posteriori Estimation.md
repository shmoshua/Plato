#Definition #ML 

> [!definition]
> Let $\Theta$ be a [[random variable]] representing the ***parameter*** of the [[Distribution|distribution]] on a probability space $(\Omega,\mathcal{A},\mathbb{P})$. Let $(x_{1},\dots,x_{n})$ be the iid realizations of probability mass function $p_{X}(\cdot|\Theta=\theta)$ (if $X$ discrete) and density $f_{X}(\cdot|\Theta=\theta)$ (if $X$ continuous). 
> 
> 1. the ***maximum a posteriori (MAP) estimation*** is to find: $$\widehat{\theta}_{\text{MAP}}\in \underset{ \theta\in \Theta }{ \arg\max }\ p_{\Theta}(\theta|x_{1},\dots,x_{n})=\underset{ \theta\in \Theta }{ \arg\max }\ p(x_{1},\dots,x_{n}|\theta )p_{\Theta}(\theta)$$

^010b53

- **Remark**: $\underset{ \theta\in \Theta }{ \arg\max }\ p(x_{1},\dots,x_{n}|\theta )p_{\Theta}(\theta)=\underset{ \theta\in \Theta }{ \arg\max }\ \log p(x_{1},\dots,x_{n}|\theta )+\log p_{\Theta}(\theta)$. ^935410


$$\begin{align}D(q\|p)&=\int_{\mathbb{R}^3}^{}(\log q(\theta,\alpha)-\log p(\theta,\alpha))q(\theta,\alpha)  \, d(\theta,\alpha)\\&=\int_{\mathbb{R}^3}^{}(\log q_{\theta}(\theta)+\log q_{\alpha}(\alpha)-\log p(\theta)-\log p(\alpha))q_{\theta}(\theta)q_{\alpha}(\alpha)  \, d(\theta,\alpha)\\&=\int_{\mathbb{R}^3}^{}\left( \log \frac{q_{\theta}(\theta)}{p(\theta)}\right)q_{\theta}(\theta)q_{\alpha}(\alpha)  \, d(\theta,\alpha)+\int_{\mathbb{R}^3}^{}\left( \log \frac{q_{\alpha}(\alpha)}{p(\alpha)}\right)q_{\theta}(\theta)q_{\alpha}(\alpha)  \, d(\theta,\alpha)\\&=\int_{\mathbb{R}^2}^{}\left( \log \frac{q_{\theta}(\theta)}{p(\theta)}\right)q_{\theta}(\theta) \, d\theta+\int_{\mathbb{R}}^{}\left( \log \frac{q_{\alpha}(\alpha)}{p(\alpha)}\right)q_{\alpha}(\alpha)  \, d\alpha\\&=D(q_{\theta}\|p)+D(q_{\alpha}\|p)\end{align}$$
Then, as $p(\theta):=\mathcal{N}(\theta;0,I)$
$$\begin{align}D(q_{\theta}\|p)=\frac{1}{2}\left( \text{tr}(\Sigma_{\theta}+\mu_{\theta}\mu_{\theta}^\top)-2-\log \det(\Sigma_{\theta}) \right)\end{align}$$and as $p(\alpha):=\mathcal{N}(\alpha;2,1)$, $$D(q_{\alpha}\|p)=\frac{1}{2}\left( \Sigma_{\alpha}+(2-\mu_{\alpha})^{2}-1-\log\Sigma_{\alpha}\right) $$Hence, $$D(q\|p)=\frac{1}{2}(\text{tr}(\Sigma_{\theta}+\mu_{\theta}\mu_{\theta}^\top)-\log \det(\Sigma_{\theta})+\Sigma_{\alpha}+1-4\mu_{\alpha}+\mu_{\alpha}^{2}-\log\Sigma_{\alpha})$$

---

We have that: $$\begin{align}\log p(\alpha,\theta|\mathcal{D})=\log p(\mathcal{D}|\alpha,\theta)+\log p(\alpha)+\log p(\theta)\end{align}$$First, notice that  $y_{i}{\bot}y_{j}|\theta$. Secondly, we have that: $\exp(\alpha)\varepsilon|\alpha \sim \mathcal{N}(0,\exp(\alpha)^{2})$ and $$y:=\theta^\top\sigma(\Lambda x)+\exp(\alpha)\varepsilon|\alpha,\theta,x\sim \mathcal{N}(\theta^\top\sigma(\Lambda x),\exp(\alpha)^{2})$$ Therefore, $$\log p(\mathcal{D}|\alpha,\theta)=\log \prod_{i=1}^{50}p(y_{i}|\alpha,\theta,x_{i})=\sum_{i=1}^{50}\left( -\frac{1}{2}\log \exp(\alpha)^{2}-\frac{1}{2}\frac{(y_{i}-\theta^\top\sigma(\Lambda x_{i}))^{2}}{} \right)$$