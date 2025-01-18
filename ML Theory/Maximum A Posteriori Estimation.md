#Definition #ML 

> [!definition]
> Let $\Theta$ be a [[random variable]] representing the ***parameter*** of the [[Distribution|distribution]] on a probability space $(\Omega,\mathcal{A},\mathbb{P})$. Let $(x_{1},\dots,x_{n})$ be the iid realizations of probability mass function $p_{X}(\cdot|\Theta=\theta)$ (if $X$ discrete) and density $f_{X}(\cdot|\Theta=\theta)$ (if $X$ continuous). 
> 
> 1. the ***maximum a posteriori (MAP) estimation*** is to find: $$\widehat{\theta}_{\text{MAP}}\in \underset{ \theta\in \Theta }{ \arg\max }\ p_{\Theta}(\theta|x_{1},\dots,x_{n})=\underset{ \theta\in \Theta }{ \arg\max }\ p(x_{1},\dots,x_{n}|\theta )p_{\Theta}(\theta)$$

^010b53

- **Remark**: $\underset{ \theta\in \Theta }{ \arg\max }\ p(x_{1},\dots,x_{n}|\theta )p_{\Theta}(\theta)=\underset{ \theta\in \Theta }{ \arg\max }\ \log p(x_{1},\dots,x_{n}|\theta )+\log p_{\Theta}(\theta)$. ^935410


$$\begin{align}D(q\|p)&=\int_{\mathbb{R}^3}^{}(\log q(\theta,r)-\log p(\theta,r))q(\theta,r)  \, d(\theta,r)\\&=\int_{\mathbb{R}^3}^{}(\log q_{\theta}(\theta)+\log q_{\alpha}(\alpha)-\log p(\theta))q(\theta,r)  \, d(\theta,r) \end{align}$$