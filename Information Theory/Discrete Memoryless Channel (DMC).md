#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X}$ and $\mathcal{Y}$ be finite sets. 
> 1. A ***discrete memoryless channel (DMC)*** from $\mathcal{X}$ to $\mathcal{Y}$ is a $\mathcal{X}\times \mathcal{Y}$ [[Markov Chain|transition matrix]] $W$ where for every $x\in \mathcal{X}$, $\sum_{y\in \mathcal{Y}}^{}W_{xy}=1$

^caee85

- **Related definition**: For a DMC $W$ from $\mathcal{X}$ to $\mathcal{Y}$ and $q\in \Delta(\mathcal{X})$, $I(q,W):=I(X;Y)$ where $X\sim q$ and $Y \sim qW$.
   ^1491bf
- **Related definition**: A rate $R$ is ***achievable*** on a DMC $W$ if there exists $(f_{n},\phi_{n})_{n\geq 1}$ where $f:\mathcal{M}_{n}\to \mathcal{X}^n$ and $\phi:\mathcal{Y}^n\to \mathcal{M}_{n}$ with $\mathcal{M}_{n}:=\{ 1,\dots,2^{nR} \}$ s.t. $$\lim_{ n \to \infty } \max_{m\in \mathcal{M}_{n}}\sum_{\begin{subarray}{c}y\in \mathcal{Y}^n\\ \phi_{n}(y)\neq m\end{subarray}}\mathbb{P}(f_{n}(m)W=y)=0$$  ^a6191c
- **Related definition**: The ***capacity*** of a DMC $W$ is $C(W):=\sup\{ R:R\text{ is achievable} \}$. ^513ead
---
##### Properties
> [!lemma] Theorem 1 (Data Processing Inequality for Relative Entropy)
> Let $p,q\in \Delta(\mathcal{X})$ and $W$ a DMC. Then,
> $$D(p\|q)\geq D(pW\|qW)$$

^bc8814

> [!proof]-
> We have by [[Technical Lemmas|log-sum inequality]],  $$\begin{align}D(pW\|qW)&=\sum_{y\in \mathcal{Y}}^{}(pW)_{y}\log \frac{(pW)_{y}}{(qW)_{y}}\\&=\sum_{y\in \mathcal{Y}}^{}\left( \sum_{x\in \mathcal{X}}^{}p_{x}W_{x,y} \right) \log \frac{\sum_{x}^{}p_{x}W_{x,y}}{\sum_{x}q_{x}W_{x,y}}\\&\leq\sum_{y\in \mathcal{Y}}^{}\sum_{x\in \mathcal{X}}^{}p_{x}W_{x,y}  \log \frac{p_{x}W_{x,y}}{q_{x}W_{x,y}}\\&=\sum_{x\in \mathcal{X}}^{}\sum_{y\in \mathcal{Y}}^{}p_{x}W_{x,y}  \log \frac{p_{x}}{q_{x}}\\&=\sum_{x\in \mathcal{X}}^{}p_{x}  \log \frac{p_{x}}{q_{x}}\\&=D(p\|q)\end{align}$$

^67dcbf

---
> [!lemma] Theorem 2 (Concavity and Convexity)
> We have that:
> 1. for any DMC $W$, $I(\cdot,W)$ is a concave function.
> 2. for any $q\in \Delta(\mathcal{X})$, $I(q,\cdot)$ is a convex function.

^0b1214

