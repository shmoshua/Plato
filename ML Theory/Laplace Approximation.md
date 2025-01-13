#Definition #PAI 

> [!definition]
> Let $p:\mathbb{R}^n\to \mathbb{R}_{> 0}$ be a twice differentiable function s.t. $\int_{\mathbb{R}^n}^{} p \, dx=1$. Then, 
> 1. the ***Laplace approximation*** of $p$ is given by the Gaussian distribution $$q(x):=\mathcal{N}(x; \widehat{x},-(\text{H}_{\widehat{x}}f)^{-1})$$where $f = \log \circ p$, $\widehat{x}:=\arg\max_{x\in \mathbb{R}^n}f(x)$ and  $\text{H}_{\widehat{x}}f$ denotes the [[Hessian]] of $f$. 
---
##### Properties
> [!lemma] Proposition 1
> Let $f:\mathbb{R}^n\to \mathbb{R}$ be a twice differentiable. Then, 
> 1. $q(x)\propto\exp(\widehat{f}(x))$ where $\widehat{f}$ is the Taylor polynomial of $f$ of degree 2.

> [!proof]-
> We have that:
> 1. Let $\widehat{f}$ be the Taylor polynomial of $f$ of degree 2. Then, $$\widehat{f}(x)=f(\widehat{x})+\text{D}_{\widehat{x}}f(x-\widehat{x})+\frac{1}{2}(x-\widehat{x})^\top \text{H}_{\widehat{x}}f(x-\widehat{x})$$However, as $\widehat{x}$ is a maximum, $\text{D}_{\widehat{x}}f=0$ and $\text{H}_{\widehat{x}}f$ is symmetric negative semidefinite. Hence, $-\text{H}_{\widehat{x}}f$ is SPsD and we have that: $$q(x)\propto \exp \left(  \frac{1}{2}(x-\widehat{x})^\top\text{H}_{\widehat{x}}f(x-\widehat{x})\right)=\text{exp}(\widehat{f}(x)-f(\widehat{x}))  \propto \exp(\widehat{f}(x))$$
---
##### Examples
> [!h] Example 1 (Bayesian Logistic Regression)
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ and $y_{1},\dots,y_{n}\in \{ \pm 1 \}$ the labels. Assume we have:
> 1. For all $x_{i}\in \mathbb{R}^d$ and $y_{i}\in \{ \pm 1 \}$, $$\mathbb{P}(Y_{i}=y_{i}|x_{i},w)=\sigma(y_{i}w^\top x_{i})$$ independently where $w\in \mathbb{R}^d$ parameter and $\sigma:\mathbb{R}\to \mathbb{R},x\mapsto \frac{1}{1-\exp(-x)}$ is the sigmoid function. 
> 1. Gaussian prior: $p(w)=\mathcal{N}(w;0,\sigma^{2}_{p}I)$ for $\sigma_{p}\in \mathbb{R}$.
> 
> Then, we have that $q(w):=\mathcal{N}(w; \widehat{w}, \Lambda ^{-1})$ where:
> 1. $\widehat{w}:=\arg\max_{w\in \mathbb{R}^d}p(w|x_{1:n},y_{1:n})=\arg\min_{w\in \mathbb{R}^d}\sum_{i=1}^{n}\log(1+\exp(-y_{i}w^\top x_{i}))+\frac{1}{2\sigma_{p}^{2}}\|w\|^{2}_{2}$. 
> 2. $\Lambda:=\sigma_{p}^{-2}I+X^\top \text{diag}(\pi_{i}(1-\pi_{i})_{i})X$ where $\pi_{i}:=\sigma(\widehat{w}^\top x_{i})$.
> 3. To predict $p(y^{*}|x^{*},x_{1:n},y_{1:n})$ for $x^{*}\in \mathbb{R}^d$, we compute: $$p(y^{*}|x^{*},x_{1:n},y_{1:n})\approx \int_{\mathbb{R}}  \, dx $$

> [!proof]-
> We have that:
> 1. Notice that: $$\begin{align}\widehat{w}&=\arg\max_{w\in \mathbb{R}^d}p(w|x_{1:n},y_{1:n})\\&=\arg\max_{w\in \mathbb{R}^d}p(y_{1:n}|x_{1:n},w)p(w)\\&=\arg\max_{w\in \mathbb{R}^d}\log p(w)+\log p(y_{1:n}|x_{1:n},w)\\&=\arg\max_{w\in \mathbb{R}^d}\left( -\frac{\|w\|^{2}_{2}}{2\sigma^{2}_{p}}+\sum_{i=1}^{n}\log \sigma(y_{i}w^\top x_{i}) \right)\\&=\arg\max_{w\in \mathbb{R}^d}\left( -\frac{\|w\|^{2}_{2}}{2\sigma^{2}_{p}}-\sum_{i=1}^{n}\log (1-\exp(-y_{i}w^\top x_{i}))\right)\\&=\arg\min_{w\in \mathbb{R}^d}\frac{\|w\|^{2}_{2}}{2\sigma^{2}_{p}}+\sum_{i=1}^{n}\log (1-\exp(-y_{i}w^\top x_{i}))\end{align}$$
> 2. Notice that: $$\begin{align}\Lambda&=-\text{H}_{\widehat{w}}(\log p(w|x_{1:n},y_{1:n}))\\&=\text{H}_{\widehat{w}}\left( \frac{\|w\|^{2}_{2}}{2\sigma^{2}_{p}}+\sum_{i=1}^{n}\log (1-\exp(-y_{i}w^\top x_{i}))\right)\\&=\text{D}_{\widehat{w}}\nabla\left( \frac{\|w\|^{2}_{2}}{2\sigma^{2}_{p}}+\sum_{i=1}^{n}\log (1-\exp(-y_{i}w^\top x_{i}))\right)\\&=\text{D}_{\widehat{w}}\left( \frac{w}{\sigma^{2}_{p}}-\sum_{i=1}^{n} \left( 1-\frac{1}{1-\exp(-y_{i}w^\top x_{i})} \right)y_{i}x_{i} \right) \\&=\sigma^{-2}_{p}I-\sum_{i=1}^{n}y_{i}x_{i}\left( \frac{1}{(1-\exp(-y_{i}w^\top x_{i}))^{2}} \right)(-\exp(-y_{i}w^\top x_{i}))(-y_{i}x_{i}^\top)\\&=\sigma^{-2}_{p}I+\sum_{i=1}^{n}x_{i}x_{i}^\top\left(-\frac{\exp(-y_{i}w^\top x_{i})}{(1-\exp(-y_{i}w^\top x_{i}))^{2}} \right) \\&=\sigma^{-2}_{p}I+\sum_{i=1}^{n}x_{i}x_{i}^\top \pi_{i}(1-\pi_{i})\end{align}$$
- **Remark**: We can use regularized logistic regression using stochastic gradient descent to solve for $\widehat{w}$.