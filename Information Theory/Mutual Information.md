#Definition #InformationTheory 

> [!definition]
> For two discrete random variables $X,Y$ in $\mathcal{X},\mathcal{Y}$, 
> 1. the ***mutual information*** of $X,Y$ is given by: $$I(X;Y):=H(X) - H(X|Y)=H(Y)-H(Y|X)$$
- **Remark**: The equality holds as $H(X)+H(Y|X)=H(X,Y)=H(Y)+H(X|Y)$.
---
##### Properties
> [!lemma] Lemma 1 (Basic Properties)
> We have:
> 1. $I(X;Y)=D(p_{XY}\|p_{X}\cdot p_{Y})$
> 2. $0\leq I(X;Y)\leq \min\{ H(X),H(Y) \}$
> 2. $I(X;Y)=0$ if and only if $X$ and $Y$ are independent.

> [!proof]-
> We have:
> 1. Observe that: $$I(X;Y)=\sum_{x,y}^{}p(x,y)\log \frac{p(x|y)}{p(x)}=\sum_{x,y}^{}p(x,y)\log \frac{p(x,y)}{p(x)p(y)}=D(p_{XY}\|p_{X}\cdot p_{Y})$$
> 2. From [[]] we have that $I(X;Y)=D(p_{XY}\|p_{X}\cdot p_{Y})\geq 0$. The upper bound holds from the fact that entropy is non-negative.
> 3. Holds from [[]].
- **Corollary**: $H(X|Y)\leq H(X)$ for all $X,Y$. 
---

