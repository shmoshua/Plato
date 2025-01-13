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
