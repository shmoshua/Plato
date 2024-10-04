#Definition #ProbabilityTheory 

> [!definition]
> Let $X\in L^2(\Omega,\mathcal{A},\mathbb{P})$ be a [[random variable]]. The ***variance*** of $X$ is defined as: $$\text{Var}(X):=\mathbb{E}[(X-\mathbb{E}[X])^{2}]\geq 0$$
- **Related definition**: The ***standard deviation*** of $X$ is $\sigma_{X}:=\sqrt{ \text{Var}(X) }$.
---
> [!lemma] Proposition 1
> For $X\in L^2(\Omega,\mathcal{A},\mathbb{P})$, 
> 1. $\text{Var}(X)=0$ if and only if $X=\mathbb{E}[X]$ almost surely.
> 2. $\text{Var}(X)=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}$
> 3. for every $a\in \mathbb{R}$, $\mathbb{E}[(X-a)^{2}]=\text{Var}(X)+(\mathbb{E}[X]-a)^{2}$
> 5. $\text{Var}(X)=\inf_{a\in \mathbb{R}}\mathbb{E}[(X-a)^{2}]$

> [!proof]-
> We have:
> 1. if $\text{Var}(X)=0$, then $\mathbb{E}[(X-\mathbb{E[X]})^{2}]=0$. Then, by [[Expected Value|Theorem 3]], $X-\mathbb{E}[X]=0$ almost surely. 
>    
>    Conversely, if $X=\mathbb{E}[X]$ almost surely, then $(X-\mathbb{E}[X])^{2}=0$ almost surely. Therefore, its expectation is $0$. 
> 2. We have that:$$\mathbb{E}[(X-a)^{2}]=\mathbb{E}[X^{2}]-2a\mathbb{E}[X]+a^{2}=\mathbb{E}[X^{2}]-\mathbb{E}[X]^{2}+(\mathbb{E}[X]-a)^2$$Take $a=\mathbb{E}[X]$.
> 3. Holds from 2. 
> 4. Holds from 3.
---
> [!lemma] Proposition 2 
> For $X,Y$ two random variables,
> 1. $\text{Var}(X+Y)=\text{Var}(X)+\text{Var}(Y)+2\text{Cov}(X,Y)$
> 2. $\text{Var}(\alpha X)=\alpha^{2} \text{Var}(X)$

> [!proof]-
> We have: 
> 1. $$\begin{align}\text{Var}(X+Y)&=\mathbb{E}[X^{2}+2XY+Y^{2}]-\mathbb{E}[X]^{2}-2\mathbb{E}[X]\mathbb{E}[Y]-\mathbb{E}[Y]^{2}\\&=\text{Var}(X)+\text{Var}(Y)+2(\mathbb{E}[XY]-\mathbb{E}[X]\mathbb{E}[Y])\\&=\text{Var}(X)+\text{Var}(Y)+2\text{Cov}(X,Y)\end{align}$$
> 2. $$\text{Var}(\alpha X)=\alpha^{2}\mathbb{E}[ X^{2}]-\alpha^{2}\mathbb{E}[X]^{2}=\alpha^{2} \text{Var}(X)$$
---
