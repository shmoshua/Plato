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
> 3. $I(X,Y;Z)=I(X;Z)+I(Y;Z|X)=I(Y;Z)+I(X;Z|Y)$

> [!proof]-
> We have:
> 1. Observe that: $$I(X;Y)=\sum_{x,y}^{}p(x,y)\log \frac{p(x|y)}{p(x)}=\sum_{x,y}^{}p(x,y)\log \frac{p(x,y)}{p(x)p(y)}=D(p_{XY}\|p_{X}\cdot p_{Y})$$
> 2. From [[]] we have that $I(X;Y)=D(p_{XY}\|p_{X}\cdot p_{Y})\geq 0$. The upper bound holds from the fact that entropy is non-negative.
> 3. Holds from [[]].
> 4. We have: $$\begin{align}H(X,Y)-H(X,Y|Z)&=H(X)+H(Y|X)-H(X|Z)-H(Y|X,Z)\\&=I(X;Z)+I(Y;Z|X)\end{align}$$The other one holds by symmetry.
- **Corollary**: $H(X|Y)\leq H(X)$ for all $X,Y$. 
---
> [!lemma] Proposition 2 (Conditional Mutual Information)
> Let $X{\bot}Z|Y$. Then, 
> 1. $I(X;Z)\leq I(X;Y)$

> [!proof]-
> We have that: $$I(X;Z)=H(X)-H(X|Z)\le H(X)-H(X|Y,Z)=H(X)-H(X|Y)=I(X;Y)$$
---
> [!lemma] Proposition 3 (Csiszár's Identity)
> For any pair of random vectors $(A_{1},\dots,A_{n}),(B_{1},...,B_{n})$, $$\sum_{i=1}^{n}(I(A_{i+1:n};B_{i}|B_{1:i-1})-I(B_{1:i-1};A_{i}|A_{i+1:n}))=0$$

^3fabf6

> [!proof]-
> $$\begin{align}&\sum_{i=1}^{n}(I(A_{i+1:n};B_{i}|B_{1:i-1})-I(B_{1:i-1};A_{i}|A_{i+1:n}))\\=&\sum_{i=1}^{n}H(B_{i}|B_{1:i-1})-H(B_{i}|B_{1:i-1},A_{i+1:n})-H(A_{i}|A_{i+1:n})+H(A_{i}|A_{i+1:n},B_{1:i-1})\\=&\sum_{i=1}^{n}H(B_{1:i})-H(B_{1:i}|A_{i+1:n})-H(A_{i:n})+H(A_{i:n}|B_{1:i-1})\\=&\sum_{i=1}^{n}I(A_{i+1:n};B_{1:i})-\sum_{i=1}^{n}I(A_{i:n};B_{1:i-1})\\=&I(A_{n+1:n};B_{1:i})-I(A_{i:n};B^0)\\=&0\end{align}$$as $A_{n+1:n}$ and $B^0$ are deterministic.

^8b584b

---
