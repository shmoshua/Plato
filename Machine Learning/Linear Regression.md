#Definition #ML 

> [!definition]
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ and $y_{1},\dots,y_{n}\in \mathbb{R}$ s.t. $y_{n}=w_{0}^\top x_{n}+\varepsilon_{n}$ where $w_{0}\in \mathbb{R}^d$ and $\varepsilon_{n} \sim$ [[Gaussian Distribution| $\mathcal{N}(0,\sigma^{2})$]] i.i.d. 
>1. ***Linear regression*** is formulated as the optimization problem: $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\sum_{i=1}^{n} (y_{i}-w^\top x_{i} )^{2}$$
>2. ***Ridge regression*** is formulated as the regularized optimization problem: $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\sum_{i=1}^{n}(y_{i}-w^\top x_{i} )^{2}+\lambda \|w\|^{2}_{2}$$where $\lambda>0$. 
---
##### Properties
> [!lemma] Proposition 1 (MLE)
> For linear regression, we have:
> 1. $w_{\text{MLE}}=(X^\top X)^{-1}X^\top y$ where $X=[x_{1}|\dots|x_{n}]^\top\in\mathbb{R}^{n,d}$. 
> 2. $\sigma^{2}_{\text{MLE}}=\frac{1}{n}\sum_{i=1}^{n}(y_{n}-w^\top x_{n})^{2}$ with unknown $\sigma_{0}$. 

> [!proof]-
> We have that:
> 1. Using [[Maximum Likelihood Estimation|MLE]] we have that $y_{n} \sim \mathcal{N}(w_{0}^\top x_{n},\sigma^{2})$
>    
>    $$\begin{align}w_{\text{MLE}}&\in \underset{ w\in \mathbb{R}^d }{ \arg\max }\left(  \log \prod_{i=1}^{n} \frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(y_{n}-w^\top x_{n})^{2}}{2\sigma^{2}} \right)\right)\\&=\underset{ w\in \mathbb{R}^d }{ \arg\min } \sum_{i=1}^{n}  (y_{n}-w^\top x_{n})^{2}\\&=\underset{ w\in \mathbb{R}^d }{ \arg\min } \left\| y-X w \right\|^2_{2} \end{align}$$As we have that: $$ \frac{d\left\| y-X w \right\| ^{2}}{dw} (w_{\text{MLE}}) = -2(w_{\text{MLE}}^\top X^\top -y^\top)X =0$$It follows that $$w_{\text{MLE}}=(X^\top X )^{-1}X^\top y$$
> 2. Using MLE, we have that: $$\begin{align}\sigma^{2}_{\text{MLE}}&\in \underset{ \sigma^{2}\geq 0 }{ \arg\max }\left(  \log \prod_{i=1}^{n} \frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(y_{n}-w^\top x_{n})^{2}}{2\sigma^{2}} \right)\right)\\&=\underset{ \sigma^{2}\geq 0 }{ \arg\min }\sum_{i=1}^{n} \frac{1}{2}\log  (2\pi\sigma^{2}) +\frac{1}{2\sigma^{2}}(y_{n}-w^\top x_{n})^{2}\\&= \underset{ \sigma^{2}\geq 0}{ \arg\min }\underbrace{ \frac{n}{2}\log  (2\pi\sigma^{2}) +\frac{1}{2\sigma^{2}}\sum_{i=1}^{n} (y_{n}-w^\top x_{n})^{2} }_{ =:\mathcal{L}(w,\sigma^{2}) }\end{align}$$Therefore, $$\frac{\partial \mathcal{L}}{\partial\sigma^{2}}(w,\sigma^{2}_{\text{MLE}})=\frac{n}{2\sigma^{2}_{\text{MLE}}}-\frac{1}{2\sigma^4_{\text{MLE}}}\sum_{i=1}^{n}(y_{n}-w^\top x_{n})^{2}=0$$and $$\sigma^{2}_{\text{MLE}}=\frac{1}{n}\sum_{i=1}^{n}(y_{n}-w^\top x_{n})^{2}$$