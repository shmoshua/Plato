#Series #InformationTheory 

##### Problem 1
![[Mutual Information#^3fabf6]]
![[Mutual Information#^8b584b|p]]
---
##### Problem 2
Let $\mathcal{S}:=\{ X_{a_{1}},\dots,X_{a_{n}} \}$ and $\mathcal{T}:=\{ X_{b_{1}},\dots,X_{b_{m}} \}$ be subsets of $\Omega$. Then, 
$$\begin{align}H(\mathcal{S}\cup \mathcal{T})+H(\mathcal{S}\cap \mathcal{T})&= H(\mathcal{S})+H(\mathcal{T \backslash S}|\mathcal{S})+H(\mathcal{S}\cap \mathcal{T})\\&\leq H(\mathcal{S})+H(\mathcal{T \backslash S}|\mathcal{S}\cap \mathcal{T})+H(\mathcal{S}\cap \mathcal{T})\\&= H(\mathcal{S})+H(\mathcal{T })\end{align}$$
---
##### Problem 3
1. $nH_{\text{b}}(p)=nH(X_{1})=\sum_{i=1}^{n}H(X_{i})=H(X_{1},\dots,X_{n})$ due to independence. 
2. $H(X)\geq H(g(X))$
3. Chain rule
4. We have:$$\begin{align}H(Z_{1},\dots,Z_{K}|K)&=-\mathbb{E}\left( \log p(Z_{1},\dots,Z_{K}|K) \right)\\&=-\sum_{z_{1},\dots,z_{K},k}^{}p(z_{1},\dots,z_{K},k)\log\left( \frac{1}{2^k} \right)\\&=\sum_{z_{1},\dots,z_{K},k}^{}p(z_{1},\dots,z_{K},k)k\\&=\sum_{k}^{}p(k)k\\&=\mathbb{E}[K]\end{align}$$where $$\mathbb{E}[\log p(Z_{1}|K)]=\sum_{k}^{}p(Z_{i}=0|K=k)+p(Z_{i}=1|K=k)=\sum_{k}^{}1$$
5. $H(K)\geq 0$
6. Let $g:\mathcal{X}^2\to \{ 0,1 \}^{*}$ be $g(00)=g(11)=\Lambda$, $g(01)=0$ and $g(10)=1$. Then, $$f:\mathcal{X}^4\to \{ 0,1 \}^{*},\quad (X_{1},X_{2},X_{3},X_{4})=g(X_{1},X_{2})g(X_{3},X_{4})$$
---
##### Problem 4
Consider two independent fair coin flips and let $X,Y$ be the indicator variable of first and second flip showing heads respectively. Now, let $Z$ be the indicator variable that $X=Y$. Then, 
$$I(X;Y|Z)=H(X|Z)-\underbrace{ H(X|Y,Z)}_{ =0 }=H(X|Z)=1>0=I(X;Y) $$as $X{\bot} Y$.
However, $$I(X;Z|Y)=H(Z|Y)-H(Z|X,Y)=H(Z|Y)$$

---
##### Problem 5


---
##### Approach 1
We have that for each $i\leq r$ $$\begin{align}\frac{ \partial }{ \partial v_{i} } \left( \sum_{i=1}^{r}v_{i}^\top Av_{i} +\sum_{i,j}^{}\mu_{ij}(v_{i}^\top v_{j}-\delta_{ij})\right)&=2v_{i}^\top A+\sum_{j\neq i}^{}\mu_{ij}v_{j}^\top+\mu_{ii}2v_{i}^\top=0\end{align} $$Therefore, $2(A+\mu_{ii}I)v_{i}=-\sum_{j\neq i}^{}\mu_{ij}v_{j}$ and as $A+\mu_{ii}I=Q\Lambda Q^\top+\mu_{ii}QQ^\top=Q(\Lambda+\mu_{ii}I)Q^\top$. Hence, $$2(\Lambda+\mu_{ii}I)Q^\top v_{i}=-\sum_{j\neq i}^{}\mu_{ij}Q^\top v_{j}$$

---
Let $v_{1},\dots,v_{r}$ be orthonormal set of vectors. Then, $$\begin{align}\sum_{i=1}^{r}v_{i}^\top Av_{i}=\sum_{i=1}^{r}v_{i}^\top Q\Lambda \underbrace{ Q^\top v_{i} }_{ =:w_{i} }=\sum_{i=1}^{r}w_{i}^\top \Lambda w_{i}=\sum_{i=1}^{r}\sum_{j=1}^{n}\lambda_{j}(w_{i})_{j}^2=\sum_{j=1}^{n}\lambda_{j}\underbrace{ \sum_{i=1}^{r}(w_{i})_{j}^{2} }_{ x_{j} }=\sum_{j=1}^{n}\lambda_{j}\left\| W_{:, j} \right\|^2_{2} \end{align}$$where $W:=[w_{1}|\dots |w_{r}]^\top\in \mathbb{R}^{r,n}$ and hence $WW ^\top=I_{r}$.  Then, $$\max \sum_{i=1}^{r}v_{i}^\top Av_{i}=\max \sum_{j=1}^{r}\lambda_{j}\left\| W_{:, j} \right\| ^2_{2}$$$\max \sum_{i=1}^{r}v_{i}^\top Av_{i}=\max \sum_{j=1}^{r}\lambda_{j}x_{j}$ where 
$$x_{j}=\sum_{i=1}^{r}(W_{ij})^2$$

---
Let $V:=[v_{1}|\dots|v_{r}]\in \mathbb{R}^{n,r}$ and: $$\text{Tr}(V^\top A V)=\sum_{i=1}^{r}(V^\top AV)_{ii}=\sum_{i=1}^{r}v_{i}^\top A v_{i}$$
Then, we have that $\text{Tr}(V^\top AV) = \text{Tr}(V^\top V V^\top AV)=\text{Tr}(V V^\top A VV^\top)=\text{Tr}(WAW)$ where $W:=V V^\top\in \mathbb{R}^{n,n}$. Notice that $WAW$ is symmetric as $W$ and $A$ are. Hence, $\text{Tr}(WAW)$. Let $$

Therefore, $$\sum_{i=1}^{r}v_{i}^\top A v_{i}=\sum_{n=1}^{}$$

