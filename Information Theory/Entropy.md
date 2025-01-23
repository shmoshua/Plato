#Definition #InformationTheory 

> [!definition]
> Let $X,Y$ be [[Random Variable|random variables]] over $\mathcal{X}$ and $\mathcal{Y}$. Then, 
> 1. the **entropy** of $X$ is given as: $$H(X):=\mathbb{E}_{X}\left[\mathbb{1}_{\text{supp }p_{X}}\cdot  \log \frac{1}{p_{X}(X)}\right] $$
> 2. the ***joint entropy*** of $X,Y$ is given as: $$H(X,Y)=-\sum_{x,y}^{}p_{XY}(x,y)\log  p_{XY}(x,y)=-\mathbb{E}(\log(p_{XY}(X,Y)))$$
> 3. the ***conditional entropy*** of $X$ given $Y$ is given as:$$H(X|Y)=\sum_{y}^{}p_{Y}(y)H(X|Y=y)=-\sum_{x,y}^{}p_{XY}(x,y)\log p(x|y)=-\mathbb{E}(\log p(X | Y))$$

^2cc2de

- **Related definition**: the ***self-information*** of $X$ is given by $i_{X}:\text{supp }p_{X}\to \mathbb{R},a\mapsto \log \frac{1}{p_{X}(a)}$. ^09ddcf
- **Remark**: The joint entropy is symmetric.
---
##### Properties
> [!lemma] Lemma 1 (Properties of Entropy)
> Let $X$ be a discrete RV.
> 1. $0\leq H(X) \leq \log \left| \mathcal{X} \right|$
> 2.  $0=H(X)$ if and only if $X$ is deterministic.
> 3. $H(X)=\log \left| \mathcal{X} \right|$ if and only if $X\sim \text{Uni}(\mathcal{X})$.
> 4. $H(X)=\mathbb{E}_{X}[i_{X}(X)]$.

^bf1bbb

> [!proof]-
> We have that:
> 1. $p_{X}(\mathcal{X})\subseteq[0,1]$ and $\log \frac{1}{p_{X}(x)}\subseteq[0,\infty)$ for all $x\in \mathcal{X}$.  Further, the second inequality trivially holds.
> 2. If $H(X)=0$, then by [[Expected Value|Theorem 3.1]] $\log \frac{1}{p_{X}(x)}=0$ almost surely and $p_{X}(x)=1$ almost surely in $\text{supp }p_{X}$. Hence, $\{ x \}=\text{supp }p_{X}$. Conversely, if it's deterministic the statement holds.
> 3. Analogous.
> 4. Obvious.

^049dcb

---
> [!lemma] Lemma 2 (Properties of Conditional Entropy)
> We have:
> 1. $0\leq H(X|Y)\leq \log \left| \mathcal{X} \right|$
> 2. $H(X,Y)=H(X)+H(Y|X)$
> 3. $H(X,Y|Z)=H(X|Z)+H(Y|X,Z)$
> 4. $H(X|Y)\leq H(X)$ with equality if and only if $X \ {\bot} \ Y$. 

^f62e41

> [!proof]-
> We have:
> 1. $0\leq H(X|Y=y)\leq \log \left| \mathcal{X} \right|$ for all $y$.
> 2. We have: $$H(X,Y)=-\mathbb{E}(\log p_{XY}(X,Y))=-\mathbb{E}(\log p_{X}(X))-\mathbb{E}(\log p(X|Y))=H(X)+H(Y|X)$$
> 3. Analogous to 2. 
> 4. From [[Mutual Information|Lemma 1]].

^8e99d6

---

> [!lemma] Theorem (Fano's Inequality)
> Let $X,Y$ be random variables over $\mathcal{X}$ and $\mathcal{Y}$. Let $\Phi:\mathcal{Y}\to \mathcal{X}$ be a [[Maximum A Posteriori Estimation|maximum a posteriori]] guessing function. Then, $$H(X|Y)\leq H_{b}(P_{e})+P_{e}\log(\left| \mathcal{X} \right| -1)$$where $P_{e}:=\mathbb{P}(\Phi(Y)\neq X)$.

> [!proof]-
> Given $\Phi:\mathcal{Y}\to \mathcal{X}$, we have that:
> $$H(X,\mathbb{1}_{\{ \Phi(Y)\neq X \}}|Y)=H(X|Y)+\underbrace{ H(\mathbb{1}_{\{ \Phi(Y)\neq X \}}|X,Y) }_{ =0 }$$ Therefore, $$\begin{align}H(X|Y)&=H(\mathbb{1}_{\{ \Phi(Y)\neq X \}}|Y)+H(X|Y,\mathbb{1}_{\{ \Phi(Y)\neq X \}})\\&\leq H(\mathbb{1}_{\{ \Phi(Y)\neq X \}})+\mathbb{P}(\Phi(Y)= X)\underbrace{ H(X|Y,\Phi(Y)=X) }_{ =0 }+\mathbb{P}(\Phi(Y)\neq X)H(X|Y,\Phi(Y)\neq X)\\&\le H_{b}(P_{e})+P_{e}\log(\left| \mathcal{X} \right| -1)\end{align}$$
---
##### Examples
> [!h] Example 1 (Bernoulli distribution)
> Let $X\sim \text{Ber}(p)$ the [[Distribution|Bernoulli distribution]]. Then, 
> 1. $H(X)=p\log \frac{1}{p}+(1-p)\log \frac{1}{1-p}=:H_{b}(p)$