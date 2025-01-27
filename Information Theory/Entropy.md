#Definition #InformationTheory 

> [!definition]
> Let $X,Y$ be [[Random Variable|random variables]] over $\mathcal{X}$ and $\mathcal{Y}$. Then, 
> 1. the **entropy** of $X$ is given as: $$H(X):=\mathbb{E}_{X}\left[ \log \frac{1}{p_{X}(X)}\right] $$
> 2. the ***joint entropy*** of $X,Y$ is given as: $$H(X,Y):=\mathbb{E}_{X,Y}\left[ \log \frac{1}{p_{XY}(X,Y)} \right] $$
> 3. the ***conditional entropy*** of $X$ given $Y$ is given as:$$H(X|Y):=\mathbb{E}_{y\sim p_{Y}}[H(X|Y=y)]=\mathbb{E}_{X,Y}\left[ \log \frac{1}{p_{X|Y}(X|Y)} \right]$$

^2cc2de

- **Related definition**: the ***self-information*** of $X$ is given by $i_{X}:\text{supp }p_{X}\to \mathbb{R},a\mapsto \log \frac{1}{p_{X}(a)}$. ^09ddcf
- **Remark**: The joint entropy is symmetric.
- **Remark**: All the expected values are meant to be taken over the support. 
---
##### Properties
> [!lemma] Proposition 1 (Properties of Entropy)
> Let $X$ be a discrete RV.
> 1. $0\leq H(X) \leq \log \left| \mathcal{X} \right|$
> 2.  $0=H(X)$ if and only if $X$ is deterministic.
> 3. $H(X)=\log \left| \mathcal{X} \right|$ if and only if $X\sim \text{Uni}(\mathcal{X})$.
> 4. $H(X)=\mathbb{E}_{X}[i_{X}(X)]$.

^bf1bbb

> [!proof]-
> We have that:
> 1. $p_{X}(\mathcal{X})\subseteq[0,1]$ and $\log \frac{1}{p_{X}(x)}\subseteq[0,\infty)$ for all $x\in \mathcal{X}$.  Further, the second inequality is given by [[Relative Entropy|Proposition 1]] and [[Relative Entropy|Example 1]] as: $$\log \left| \mathcal{X} \right| -H(p)=D(p\|q)\geq 0$$
> 2. If $H(X)=0$, then by [[Expected Value|Theorem 3.1]] $\log \frac{1}{p_{X}(x)}=0$ almost surely and $p_{X}(x)=1$ almost surely in $\text{supp }p_{X}$. Hence, $\{ x \}=\text{supp }p_{X}$. Conversely, if it's deterministic the statement holds.
> 3. Analogous.
> 4. Obvious.

^049dcb

---
> [!lemma] Proposition 2 (Properties of Joint Entropy)
> Let $X,Y$ be random variables over $\mathcal{X}$ and $\mathcal{Y}$. Then, 
> 1. $H(X,Y)=H(X)+H(Y)$, if $X$ and $Y$ are independent.
> 2. $H(X,X)=H(X)$.

^4eec02

> [!proof]-
> We have that: 
> 1. $$H(X,Y)=\mathbb{E}\left[ \log \frac{1}{p_{XY}(X,Y)} \right]=\mathbb{E}\left[ \log \frac{1}{p_{X}(X)p_{Y}(Y)} \right]=H(X)+H(Y)$$
> 2. $$H(X,X)=\sum_{x\in \mathcal{X}}^{}\sum_{x'\in \mathcal{X'}}^{}p_{XX}(x,x')\log \frac{1}{p_{XX}(x,x')}=\sum_{x\in \mathcal{X}}^{}p_{X}(x)\log \frac{1}{p_{X}(x)}=H(X)$$

^6a94ef

---
> [!lemma] Proposition 3 (Properties of Conditional Entropy)
> We have:
> 1. $0\leq H(X|Y)\leq \log \left| \mathcal{X} \right|$
> 2. $H(X,Y)=H(X)+H(Y|X)$
> 3. $H(X,Y|Z)=H(X|Z)+H(Y|X,Z)$
> 4. $H(X|Y)\leq H(X)$ with equality if and only if $X \ {\bot} \ Y$. 
> 5. $H(Y|X)=0$ if and only if there exists $g:\mathcal{X}\to \mathcal{Y}$ s.t. $\mathbb{P}(Y=g(X))=1$. 

