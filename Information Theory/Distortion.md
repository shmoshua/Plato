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
---
> [!lemma] Theorem 2 (Shannon)
> For $\mathcal{X},\mathcal{Y}$ finite,  
> 1. $R(D)=R^{(I)}(D)$.
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