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

^0bf01f

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
> [!lemma] Proposition 3
> Let $X$ be a positive random variable.
> 1. $\mathbb{P}(X=0)\leq \text{Var(X)} / \mathbb{E}[X]^{2}$
> 1. if $\text{Var}(X)=\text{o}(\mathbb{E}[X]^{2})$ then $X>0$ almost surely.
> 2. if $\text{Var}(X)=\text{o}(\mathbb{E}[X]^{2})$ then $X\sim \mathbb{E}[X]$ almost surely.

^a34f60


> [!proof]-
> We have:
> 1. By [[Expected Value|Chebyshev]]: $$\mathbb{P}(X=0)\leq \mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq \mathbb{E}[X])\leq \frac{\text{Var}(X)}{\mathbb{E}[X]^{2}}$$
> 1. $\mathbb{P}(X=0)\leq \text{o}(1)$.
> 2. For any $\varepsilon>0$, $\mathbb{P}\left( \left| \frac{X}{\mathbb{E}[X]}-1 \right|\geq \varepsilon \right)\leq \frac{1}{\varepsilon^{2}}\text{o}(1)=\text{o}(1)$
> 3. By [[Expected Value|Chebyshev]] for any $\varepsilon>0$: $$\mathbb{P}(X=0)\leq \mathbb{P}(X\leq \varepsilon \mathbb{E}[X])\leq\mathbb{P}(\left| X-\mathbb{E}[X] \right| \geq  \varepsilon \mathbb{E}[X])\leq \frac{\text{Var}(X)}{\varepsilon^{2} \mathbb{E}[X]^{2}} = \text{o}(1)$$

^d93e5b

---
> [!lemma] Theorem 4
> Let $A_{1},\dots,A_{m}\in \mathcal{A}$. Then, we define $i\sim j$ if and only if $A_{i},A_{j}$ are not independent. Further, let $X:=\mathbb{1}_{A_{1}}+\dots+\mathbb{1}_{A_{m}}$ and define: $$\Delta:=\sum_{i\sim j}^{}\mathbb{P}(A_{i}\land A_{j}),\quad \Delta ^{*}:=\max_{i} \sum_{j: j \sim i}^{}\mathbb{P}(A_{j}|A_{i})$$
> 1. $\text{Var}(X)\leq \mathbb{E}[X]+\Delta$
> 2. if $\mathbb{E}[X]\to \infty$ and $\Delta=\text{o}(\mathbb{E}[X]^{2})$, then $X>0$ and $X\sim \mathbb{E}[X]$ a.s.
> 3. if $\mathbb{E}[X]\to \infty$ and $\Delta ^{*}=\text{o}(\mathbb{E}[X])$, then $X>0$ and $X\sim \mathbb{E}[X]$ a.s.

> [!proof]-
> Let $X_{i}:=\mathbb{1}_{A_{i}}$. Then:
> 1. If $i\sim j$, then: $$\text{Cov}(X_{i},X_{j})=\mathbb{E}[X_{i}X_{j}]-\mathbb{E}[X_{i}]\mathbb{E}[X_{j}]\leq \mathbb{E}[X_{i}X_{j}]=\mathbb{P}(A_{i}\land A_{j})$$Therefore,$$\text{Var}(X)\leq\sum_{i=1}^{m}\mathbb{E}[\mathbb{1}_{A_{i}}]+\sum_{i \sim j}^{}\mathbb{P}(A_{i}\land A_{j})=\mathbb{E}[X]+\Delta$$
> 2. We have that: $$0\leq \lim_{ n \to \infty } \frac{\text{Var}(X)}{\mathbb{E}[X]^{2}}\leq \lim_{ n \to \infty } \frac{1}{\mathbb{E}[X]}+\frac{\Delta}{\mathbb{E}[X]^{2}}=0$$The rest follows from Proposition 3.2 and 3.3
> 3. We have that: $$\Delta=\sum_{i}^{}\sum_{j:j \sim i}^{}\mathbb{P}(A_{i}\land A_{j})=\sum_{i}^{}\mathbb{P}(A_{i})\sum_{j:j \sim i}^{}\mathbb{P}(A_{j}|A_{i})\leq \Delta ^{*}\sum_{i}^{}\mathbb{P}(A_{i})=\mathbb{E}[X]\cdot \Delta ^{*}$$The rest follows from 2.
---
