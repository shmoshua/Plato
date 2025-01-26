#Definition #InformationTheory 

> [!definition]
> Let $\mathcal{X},\mathcal{Y}$ be a finite set and $p\in \Delta(\mathcal{X})$. 
> 1. A ***distortion*** is a map $d:\mathcal{X}\times \mathcal{Y}\to \mathbb{R}_{\geq 0}$.

- **Remark**: A distortion $d:\mathcal{X}\times \mathcal{Y}\to \mathbb{R}_{\geq 0}$ can be extended to $$d:\mathcal{X}^n\times \mathcal{Y}^n\to \mathbb{R}_{\geq 0}, \quad (x,y)\mapsto \frac{1}{n}\sum_{i=1}^{n}d(x_{i},y_{i})$$
- **Related definition**: A ***description of rate $R$*** is $(f_{n},\phi_{n})_{n}$ where $f_{n}:\mathcal{X}^n\to [2^{nR}]$ and $\phi_{n}:[2^{nR}]\to \mathcal{Y}^n$.
	1. For $R\geq 0$ and $D\geq 0$, $(R,D)$ is ***achievable*** if for all $\delta>0$, there exists $n$ large enough and a description $(f_{n},\phi_{n})$ of rate $R$ s.t. $$\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq D+\delta$$
- **Related definition**: We have that:
	1. $R(D):=\inf_{R}\{ R\geq 0 :(R,D)\text{ is achievable} \}$.
	2. $R^{(I)}(D):=\min_{p_{Y|X}: \mathbb{E}p_{XY}[d(x,y)]\leq D}I_{p_{XY}}(X;Y)$ where $p_{XY}(x,y):=p_{X}(x)p_{Y|X}(y|x)$.
	3. $D(R):=\inf_{D}\{ D\geq 0 :(R,D)\text{ is achievable} \}$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $R^{(I)}(D)$ is monotonically decreasing in $D$. 
> 2. $R^{(I)}(D)$ is convex in $D$. 
> 3. $R^{(I)}(D)$ is continuous over $D\in [0,\infty)$.

> [!proof]-
> We have that:
> 1. Obvious.
> 2. Let $p^1_{Y|X}$ and $p^2_{Y|X}$ achieve $R^{(I)}(D_{1})$ and $R^{(I)}(D_{2})$. Consider: $$p_{Y|X}:=\lambda p^1_{Y|X}+(1-\lambda)p^2_{Y|X}$$Then, $\mathbb{E}_{p_{X}p_{Y|X}}[d(X,Y)]\leq \lambda D_{1}+(1-\lambda)D_{2}$ and: $$\begin{align}R^{(I)}(\lambda D_{1}+(1-\lambda)D_{2})&\leq I_{p_{XY}}(X;Y)\\&=I(p_{X},\lambda p^1_{Y|X}+(1-\lambda)p^2_{Y|X})\\&\leq \lambda I(p_{X},p^1_{Y|X})+(1-\lambda)I(p_{X},p^2_{Y|X})\\&=\lambda R^{(I)}(D_{1})+(1-\lambda)R^{(I)}(D_{2})\end{align}$$
> 3. The continuity at $(0,\infty)$ is shown by convexity. 
---
> [!lemma] Lemma 2
> Let $p_{Y|X}$ s.t. $\mathbb{E}[d(X,Y)]\leq D$ for some $D\geq 0$. 
> 1. there exists a description $(f_{n},\phi_{n})_{n}$ with $n_{0}\geq 0$ s.t. for all $n\geq n_{0}$, $$\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq D+\delta$$ of rate $I(X;Y)+\varepsilon$.

