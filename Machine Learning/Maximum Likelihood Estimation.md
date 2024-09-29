#Definition #ML 

> [!definition]
> Let $\{ P_{\theta} \}_{\theta\in \Theta}$ be a set of [[Distribution|distributions]] on a probability space $(\Omega,\mathcal{A},\mathbb{P})$ with probability mass function $p_{\theta}$ if discrete and [[Density|densities]] $f_{\theta}$ if continuous. Let $X\sim P_{\theta_{0}}$ where $\theta_{0}\in \Theta$ denotes the true distribution. 
> 1. the ***maximum likelihood estimation (MLE)*** is to find: $$\widehat{\theta}\in \underset{ \theta\in \Theta }{ \arg\max }\ f_{\theta}(x) $$

^fe8cee

- **Remark**: We have that $\underset{ \theta\in \Theta }{ \arg\max }\ f(X|\theta)=\underset{ \theta\in \Theta }{ \arg\max } \log f(X|\theta)$. ^6a1148
---
