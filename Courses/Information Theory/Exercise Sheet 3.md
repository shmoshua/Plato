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
