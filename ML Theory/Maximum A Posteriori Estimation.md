#Definition #ML 

> [!def]
> Let $\Theta$ be a [[random variable]] representing the ***parameter*** of the [[Distribution|distribution]] on a probability space $(\Omega,\mathcal{A},\mathbb{P})$. Let $(x_{1},\dots,x_{n})$ be the iid realizations of probability mass function $p_{X}(\cdot|\Theta=\theta)$ (if $X$ discrete) and density $f_{X}(\cdot|\Theta=\theta)$ (if $X$ continuous). 
> 
> 1. the ***maximum a posteriori (MAP) estimation*** is to find: $$\widehat{\theta}_{\text{MAP}}\in \underset{ \theta\in \Theta }{ \arg\max }\ p_{\Theta}(\theta|x_{1},\dots,x_{n})=\underset{ \theta\in \Theta }{ \arg\max }\ p(x_{1},\dots,x_{n}|\theta )p_{\Theta}(\theta)$$