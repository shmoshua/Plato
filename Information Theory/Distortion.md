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

> [!proof]-
> Let $0<\varepsilon'<\varepsilon<\tilde{\varepsilon}$ and set $R:=I(X;Y)+\tilde{\varepsilon}$. Let $p_{Y}$ be the marginal of $p_{X}(x)p_{Y|X}(y|x)$.
> 
> Now, we define $(f_{n},\phi_{n})_{n}$ as follows. Fix $n$. Let $\mathcal{C}$ be a codebook, i.e. $\mathcal{C}\in \mathcal{Y}^{2^{nR}\times n}$. Denote $\mathcal{C}[i]$ as the $i$-th row of $\mathcal{C}$. Then, 
> $$f_{n}:\mathcal{X}^n\to[2^{nR}],\quad x\mapsto \begin{cases}j&j=\min\{ i\geq 1:(x,\mathcal{C}[i])\in T^n_{\varepsilon}(p_{X}p_{Y|X}) \}\\{\bot}&\text{otherwise}\end{cases}$$and $\phi_{n}:[2^{nR}]\to \mathcal{Y}^n, j\mapsto \mathcal{C}[j]$.
> 
> Let $X:=(X_{1},\dots,X_{n})\in \mathcal{X}^n$ i.i.d sampled with $p_{X}$. Then, $$\begin{align}\mathbb{P}(f_{n}(X)\neq  {\bot})&=\sum_{x\in \mathcal{X}^n}^{}\mathbb{P}(X=x)\mathbb{P}(f_{n}(X)\neq {\bot}|X=x)\\&\leq\sum_{x\in T^n_{\varepsilon}(p_{X}p_{Y|X})}^{}\mathbb{P}(X=x)\mathbb{P}(f_{n}(x)\neq {\bot})+\mathbb{P}(X\notin T^n_{\varepsilon}(p_{X}p_{Y|X}))\end{align}$$Now, as the rows of $\mathcal{C}$ are independent, foir a fixed $x$, $$(x,\mathcal{C}[i])\in T^n_{\varepsilon}(p_{X}p_{Y|X})$$are independent events over $i\in [2^{nR}]$. Notice that we have: $$\lim_{ n \to \infty } 2^{nR}2^{-n(I(X,Y)+4\delta_{XY})}=\lim_{ n \to \infty } 2^{n(\tilde{\varepsilon}+4\delta_{XY})}=\infty$$For all $\tilde{\varepsilon}>4 \delta_{XY}$. Hence, we have that $\lim_{ n \to \infty }\mathbb{P}(f_{n}(x)\neq {\bot})=1$. Therefore, $$\lim_{ n \to \infty } \mathbb{P}(f_{n}(X)\neq {\bot})=\lim_{ n \to \infty } \sum_{x\in \mathcal{X}^n}^{}\mathbb{P}(X=x)\chi_{T^n_{\varepsilon}(p_{X}p_{Y|X})}(x)\mathbb{P}(f_{n}(x)\neq {\bot})=1$$Hence,$$1=\lim_{ n \to \infty } \mathbb{P}(f_{n}(X)\neq {\bot})=\lim_{ n \to \infty } \sum_{}^{}\mathbb{P}(\mathcal{C})\mathbb{P}(f_{n}(X)\neq {\bot}|\mathcal{C})$$and we have a series of codebooks $(\mathcal{C}_{n})_{n}$ s.t. $\mathbb{P}(f_{n}(X)\neq {\bot}|\mathcal{C}_{n})\to 1$. Now, notice that by [[Typical Sequence|Lemma 5]], if $(x,\mathcal{C}[j])\in T^n_{\varepsilon}(p_{X}p_{Y|X})$ then $d(x,\mathcal{C}[j])\leq (1+\varepsilon)D$. Hence, $$\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq(1+\varepsilon)D\cdot \mathbb{P}(f_{n}(X)\neq {\bot}|\mathcal{C}_{n})+d_{\max}\cdot \mathbb{P}(f_{n}(X)= {\bot}|\mathcal{C}_{n})$$Hence, $\lim_{ n \to \infty }\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq (1+\varepsilon)D$.
---
> [!lemma] Theorem 3 (Shannon, Source Coding Theorem)
> For $\mathcal{X},\mathcal{Y}$ finite,  
> 1. $R(D)=R^{(I)}(D)$.