> [!proof]-
> We have that:
> 1. Notice that: $$\begin{align}I(\underbrace{ \lambda q_{1}+(1-\lambda)q_{2} }_{ =: q },W)&=D(q \times W,q\cdot q W)\\&=\sum_{x,y}q(x)W(y|x)\log \frac{W(y|x)}{\sum_{x'}^{}q(x')W(y|x')}\\&=\sum_{x,y}q(x)W(y|x)\log \frac{W(y|x)}{\lambda\sum_{x'}^{}q_{1}(x')W(y|x')+(1-\lambda)\sum_{x'}^{}q_{2}(x')W(y|x')}\\&\geq \sum_{x,y}^{}\left( \lambda q_{1}(x)W(y|x)\log \frac{W(y|x)}{\sum_{x'}q_{1}(x')W(y|x')}+(1-\lambda)q_{2}(x)W(y|x)\log \frac{W(y|x)}{\sum_{x'}q_{2}(x')W(y|x')}\right)\\&=\lambda D(q_{1}\times W,q_{1}\cdot q_{1}W)+(1-\lambda) D(q_{2}\times W,q_{2}\cdot q_{2}W)\\&=\lambda I(q_{1},W)+(1-\lambda)I(q_{2},W)\end{align}$$where we used the [[Technical Lemmas|log sum inequality]].
> 2. We have that: $$\begin{align}I(q,\lambda W_{1}+(1-\lambda)W_{2})&=D(q\times(\lambda W_{1}+(1-\lambda)W_{2})\| q\cdot q(\lambda W_{1}+(1-\lambda)W_{2}))\\&=D(\lambda q\times W_{1}+(1-\lambda)q\times W_{2}\|\lambda q\cdot qW_{1}+(1-\lambda)q\cdot qW_{2})\\&\leq \lambda D(q\times W_{1}\|q\cdot qW_{1})+(1-\lambda)D(q\times W_{2}\|q\cdot qW_{2})\\&=\lambda I(q,W_{1})+(1-\lambda)I(q,W_{2})\end{align}$$where the inequality comes from the [[Mutual Information|convexity of mutual information]].

^2662b0

---
> [!lemma] Theorem 3 (Karush-Kuhn-Tucker, KKT)
> Let $W$ be a DMC. 
> 1. if $q^{*}=\arg\max_{q\in \Delta(\mathcal{X})} I(q,W)$ with $C:=I(q^{*},W)$ then: $$D(W(\cdot |x)\|q^{*}W)\leq C,\quad \forall x\in \mathcal{X}$$with equality for all $x\in \mathcal{X}$ s.t. $q^{*}(x)>0$.
> 2. for $q\in \Delta(\mathcal{X})$ and $\gamma\in \mathbb{R}$, if: $$D(W(\cdot |x)\|q W)\leq \gamma,\quad \forall x\in \mathcal{X}$$with equality for all $x\in\mathcal{X}$ s.t. $q(x)>0$, then $I(q,W)=\gamma$.

^79c0ff

> [!proof]+


---

> [!lemma] Theorem 4 (Shannon)
> For a DMC $W$ from $\mathcal{X}$ to $\mathcal{Y}$, we have that:
> 1. $C(W)=\max_{q\in \Delta(\mathcal{X})}I(q,W)$.
> 2. $C(W)=\min_{r\in \Delta(\mathcal{Y})}\max_{x\in \mathcal{X}}D(W(\cdot|x)\| r)$.

^45755d

> [!proof]+
> We have that:
> 1. Let $R$ be achievable, i.e. we have $(f_{n},\phi_{n})_{n}$ with $$\lim_{ n \to \infty } \max_{m\in \mathcal{M}_{n}}\underbrace{ \sum_{\begin{subarray}{c}y\in \mathcal{Y}^n\\ \phi_{n}(y)\neq m\end{subarray}}\mathbb{P}(f_{n}(m)W=y) }_{ =:\lambda_{m} }=0$$We will show that $R\leq \max_{q\in \Delta(\mathcal{X})}I(q,W)$. First, let $$P^n_{e}:=\frac{1}{2^{nR}}\sum_{m\in \mathcal{M}_{n}}^{}\lambda_{m}$$Then, as $P^n_{e}=\frac{1}{2^{nR}}\sum_{m}^{}\lambda_{m}\leq \max_{m}\lambda_{m}$ and $\lim_{ n \to \infty }P^n_{e}=0$.  
>    
>    Now, let $M\sim \text{Uni}(\mathcal{M})$. Let $(X_{1},\dots,X_{n}):=f_{n}(M)$ and $(Y_{1},\dots,Y_{n})$ the output of the channel. Then, notice that by [[Entropy|Fano]], $$\begin{align}nR &=H(M)\\&=I(M;Y_{1:n})+H(M|Y_{1:n})\\&\leq I(M;Y_{1:n})+1+P^n_{e}\cdot nR\end{align}$$and $R\leq \frac{1}{n}I(M;Y_{1:n})+\frac{1}{n}+P^n_{e}\cdot R$. We claim that $I(M;Y_{1:n})\leq n\cdot\max_{q\in \Delta(\mathcal{X})}I(q,W)$. We have that: $$\begin{align}I(M;Y_{1:n})&=H(Y_{1:n})-H(Y_{1:n}|M)\\&=\sum_{i=1}^{n}H(Y_{i}|Y_{1:i-1})-H(Y_{i}|Y_{1:i-1},M)\\&\leq \sum_{i=1}^{n}H(Y_{i})-H(Y_{i}|Y_{1:i-1},X_{i},M)\\&=\sum_{i=1}^{n}H(Y_{i})-H(Y_{i}|X_{i})\\&=\sum_{i=1}^{n}I(X_{i};Y_{i})=\sum_{i=1}^{n}I(p_{X_{i}},W)\leq n\max_{q\in \Delta(\mathcal{X})}I(q,W)\end{align}$$Therefore, we can conclude that: $$R\leq \limsup_{ n \to \infty } \left( \max_{q\in \Delta(\mathcal{X})}I(q,W)+\frac{1}{n}+P^n_{e}\cdot R \right)= \max_{q\in \Delta(\mathcal{X})}I(q,W)$$as $P^n_{e}\to 0$. 
>    
>    ---
>    To show the converse, let $q\in \Delta(\mathcal{X})$ and $R> 0$.  
>    
   Let $\mathcal{F}_{n}:=\{ f:\mathcal{M}_{n}\to \mathcal{X}^n \}$ be the set of all possible encoders. Let $f_{n}\sim \mathcal{F}_{n}$ s.t. $$\mathbb{P}(f_{n}(m)=\xi)=\prod_{i=1}^{n}q(\xi_{i}),\quad \forall m\in \mathcal{M}_{n}$$Then, for $\overline{\lambda}_{m}:=\mathbb{E}[\lambda_{m}(f_{n})]$, $\overline{\lambda}_{1}=\overline{\lambda}_{m}$ for all $m\in \mathcal{M}_{n}$ by symmetry. 
>    
>    Now, we define:$$\mathbb{E}[P^n_{e}(f_{n})]=\mathbb{E}\left[ \frac{1}{2^{nR}}\sum_{m}^{}\lambda_{m}(f_{n}) \right]=\frac{1}{2^{nR}}\sum_{m}^{}\mathbb{E}[\lambda_{m}(f_{n})]=\frac{1}{2^{nR}}\sum_{m}^{}\overline{\lambda}_{m}=\overline{\lambda}_{1}$$We now define the decoder as follows:$$\phi_{n}(y):=\begin{cases}x&\text{if }\{ \xi\in \mathcal{X}^n:(\xi,\eta)\in \mathcal{A}^n_{\delta}(q\times W) \}=\{ x \}\\{\bot}&\text{otherwise}\end{cases}$$for some $\delta>0$. 
>    
>    Let $Y$ be the outcome of the channel of $f_{n}(1)$. Define $E_{i}$ as the event that $(f_{n}(i),Y)\in \mathcal{A}^n_{\delta}(q \times W)$. Then, $$\mathbb{P}(\phi_{n}(y)\neq 1)=\mathbb{P}\left( E_{1}^c\cup \bigcup_{i=2}^{2^{mR}}E_{i} \right)\leq \mathbb{P}(E^c_{1})+\sum_{i\geq 2}^{}\mathbb{P}(E_{i})$$ However, by definition of $f_{n}$ and [[Typical Sequence|Proposition 4]], $$\mathbb{P}(\phi_{n}(y)\neq 1)\leq \mathbb{P}(E_{1}^c)+2^{-n(I(q,W)-3\delta-R)}$$Hence, if $R<I(q,W)$, then we can choose $\delta$ and $n$ s.t. $\mathbb{P}(\phi_{n}(y)\neq 1)\leq 2\delta$.
>    
>    Now, let $q^{*}:=\arg\max I(q,W)$. Then, for $R<C(W)$, we have $\delta$ and $n$ s.t. $\mathbb{E}_{f_{n}}[\phi_{n}(y)\neq 1]\leq 2\delta$. Hence, there exists a deterministic functon $f_{n}$ s.t. $$P^n_{e}(f_{n})\leq 2\delta$$Lastly, wlog assume that $\lambda_{1}(f_{n})\leq\dots\leq \lambda_{2^{nR}}(f_{n})$ and as: $$\frac{1}{2^{nR}}\sum_{m\in \mathcal{M}}^{}\lambda_{m}(f_{n})\leq 2\delta$$we have that $$2\delta \cdot 2^{nR}\geq \sum_{i=1}^{2^{nR}}\lambda_{i}(f_{n})\geq \sum_{i=2^{nR}-1}^{2^{nR}}\lambda_{i}(f_{n})\geq $$
>    
> 2. Notice that:  $$\begin{align}\sum_{x}^{}q(x)D(W(\cdot |x)\|r)&=\sum_{x}^{}q(x)\sum_{y}^{}W(y|x)\log \frac{W(y|x)}{r(y)}\\&=\sum_{x}^{}q(x)\sum_{y}^{}W(y|x)\left( \log \frac{W(y|x)}{qW(y)}+\log \frac{qW(y)}{r(y)} \right)\\&=I(q,W)+\sum_{x,y}^{}q(x)W(y|x)\log \frac{qW(y)}{r(y)}\\&=I(q,W)+D(qW\|r)\end{align}$$Therefore, $$\max_{q\in\Delta(\mathcal{X})}I(q,W)\leq \max_{q\in\Delta(\mathcal{X})}\sum_{x}^{}q(x)D(W(\cdot |x)\|r)\leq \max_{x}D(W(\cdot |x)\|r)$$Hence, $C(W)\leq \max_{x}D(W(\cdot|x)\|r)$ for every $r\in \Delta(\mathcal{Y})$ and we have the inequality $\leq$.
>    
>    Now, let $q^{*}:=\arg\max_{q\in \Delta(\mathcal{X})}I(q,W)$. Then, by KKT, $$C\geq \max_{x}D(W(\cdot |x)\|q^{*} W)$$and hence, we have the statement.

^45d60f



---
> [!lemma] Proposition 5
> For $\mathcal{X},\mathcal{Y}$ and a DMC $W$ from $\mathcal{X}$ to $\mathcal{Y}$, let $W'$ be another DMC from $\mathcal X\times \mathcal{X}$ to $\mathcal{Y}\times \mathcal{Y}$ s.t. $$W'_{(x_{1},x_{2}),(y_{1},y_{2})}=W_{x_{1},y_{1}}W_{x_{2},y_{2}}$$
> Then, 
> 1. a rate $R$ is achievable on $W$ if and only if $2R$ is achievable on $W'$.

> [!proof]-
> We have:
> 1. Assume that $R$ is achievable on $W$. Let $f'_{n}:=f_{2n}$ and $\phi'_{n}:=\phi_{2n}$. Then, for any $m\in \mathcal{M}_{2n}:=\{ 0,1,\dots,2^{2nR} \}$, $$\lambda_{m}:=\sum_{\begin{subarray}{c}y_{1:2n}\in \mathcal{Y}^{2n}\\ \phi_{2n}(y_{1:2n})\neq m\end{subarray}}\prod_{i=1}^{n}W_{f_{2n}(m)_{2i-1,2i},y_{2i-1,2i}}=\sum_{\begin{subarray}{c}y_{1:2n}\in \mathcal{Y}^{2n}\\ \phi_{2n}(y_{1:2n})\neq m\end{subarray}}\prod_{i=1}^{2n}W_{f_{2n}(m)_{i},y_{i}}$$ Therefore, $\lim_{ n \to \infty }\max_{m\in \mathcal{M}_{2n}}\lambda_{m}=0$ and $2R$ is achievable on $W'$.
> 2. Analogous.

---
> [!lemma] Proposition 6
> Consider two independent DMC $(\mathcal{X}_{1},W_{1},\mathcal{Y}_{1})$ and $(\mathcal{X}_{2},W_{2},\mathcal{Y}_{2})$ with capacities $C_{1}$ and $C_{2}$. 
> 1. The DMC $(\mathcal{X}_{1}\times \mathcal{X}_{2},W_{1}\otimes W_{2},\mathcal{Y}_{1}\times \mathcal{Y}_{2})$ has the capacity $C:=C_{1}+C_{2}$:

> [!proof]-
> Let $C$ be the capacity of the joint channel.
> 1. We first show that $C\geq C_{1}+C_{2}$. Let $q_{1}$ and $q_{2}$ be the pmf on $\mathcal{X}_{1}$ and $\mathcal{X}_{2}$ respectively, s.t. $C_{i}=I(q_{i},W_{i})$. Notice that: $$\begin{align}C\geq I(q_{1}\otimes q_{2},W_{1}\otimes W_{2})&=I((X_{1},X_{2});(Y_{1},Y_{2}))\\&=H(X_{1},X_{2})-H(X_{1},X_{2}|Y_{1},Y_{2})\\&=H(X_{1})+H(X_{2})-H(X_{1}|Y_{1},Y_{2})-H(X_{2}|X_{1},Y_{1},Y_{2})\\&=H(X_{1})+H(X_{2})-H(X_{1}|Y_{2})-H(X_{2}|,Y_{2})\\&=I(q_{1},W_{1})+I(q_{2},W_{2})\\&=C_{1}+C_{2}\end{align}$$
>    Conversely, we will show that $C_{1}+C_{2}\geq C$. Let $q$ be the pmf on $\mathcal{X}_{1}\times \mathcal{X}_{2}$ s.t. $I(q,W_{1}\otimes W_{2})=C$. Then, $$\begin{align}C&=I(q,W_{1}\otimes W_{2})\\&\leq H(Y_{1})+H(Y_{2})-H(Y_{1},Y_{2}|X_{1},X_{2})\end{align}$$where $$\begin{align}H(Y_{1},Y_{2}|X_{1}=x_{1},X_{2}=x_{2})&=H(Y_{1}|X_{1}=x_{1})+H(Y_{2}|X_{2}=x_{2})\end{align}$$Therefore, $$\begin{align}H(Y_{1},Y_{2}|X_{1},X_{2})&=\sum_{x_{1},x_{2}}^{}q(x_{1},x_{2})(H(Y_{1}|X_{1}=x_{1})+H(Y_{2}|X_{2}=x_{2}))\\&=\end{align}$$

---
##### Examples
> [!h] Example 1 (Binary Symmetric Channel)
> The ***binary symmetric channel*** for $\varepsilon$, $\text{BSC}(\varepsilon)$ is given as: $$\text{BSC}(\varepsilon):=\begin{bmatrix}1-\varepsilon&\varepsilon\\\varepsilon&1-\varepsilon\end{bmatrix}$$
> Then, $C(\text{BSC}(\varepsilon))=1-H_{b}(\varepsilon)$ bits.

^5ed592

> [!proof]-
> We have that for any $q\in \Delta(\mathcal{X})$, $$\begin{align}I(q,W)&=H(Y)-\sum_{x}^{}q(x)H(Y|X=x)\\&=H(Y)-\sum_{x}^{}q(x)H_{b}(\varepsilon)\\&=H(Y)-H_{b}(\varepsilon)\end{align}$$Hence, by Shannon, the maximum is attained when $q=\left( \frac{1}{2}, \frac{1}{2} \right)$ with $I(q,W)=1-H_{b}(\varepsilon)$.

^fe29b9

---
> [!h] Example 2 (Z-channel)
> For $\mathcal{X}=\mathcal{Y}=\{ 0,1 \}$, the ***$Z$-channel*** is given as: $$W:=\begin{bmatrix}1&0\\ \frac{1}{2}& \frac{1}{2}\end{bmatrix}$$

^54476c

> [!proof]-
> Let $p=(1-\varepsilon,\varepsilon)$. We have that: $H(Y|X=0)=0$ and $H(Y|X=1)=1$. Hence,  $$H(Y|X)=\varepsilon$$Further, $qW=\left( \frac{2-\varepsilon}{2}, \frac{\varepsilon}{2} \right)$
> 
> We have that: $$\begin{align}I(p,Q)&=I(X;Y)=H(Y)-H(Y|X)\\&=-\left(  1-\frac{\varepsilon}{2} \right)\log\left(  1-\frac{\varepsilon}{2} \right)-\frac{\varepsilon}{2}\log\frac{\varepsilon}{2}-\varepsilon\end{align}$$Then, $\frac{d}{d\varepsilon}I(p,Q)=-\frac{1}{2}\log \frac{\varepsilon}{2} -\frac{1}{2}+\frac{1}{2}\log\left( 1-\frac{\varepsilon}{2} \right)+\frac{1}{2}-1=0$ and $$\log\left( \frac{2-\varepsilon}{\varepsilon} \right)=2$$Therefore, $\frac{2-\varepsilon}{\varepsilon}=4$ and $\varepsilon=\frac{2}{5}$. Hence, 

^dac41a

---
> [!h] Example 3 (Weakly Symmetric Channel)
> A DMC $W$ is ***weakly symmetric*** if:
> 1. for all $i,j\in [n]$, $W_{i,:}=\sigma W_{j,:}$ where $\sigma\in S_{n}$, i.e. the rows are permutations of each other.
> 2. $\sum_{x}W(y|x)=\sum_{x}W(y'|x)$ for all $y=y'$.
> 
> Then, 
> 1. $C(W)=\log \left| \mathcal{Y} \right|-H(W_{i,:})$. 

^9f9b95

---
> [!h] Example 4 (Binary Erasure Channel)
> A ***binary erasure channel*** for $\rho$ is given by $\mathcal{X}:=\{ 0,1 \}$, $\mathcal{Y}:=\{ 0,1,{\bot} \}$ where:
> $$\text{BEC}(\rho):=\begin{bmatrix}1-\rho&0&\rho\\0&1-\rho&\rho\end{bmatrix}$$Then, 
> 1. $C(\text{BEC}(\rho))=1-\rho$.

^ca15d1

> [!proof]-
> We have that for any $q\in \Delta(\mathcal{X})$ $$\begin{align}I(q,W)&=H(X)-H(X|Y)\\&=H(X)-q(0)\underbrace{ H(X|Y=0) }_{ =0 }-q(1)\underbrace{ H(X|Y=1) }_{ =0 }-q({\bot})\underbrace{ H(X|Y={\bot}) }_{ H(X) }\\&=H(X)-\rho H(X)\\&=(1-\rho)H(X)\end{align}$$whose maximum is attained at $q=\left( \frac{1}{2}, \frac{1}{2} \right)$ with $I(q,W)=(1-\rho)$.

^39768b

---
