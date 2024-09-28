#Definition #ML 

> [!definition]
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ and $y_{1},\dots,y_{n}\in \mathbb{R}$ s.t. $y_{n}=w_{0}^\top x_{n}+\varepsilon_{n}$ where $w_{0}\in \mathbb{R}^d$ and $\varepsilon_{n} \sim$ [[Gaussian Distribution| $\mathcal{N}(0,\sigma^{2})$]] i.i.d. 
>1. ***Linear regression*** is formulated as the optimization problem: $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\sum_{i=1}^{n} (y_{i}-w^\top x_{i} )^{2}$$
>2. ***Ridge regression*** is formulated as the regularized optimization problem: $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\sum_{i=1}^{n}(y_{i}-w^\top x_{i} )^{2}+\lambda \|w\|^{2}_{2}$$where $\lambda>0$. 
---
##### Properties
> [!lemma] Proposition 1 (MLE)
> We have that:
> 1. $w_{\text{MLE}}=(X^\top X)^{-1}X^\top y$ where $X=[x_{1}|\dots|x_{n}]^\top\in\mathbb{R}^{n,d}$. 

> [!proof]+
> We have that:
> 1. Using [[Maximal Likelihood Estimation|MLE]] we have that $y_{n} \sim \mathcal{N}(w_{0}^\top x_{n},\sigma^{2})$
>    
>    $$\begin{align}w_{\text{MLE}}&\in \underset{ w\in \mathbb{R}^d }{ \arg\max }\left(  \log \prod_{i=1}^{n} \frac{1}{\sigma\sqrt{ 2\pi }}\exp\left( -\frac{(y_{n}-w^\top x_{n})^{2}}{2\sigma^{2}} \right)\right)\\&=\underset{ w\in \mathbb{R}^d }{ \arg\min } \sum_{i=1}^{n}  (y_{n}-w^\top x_{n})^{2}\\&=\underset{ w\in \mathbb{R}^d }{ \arg\min } \left\| y-X^\top w \right\|^2_{2} \end{align}$$As we have that: $$\left. \frac{d\left\| y-X^\top w \right\| ^{2}}{dw} \right|   $$