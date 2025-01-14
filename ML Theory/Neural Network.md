#Definition #PAI 

> [!definition]
> A ***$L$-layer neural network*** is a function $f_{\theta}:\mathbb{R}^d\to \mathbb{R}^k$ given by: $$f_{\theta}(x):=\varphi_{L}(W_{L}\cdot \varphi_{L-1}(W_{L-1}\cdot \dots \varphi_{1}(W_{1}x)))$$where $\varphi_{1},\dots,\varphi_{L}:\mathbb{R}\to \mathbb{R}$ are applied component-wise and $\theta:=(W_{1},\dots,W_{L})$ are weights where $W_{i}\in \text{Mat}_{n_{i}\times n_{i-1}}$

^1d6c4a

---
##### Properties
> [!lemma] Proposition 1 (Gaussian Prior)
> Let $\theta \sim \mathcal{N}(0,\sigma_{p}^{2}I)$. Then, 
> 1. 