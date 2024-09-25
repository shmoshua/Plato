#Definition #InformationTheory 

> [!definition]
> Let $X,Y$ be discrete random variables over $\mathcal{X}$ and $\mathcal{Y}$. Then, 
> 1. the **entropy** of $X$ is given as: $$H(X):=-\sum_{x}^{}p_{X}(x)\log p_{X}(x)=-\mathbb{E}(\log(p_{X}(X)))$$
> 2. the ***joint entropy*** of $X,Y$ is given as: $$H(X,Y)=-\sum_{x,y}^{}p_{XY}(x,y)\log  p_{XY}(x,y)=-\mathbb{E}(\log(p_{XY}(X,Y)))$$
> 3. the ***conditional entropy*** of $X$ given $Y$ is given as:$$H(X|Y)=\sum_{y}^{}p_{Y}(y)H(X|Y=y)=-\sum_{x,y}^{}p_{XY}(x,y)\log p(x|y)=-\mathbb{E}(\log p(X | Y))$$
- **Remark**: The joint entropy is symmetric.
---
##### Properties
> [!lemma] Lemma 1 (Properties of Entropy)
> We have:
> 1. $0\leq H(X|Y)\leq \log \left| \mathcal{X} \right|$
> 2. $H(X,Y)=H(X)+H(Y|X)$
> 3. $H(X,Y|Z)=H(X|Z)+H(Y|X,Z)$
> 4. $H(X|Y)\leq H(X)$ with equality if and only if $X \ {\bot} \ Y$. 

> [!proof]+
> We have:
> 1. $0\leq H(X|Y=y)\leq \log \left| \mathcal{X} \right|$ for all $y$.
> 2. We have: $$H(X,Y)=-\mathbb{E}(\log p_{XY}(X,Y))=-\mathbb{E}(\log p_{X}(X))-\mathbb{E}(\log p(X|Y))=H(X)+H(Y|X)$$
> 3. Analogous to 2. 