> [!proof]-
> We have that:
> 1. To show that $R(D)\geq R^{(I)}(D)$, let $R\geq 0$ s.t. $(R,D)$ is achievable. We claim that:
> 	1. **Claim 1**: If $(f,\phi)$ is a description of rate $R$ and $\mathbb{E}[d(X,\phi(f(X)))]\leq \lambda$, then $R\geq R^{(I)}(\lambda)$ for all $\lambda$. 
> 	   We have that: $$\begin{align}nR&\geq H( f(X))=H(f(X))-H(f(X);X)\\&=I(X;f(X))\\&\geq  I(X;Y)\\&=H(X)-H(X|Y)\\&=\sum_{i=1}^{n}H(X_{i})-H(X_{i}|Y,X_{1:i-1})\\&\geq \sum_{i=1}^{n}H(X_{i})-H(X_{i}|Y_{i})\\&=\sum_{i=1}^{n}I(X_{i};Y_{i})\\&\geq n\cdot  \frac{1}{n}\sum_{i=1}^{n}R^{(I)}(\mathbb{E}[d(X_{i},Y_{i})])\end{align}$$As $R^{(I)(\cdot)}$ is convex and monotonously decreasing, we have: $$nR\geq n\cdot R^{(I)}\left( \frac{1}{n}\sum_{i=1}^{n}\mathbb{E}[d(X_{i},Y_{i})] \right)=n\cdot R^{(I)}(\mathbb{E}[d(X,Y)])\geq n\cdot R^{(I)}(\lambda)$$
> 	
> 	Therefore, let $(\delta_{i})_{i}$ s.t. $\delta_{i}\to 0$. Then, by Claim 1 and continuity: $$R\geq \lim_{ i \to \infty } R^{(I)}(D+\delta_{i})=R^{(I)}(D)$$
> 2. To show that $R^{(I)}(D)\geq R(D)$, let $p_{Y|X}$ attain $R^{(I)}(D)$. Then, by Lemma 2, there exists a description $(f_{n},\phi_{n})_{n}$ with $\mathbb{E}[d(X,\phi_{n}(f_{n}(X)))]\leq D+\delta$ of rate $I(X;Y)+\varepsilon$. Hence, $I(X;Y)=R^{(I)}(D)\geq R(D)$. 
---
> [!lemma] Proposition 4
> Let $p_{X}\in \Delta(\mathcal{X})$ be an i.i.d source and $d$ a distortion measure. 
> 1. for any $w:\mathcal{X}\to \mathbb{R}$ s.t. $d(x,y)\geq w(x)$ for all $x\in \mathcal{X}$, $y\in \mathcal{Y}$, $$R_{d'}(D)=R_{d}(D+\mathbb{E}[w(X)])$$where $d':\mathcal{X}\times \mathcal{Y}\to \mathbb{R}_{\geq 0},(x,y)\mapsto d(x,y)-w(x)$.
> 2. If there exists $\widehat{y}\in \mathcal{Y}$ s.t. $\widehat{y}\in \arg\min_{y\in \mathcal{Y}}d(x,y)$ for all $x\in \mathcal{X}$, then, $$R(D)=0,\quad \forall D\geq \mathbb{E}[\min_{y\in \mathcal{Y}}d(X,y)]$$

> [!proof]-
> We have that:
> 1. For a fixed $p_{Y|X}$, we have: $$\mathbb{E}[d'(X,Y)]=\mathbb{E}[d(X,Y)-w(X)]=\mathbb{E}[d(X,Y)]-\mathbb{E}[w(X)]$$Hence, $$R_{d'}(D)=\min_{p_{Y|X}: \mathbb{E}[d'(X,Y)]\leq D}I(X;Y)=\min_{p_{Y|X}: \mathbb{E}[d(X,Y)]\leq D+\mathbb{E}[w(X)]}I(X;Y)=R_{d}(D+\mathbb{E}[w(X)])$$
> 2. Let $w:\mathcal{X}\to \mathbb{R}$ with $w(x):=\min_{y\in \mathcal{Y}}d(x,y)$. Then, we have that by assumption $d'(x,\widehat{y})=0$ for all $x\in \mathcal{X}$. Let $p_{Y|X}(y|x)=\delta_{y,\widehat{y}}$. Then, we have that: $$\mathbb{E}[d'(X,Y)]=\sum_{x\in \mathcal{X}}^{}p(x)d'(x,\widehat{y})=0$$and $I(X;Y)= 0$. Hence, $R_{d'}(D)=0$ for all $D\geq 0$. Therefore, by 1, $$R(D)=R(D-\mathbb{E}[w(X)])=0,\quad \forall D\geq \mathbb{E}[w(X)]$$
---
> [!lemma] Theorem 5 (Source-Channel Separation Theorem)
> We have the setting: $$\begin{array}{cccccc}\mathcal{S}^k&\to&\mathcal{X}^n&\xrightarrow{W}& \mathcal{Y}^n&\to& \mathcal{T}^k\\S_{1:k}&\mapsto &X_{1:n}&\mapsto &Y_{1:n}&\mapsto &T_{1:k}\end{array}$$
> Let $\rho_{S}$ denote the number of source symbols per second and $\rho_{C}$ the number of channel uses per second. Then, 
> 1. if $\rho_{S}R(D)< \rho_{C}C(W)$, we can transmit the source over the channel $W$ with separative approach. 
> 2. if the source can be sent with distortion $D$, then $\rho_{S}R(D)\leq \rho_{C}C(W)$. 

> [!proof]-
> We have:
> 1. hihi
> 2. We have that $k$ source symbols are generated every $k\cdot\rho_{S}^{-1}$ seconds and $n$ channel uses every $n\cdot\rho_{C}^{-1}$ seconds. Therefore, $\frac{k}{n}=\rho_{S}\rho_{C}^{-1}$. Hence, if the source can be sent then:$$\begin{align}nC(W)&\geq  I(S_{1:k};T_{1:k})\\&=H(S_{1:k})-H(S_{1:k}|T_{1:k})\\&\geq \sum_{i=1}^{k}H(S_{i})-H(S_{i}|T_{i})\\&=\sum_{i=1}^{k}I(S_{i};T_{i})\\&\geq  k \frac{1}{k}\sum_{i=1}^{k}\cdot  R(\mathbb{E}[d(S_{i},T_{i})])\\&\geq k\cdot R\left( \mathbb{E}[d(S_{1:k},T_{1:k})]\right)\\&\geq k\cdot R(D)\end{align}$$Therefore, $$\rho_{S}R(D)\leq \frac{k}{n}\rho_{C} \cdot  R(D)\leq \rho_{C}\cdot C(W)$$
---
> [!lemma] Theorem 6 (Source-Channel Separation with Feedback)
> Consider an i.i.d source $U_{1:k}\in \mathcal{U}^k$ for a finite $\mathcal{U}$, a bounded distortion function $d:\mathcal{U}\times \widehat{\mathcal{U}}\to \mathbb{R}_{\geq 0}$ and a DMC $W$. A ***combined source channel coding scheme*** in the presence of feedback is described as follows: 
> 1. the encoder is a sequence of mappings $f_{i}:(U_{1:k},Y_{1:i-1})\mapsto X_{i}$, 
> 2. the decoder is a mapping $g:Y_{1:n}\to \widehat{U}_{1:k}$. 
> 
> The combined source-channel coding scheme with feedback can achieve expected distortion $D$ only if: $$\frac{n}{k}C(W)\geq R(D)$$

> [!proof]-
> We have that: $$\begin{align}kR(D)&\leq kR(\mathbb{E}[d(U^k,\widehat{U}^k)])\\&=kR\left( \sum_{i=1}^{k} \frac{1}{k}\mathbb{E}[d(U_{i},\widehat{U}_{i})] \right) \\&,\leq \sum_{i=1}^{k}R(\mathbb{E}[d(U_{i},\widehat{U}_{i})])\\&=\sum_{i=1}^{k}I(U_{i},\widehat{U}_{i})\\&=\sum_{i=1}^{k}H(U_{i})-H(U_{i}|\widehat{U}_{i})\\&\leq H(U^k)-\sum_{i=1}^{k}H(U_{i}|\widehat{U}^k,U_{1:i-1})\\&=H(U^k)-H(U^k|\widehat{U}^k)\\&=I(U^k|\widehat{U}^k)\\&\leq I(U^k|Y^n)\\&=H(Y^n)-H(Y^n|U^k)\\&=\sum_{i=1}^{n}H(Y_{i}|Y_{1:i-1})-H(Y_{i}|Y_{1:i-1},U^k)\\&\leq\sum_{i=1}^{n}H(Y_{i})-H(Y_{i}|Y_{1:i-1},U^k,X_{i})\\&=\sum_{i=1}^{n}H(Y_{i})-H(Y_{i}|X_{i})\\&=\sum_{i=1}^{n}I(Y_{i};X_{i})\\&\leq nC(W)\end{align}$$
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
---
> [!h] Example 2 (Erasure distortion)
> Let $\mathcal{X}:=\{ 0,1 \}$, $\mathcal{Y}:=\{ 0,1,? \}$ and $X\sim \text{Ber}( 1/2)$. With the following distortion: $$d:=\begin{bmatrix}0&\infty&1\\ \infty & 0 & 1\end{bmatrix}$$we have that $R(D)=\begin{cases}1-D&D\leq 1\\0&D\geq 1\\\end{cases}$.

> [!proof]-
> Let $p_{Y|X}$ given s.t. $p_{Y|X}(1|0)=p_{Y|X}(0|1)=0$. Then, $$\mathbb{E}[d(X,Y)]=\frac{1}{2}p_{Y|X}(?|0)+\frac{1}{2}p_{Y|X}(?|1)=\mathbb{P}(Y=?)$$Assume that:
> 1. if $D\geq 1$, then by choosing $p_{Y|X}(? | x)=1$, we have that $\mathbb{E}[d(X,Y)]\leq D$ and $R(D)=0$.
> 2. if $D\leq 1$, then we have: $$\begin{align}I(X;Y)&=H(X)-H(X|Y)\\&=1-\underbrace{ \mathbb{P}(Y=0)H(X|Y=0) }_{ =0 }-\underbrace{ \mathbb{P}(Y=1)H(X|Y=1) }_{ =0 }-\mathbb{P}(Y=?)H(X|Y=?)\\&=1-\mathbb{P}(Y=?)H(X|Y=?)\\&\geq 1-D\end{align}$$where choosing $p_{Y|X}(y|x)=\begin{cases}1-D&y=x\\D&y=?\\0&\text{otherwise}\end{cases}$ we have that: $$I(X;Y)=1-D\cdot 1=1-D$$
---
> [!h] Example 3
> Let $\mathcal{X},\mathcal{Y}:=\{ 0,1 \}$ and $X\sim \text{Ber}( 1/2)$. With the following distortion: $$d:=\begin{bmatrix}0&\infty\\ 1 & 0\end{bmatrix}$$we have that $R(D)=\begin{cases}1-\left( \frac{1+2D}{2}\right)H_{b}\left( \frac{1}{1+2D} \right) &D\leq 1 /2\\0&D\geq 1 /2\\\end{cases}$.

> [!proof]-
> Let $p_{Y|X}$ given s.t. $p_{Y|X}(1|0)=0$. Then, $$\mathbb{E}[d(X,Y)]=\frac{1}{2}p_{Y|X}(0|1)$$Assume that:
> 1. if $D\geq \frac{1}{2}$, then by choosing $p_{Y|X}(0 | x)=1$, we have that $\mathbb{E}[d(X,Y)]\leq D$ and $R(D)=0$.
> 2. if $D\leq \frac{1}{2}$, then we have: $$\begin{align}I(X;Y)&=H(X)-H(X|Y)\\&=1-\mathbb{P}(Y=0)H(X|Y=0)-\mathbb{P}(Y=1)H(X|Y=1)\\&=1-\left( \frac{2-a}{2} \right)H_{b}\left( \frac{1}{2-a} \right)\\&\geq 1-\left( \frac{1+2D}{2}\right)H_{b}\left( \frac{1}{1+2D} \right)  \end{align}$$where for $p_{Y|X}(y|1)=(2D, 1-2D)$, we have that $I(X;Y)$ is the minimum. 
---
> [!h] Example 4
> Let $\mathcal{X},\mathcal{Y}:=[m]$ and $X\sim \text{Uni}(\mathcal{X})$. Consider the Hamming distortion, $$d(x,y):=\begin{cases}0&x=y\\1&x\neq y\end{cases}$$Then, $R(D)=\begin{cases}\log m-H_{b}(D)-D\log(m-1)&D\leq \frac{m-1}{m}\\0&D\geq \frac{m-1}{m}\end{cases}$

> [!proof]-
> We have that: $\mathbb{E}[d(X,Y)]=\mathbb{P}(Y\neq X)$. Hence, 
> 1. if $D\geq \frac{m-1}{m}$, then a deterministic output has $\mathbb{E}[d(X,Y)]=\frac{m-1}{m}$ with $I(X;Y)=0$.
> 2. if $D\leq \frac{m-1}{m}$, we have that: $$\begin{align}I(X;Y)&=H(X)-H(X|Y)\\&\geq \log m-H_{b}(P_{e})-P_{e}\log(m-1)\\&\geq \log m-H_{b}(D)-D\log(m-1)\end{align}$$
> 	Now, if we choose: $$p_{Y|X}(y|x)=\begin{cases}1-D&y=x\\ \frac{D}{m-1}&y\neq x\end{cases}$$then, we have $\mathbb{P}(Y\neq X)\leq D$ and we have that: $$\begin{align}H(X|Y)&=\sum_{y}^{}\sum_{x}p_{Y|X}(y|x)H(X|Y=y)\\&=\frac{1}{m}\sum_{y}^{}H(X|Y=y)\\&=\frac{1}{m}\sum_{ y}^{}\left( D \log \frac{m-1}{D}+(1-D)\log \frac{1}{1-D} \right)\\&=H_{b}(D)+D\log (m-1)\end{align}$$Therefore, $R(D)=\begin{cases}\log m-H_{b}(D)-D\log(m-1)&D\leq \frac{m-1}{m}\\0&D\geq \frac{m-1}{m}\end{cases}$
---
> [!h] Example 5
> Let $\mathcal{X},\mathcal{Y}:=\{ 0,1,2 \}$ with $p_{X}=(0.5,0.25, 0.25)$ with distortion $d(x,y):=\left| x-y \right|$. Then, 
> 1. $R(0)=\frac{3}{2}$.
> 2. $D(0)=\frac{3}{4}$.

> [!proof]-
> We have that for $p_{Y|X}$,  
> 1. $R(0)$, then $p_{Y|X}(y|x)=\delta_{yx}$. Hence, $$\begin{align}I(X;Y)&=H(X)-H(X|Y)=\frac{3}{2}-0=\frac{3}{2}\end{align}$$
> 2. Assume that we have $R = 0$. Then, our transition is deterministic. Hence, we have $D(0)= \frac{3}{4}$
---