^f62e41

> [!proof]+
> We have:
> 1. $0\leq H(X|Y=y)\leq \log \left| \mathcal{X} \right|$ for all $y$.
> 2. We have: $$H(X,Y)=-\mathbb{E}(\log p_{XY}(X,Y))=-\mathbb{E}(\log p_{X}(X))-\mathbb{E}(\log p(X|Y))=H(X)+H(Y|X)$$
> 3. Analogous to 2. 
> 4. From [[Mutual Information|Lemma 1.3]].
> 5. Assume $H(Y|X)=0$. Then, $$\sum_{x\in \mathcal{X}}^{}p_{X}(x)H(Y|X)$$

^8e99d6

---
> [!lemma] Proposition 4 (Concavity of Entropy)
> We have that: 
> 1. $H:\Delta(\mathcal{X})\to \mathbb{R}, p\mapsto H(p)$ is [[Convex Function|concave]].

^8e1dbc

> [!proof]-
> Let $p,q\in \Delta(\mathcal{X})$. Let $Y\sim \text{Ber}(\lambda)$ and we define $X$ s.t. $X|Y=1\sim p$ and $X|Y=0\sim q$. Then, $$H(X|Y)=\lambda H(X|Y=1)+(1-\lambda)H(X|Y=0)=\lambda H(p)+(1-\lambda)H(q)$$Therefore, $p_{X}(x)=\lambda p(x)+(1-\lambda)q(x)$ and $$H(\lambda p+(1-\lambda)q)=H(X)\geq H(X|Y)= \lambda H(p)+(1-\lambda)H(q)$$from Proposition 3.4.

^38bd1d

---
> [!lemma] Theorem (Fano's Inequality)
> Let $X,Y$ be jointly distributed over $\mathcal{X}\times \mathcal{Y}$ and let $\phi:\mathcal{Y}\to \mathcal{X}$ be a function. Then, $$H(X|Y)\leq H_{b}(\eta)+\eta \cdot \log(\left| \mathcal{X} \right| -1)$$where $\eta:=\mathbb{P}(\phi(Y)\neq X)$ and $H_{b}(\eta)=H(\text{Ber}(\eta))$.

^730b6a

> [!proof]-
> Given $\phi:\mathcal{Y}\to \mathcal{X}$, we have that:
> $$H(X,\mathbb{1}_{\{ \phi(Y)\neq X \}}|Y)=H(X|Y)+\underbrace{ H(\mathbb{1}_{\{ \phi(Y)\neq X \}}|X,Y) }_{ =0 }$$as $\mathbb{1}_{\phi(Y)\neq X}|X,Y$ is determinstic. Therefore, $$\begin{align}H(X|Y)&=H(X,\mathbb{1}_{\{ \phi(Y)\neq X \}}|Y)\\&=H(\mathbb{1}_{\{ \phi(Y)\neq X \}}|Y)+H(X|Y,\mathbb{1}_{\{ \phi(Y)\neq X \}})\\&\leq H_{b}(\eta)+\mathbb{P}(\phi(Y)= X)\underbrace{ H(X|Y,\phi(Y)=X) }_{ =0 }+\mathbb{P}(\phi(Y)\neq X)H(X|Y,\phi(Y)\neq X)\\&\le H_{b}(\eta)+\eta\log(\left| \mathcal{X} \right| -1)\end{align}$$

^9dcdf7

---
##### Examples
> [!h] Example 1 (Bernoulli distribution)
> Let $X\sim \text{Ber}(p)$ the [[Distribution|Bernoulli distribution]]. Then, 
> 1. $H(X)=p\log \frac{1}{p}+(1-p)\log \frac{1}{1-p}=:H_{b}(p)$

^1d6ace

---
> [!h] Example 2
> Let $p_{XY}(x,y)$ be given by: $$P:=\begin{bmatrix}1 / 3&1 /3 \\0 &1 / 3\end{bmatrix}$$Then,
> 1. $H(X)=H_{b}(1 /3)$.
> 2. $H(Y)=H_{b}(1 / 3)$.
> 3. $H(X|Y)=2 /3$.
> 4. $H(Y|X)=2 / 3$.
> 5. $H(X,Y)=H_{b}(1 /3 )+2 / 3$.
> 6. $I(X;Y)=H(Y)-H(Y|X)= H_{b}(1 /3 )- 2 /3$