> [!proof]+
> Let $0<\varepsilon'<\varepsilon<\tilde{\varepsilon}$ and set $R:=I(X;Y)+\tilde{\varepsilon}$. Let $p_{Y}$ be the marginal of $p_{X}(x)p_{Y|X}(y|x)$.
> 
> Now, we define $(f_{n},\phi_{n})_{n}$ as follows. Fix $n$. Let $\mathcal{C}$ be a codebook, i.e. $\mathcal{C}\in \mathcal{Y}^{2^{nR}\times n}$. Denote $\mathcal{C}[i]$ as the $i$-th row of $\mathcal{C}$. Then, 
> $$f_{n}:\mathcal{X}^n\to[2^{nR}],\quad x\mapsto \begin{cases}j&j=\min\{ i\geq 1:(x,\mathcal{C}[i])\in T^n_{\varepsilon}(p_{X}p_{Y|X}) \}\\{\bot}&\text{otherwise}\end{cases}$$and $\phi_{n}:[2^{nR}]\to \mathcal{Y}^n, j\mapsto \mathcal{C}[j]$.
> 
> Let $X:=(X_{1},\dots,X_{n})\in \mathcal{X}^n$ i.i.d sampled with $p_{X}$. Then, $$\begin{align}\mathbb{P}(f_{n}(X)\neq  {\bot})&=\sum_{x\in \mathcal{X}^n}^{}\mathbb{P}(X=x)\mathbb{P}(f_{n}(X)\neq {\bot}|X=x)\\&\leq\sum_{x\in T^n_{\varepsilon}(p_{X}p_{Y|X})}^{}\mathbb{P}(X=x)\mathbb{P}(f_{n}(x)\neq {\bot})+\mathbb{P}(X\notin T^n_{\varepsilon}(p_{X}p_{Y|X}))\end{align}$$Now, as the rows of $\mathcal{C}$ are independent, foir a fixed $x$, $$(x,\mathcal{C}[i])\in T^n_{\varepsilon}(p_{X}p_{Y|X})$$are independent events over $i\in [2^{nR}]$. Notice that we have: $$\lim_{ n \to \infty } 2^{nR}2^{-n(I(X,Y)+4\delta_{XY})}=\lim_{ n \to \infty } 2^{n(\tilde{\varepsilon}+4\delta_{XY})}=\infty$$For all $\tilde{\varepsilon}>4 \delta_{XY}$. Hence, we have that $\lim_{ n \to \infty }\mathbb{P}(f_{n}(x)\neq {\bot})=1$. Therefore, $$\lim_{ n \to \infty } \mathbb{P}(f_{n}(X)\neq {\bot})=\lim_{ n \to \infty } \sum_{x\in \mathcal{X}^n}^{}\mathbb{P}(X=x)\chi_{T^n_{\varepsilon}(p_{X}p_{Y|X})}(x)\mathbb{P}(f_{n}(x)\neq {\bot})=1$$Hence,$$1=\lim_{ n \to \infty } \mathbb{P}(f_{n}(X)\neq {\bot})=\lim_{ n \to \infty } \sum_{}^{}\mathbb{P}(\mathcal{C})\mathbb{P}(f_{n}(X)\neq {\bot}|\mathcal{C})$$and we have a series of codebooks $(\mathcal{C}_{n})_{n}$ s.t. $\mathbb{P}(f_{n}(X)\neq {\bot}|\mathcal{C}_{n})\to 1$. Now, $$\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq(1+\varepsilon)D$$
---
> [!lemma] Theorem 3 (Shannon)
> For $\mathcal{X},\mathcal{Y}$ finite,  
> 1. $R(D)=R^{(I)}(D)$.

