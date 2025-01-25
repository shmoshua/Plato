#Definition #InformationTheory 

> [!definition]
> For discrete random variables $X,Y,Z$ in $\mathcal{X},\mathcal{Y},\mathcal{Z}$, 
> 1. the ***mutual information*** of $X,Y$ is given by: $$I(X;Y):=H(X) - H(X|Y)=H(Y)-H(Y|X)$$
> 2. the ***conditional mutual information*** of $X,Y$ given $Z$ is given as: $$I(X;Y|Z)=\mathbb{E}_{Z}[I(X;Y|Z=z)]$$where $I(X;Y|Z=z):=D(p_{XY|Z=z},p_{X|Z=z}\cdot p_{Y|Z=z})$.

^b7d647

- **Remark**: The equality holds as $H(X)+H(Y|X)=H(X,Y)=H(Y)+H(X|Y)$.
---
##### Properties
> [!lemma] Proposition 1 (Basic Properties)
> We have:
> 1. $I(X;Y)=H(X)+H(Y)-H(X,Y)$
> 1. $I(X;Y)=D(p_{XY}\|p_{X}\cdot p_{Y})$
> 2. $0\leq I(X;Y)\leq \min\{ H(X),H(Y) \}$
> 3. $I(X;Y)=0$ if and only if $X$ and $Y$ are independent.
> 4. $I(X;Y|Z)=H(X|Z)-H(X|Y,Z)$
> 5. $I(X,Y;Z)=I(X;Z)+I(Y;Z|X)=I(Y;Z)+I(X;Z|Y)$

^f92807

> [!proof]-
> We have:
> 1. From [[Entropy|Proposition 3.2]].
> 1. Observe that: $$I(X;Y)=\mathbb{E}_{X,Y}\left[ \log \frac{p_{X|Y}(X|Y)}{p_{X}(X)} \right]=\mathbb{E}_{X,Y}\left[ \log \frac{p_{XY}(X,Y)}{p_{X}(X)p_{Y}(Y)} \right]=D(p_{XY}\|p_{X}\cdot p_{Y})$$
> 2. From [[Relative Entropy|Information inequality]] we have that $I(X;Y)=D(p_{XY}\|p_{X}\cdot p_{Y})\geq 0$. The upper bound holds from the fact that entropy is non-negative.
> 3. Holds from [[Entropy|Proposition 3.4]].
> 4. We have: $$\begin{align}I(X,Y;Z)&=\int_{\mathcal{Z}} \int_{X\times Y} p_{XY|Z=z}(x,y)  \, \log \frac{p_{XY|Z=z}(x,y)}{p_{X|Z=z}(x)p_{Y|Z=z}(y)}d(x,y)  \, dz\\&=\int_{\mathcal{Z}} \int_{X\times Y} p_{XY|Z=z}(x,y)  \, \log \frac{p_{X|Y,Z=z}(x|y)}{p_{X|Z=z}(x)}d(x,y)  \, dz\\&=H(X|Z)-H(X|Y,Z)\end{align} $$
> 5. We have: $$\begin{align}H(X,Y)-H(X,Y|Z)&=H(X)+H(Y|X)-H(X|Z)-H(Y|X,Z)\\&=I(X;Z)+I(Y;Z|X)\end{align}$$The other one holds by symmetry.

^7e7455

- **Corollary**: $H(X|Y)\leq H(X)$ for all $X,Y$. 
---
> [!lemma] Proposition 2 (Conditional Mutual Information)
> Let $X{\bot}Z|Y$. Then, 
> 1. $I(X;Z)\leq I(X;Y)$

^eb14f8

> [!proof]-
> We have that: $$I(X;Z)=H(X)-H(X|Z)\le H(X)-H(X|Y,Z)=H(X)-H(X|Y)=I(X;Y)$$

^986f22

---
> [!lemma] Proposition 3 (Csiszár's Identity)
> For any pair of random vectors $(A_{1},\dots,A_{n}),(B_{1},...,B_{n})$, $$\sum_{i=1}^{n}(I(A_{i+1:n};B_{i}|B_{1:i-1})-I(B_{1:i-1};A_{i}|A_{i+1:n}))=0$$

^3fabf6

> [!proof]-
> $$\begin{align}&\sum_{i=1}^{n}(I(A_{i+1:n};B_{i}|B_{1:i-1})-I(B_{1:i-1};A_{i}|A_{i+1:n}))\\=&\sum_{i=1}^{n}H(B_{i}|B_{1:i-1})-H(B_{i}|B_{1:i-1},A_{i+1:n})-H(A_{i}|A_{i+1:n})+H(A_{i}|A_{i+1:n},B_{1:i-1})\\=&\sum_{i=1}^{n}H(B_{1:i})-H(B_{1:i}|A_{i+1:n})-H(A_{i:n})+H(A_{i:n}|B_{1:i-1})\\=&\sum_{i=1}^{n}I(A_{i+1:n};B_{1:i})-\sum_{i=1}^{n}I(A_{i:n};B_{1:i-1})\\=&I(A_{n+1:n};B_{1:i})-I(A_{i:n};B^0)\\=&0\end{align}$$as $A_{n+1:n}$ and $B^0$ are deterministic.

^8b584b

---