> [!proof]+
> We have that:
> 1. To show that $R(D)\geq R^{(I)}(D)$, let $R\geq 0$ s.t. $(R,D)$ is achievable. We claim that:
> 	1. **Claim 1**: If $(f,\phi)$ is a description of rate $R$ and $\mathbb{E}[d(X,\phi(f(X)))]\leq \lambda$, then $R\geq R^{(I)}(\lambda)$ for all $\lambda$. 
> 	   We have that: $$\begin{align}nR&\geq H( f(X))=H(f(X))-H(f(X);X)\\&=I(X;f(X))\\&\geq  I(X;Y)\\&=H(X)-H(X|Y)\\&=\sum_{i=1}^{n}H(X_{i})-H(X_{i}|Y,X_{1:i-1})\\&\geq \sum_{i=1}^{n}H(X_{i})-H(X_{i}|Y_{i})\\&=\sum_{i=1}^{n}I(X_{i};Y_{i})\\&\geq n\cdot  \frac{1}{n}\sum_{i=1}^{n}R^{(I)}(\mathbb{E}[d(X_{i},Y_{i})])\end{align}$$As $R^{(I)(\cdot)}$ is convex and monotonously decreasing, we have: $$nR\geq n\cdot R^{(I)}\left( \frac{1}{n}\sum_{i=1}^{n}\mathbb{E}[d(X_{i},Y_{i})] \right)=n\cdot R^{(I)}(\mathbb{E}[d(X,Y)])\geq n\cdot R^{(I)}(\lambda)$$
> 	
> 	Therefore, let $(\delta_{i})_{i}$ s.t. $\delta_{i}\to 0$. Then, by Claim 1 and continuity: $$R\geq \lim_{ i \to \infty } R^{(I)}(D+\delta_{i})=R^{(I)}(D)$$
> 2. To show that $R^{(I)}(D)\leq R(D)$, we aim to find $p_{Y|X}$ with $\mathbb{E}[d(x,y)]\leq D$ s.t. $I(X;Y)\leq R(D)$
> 	   
---
##### Examples
> [!h] Example 1 (Bernoulli source and Hamming distortion)
> Let $\mathcal{X},\mathcal{Y}:=\{ 0,1 \}$ and $X\sim \text{Ber}(p)$. With the hamming distortion, we have:
> 1. $R(D)=\begin{cases}H_{b}(p)-H_{b}(D)&D\leq \min\{ p,1-p \}\\0&\text{otherwise}\end{cases}$

> [!proof]-
> We have that:
> 1. If $D>\min \{ p,1-p \}$, we show that $(0,D)$ is achievable. If $p \leq \frac{1}{2}$, we have for $n=1$,  $f:\mathcal{X}\to [1]$ and $\phi:[1]\mapsto \{ 0,1 \}$ s.t. $\phi=0$. Then, $$\mathbb{E}[d_{H}(X,0)]=p<D$$If $p \geq \frac{1}{2}$, then $\phi=1$ this time. Then, $\mathbb{E}[d_{H}(X,1)]=1-p<D$. Hence, $R(D)=0$. 
> 2. If $D\leq \min \{ p,1-p \}$, we use Shannon. Let $p_{Y|X}$ s.t. $\mathbb{E}[d(x,y)]\leq D$. Then, $$\begin{align} I(X;Y)&=H(X)-H(X|Y)\\&=H_{b}(p)-H(X\oplus  Y|Y)\\&\geq H_{b}(p)-H(X\oplus  Y)\\&=H_{b}(p)-H_{b}(\mathbb{P}(X\neq  Y))\end{align}$$As $\mathbb{P}(X\neq Y)=\mathbb{E}[d(X,Y)]\leq D\leq \frac{1}{2}$, we have $I(X;Y)\geq H_{b}(p)-H_{b}(D)$. Hence, $R(D)\geq H_{b}(p)-H_{b}(D)$.
>    
>    To show the other inequality, let $q:=\frac{p-D}{1-2D}$. Then, as $D\leq 1-p$, $q\leq 1$. Further, $q\geq 0$ as $D\leq p$ and $D\leq \frac{1}{2}$. Let $Y\sim \text{Ber}(q)$ independent of $Z\sim \text{Ber}(D)$. Let $X:= Y\oplus Z$. Then,  $$\mathbb{E}[d_{H}(X,Y)]=\mathbb{P}(X\neq Y)=D$$and we have $\mathbb{P}(X)=\mathbb{P}(Y\oplus Z)=p$. Therefore, we have that $I(X;Y)=H_{b}(p)-H_{b}(D)$ and this proves the statement.