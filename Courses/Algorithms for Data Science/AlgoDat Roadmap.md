#Roadmap #Algorithms 

### 1. Linear Regression
![[Linear Regression#^e4d197]]

---
#### 1.1 Least-Squares Estimator

> [!lemma] Proposition 1
> For the least squares solution $w^{*}$ we have that: $$\mathbb{E}[\|w_{0}-w^{*}\|^{2}]=\sigma^{2} \cdot  \frac{d}{n}$$

> [!proof]-
> Let $X=[x_{1}|\dots|x_{n}]^\top\in \mathbb{R}^{n,d}$. By orthogonalizing the data and scaling, we may assume that $\frac{1}{n}X^\top X=I_{d}$ and $y=Xw_{0}+\varepsilon$. Then,
> 
> Notice that: $$\nabla_{w }\|Xw-y\|^{2}=2X^\top(Xw-Xw_{0}-\varepsilon)=2n(w-w_{0})-2X^\top \varepsilon$$Hence, from the optimality of $w^{*}$, we get that $w^{*}-w_{0}=\frac{1}{n}X^\top \varepsilon$ and: $$\|w^{*}-w_{0}\|^{2}=\frac{1}{n^{2}}\text{tr}(X^\top\varepsilon \varepsilon^\top X)$$Therefore, 
> 
 $$\begin{align} \mathbb{E}[\left\| w^{*}-w_{0} \right\| ^{2}]=\frac{1}{n^{2}}\text{tr}(XX^\top \mathbb{E}[\varepsilon \varepsilon^\top])=\frac{\sigma^{2}}{n^{2}}\text{tr}(XX^\top)=\frac{\sigma^{2}}{n}\text{tr}\left( \frac{1}{n}X^\top X \right)=\sigma^{2} \cdot  \frac{d}{n}\end{align}$$

---
- **Related definition**: Let $\widehat{w}:\mathbb{R}^n\to \mathbb{R}^d$ be an estimator of $w_{0}$ based on the observation $y$. Then, the ***risk*** is defined as:$$\text{R}(\widehat{w};w_{0}):=\mathbb{E}[\left\| \widehat{w}(Xw_{0}+\varepsilon)-w_{0} \right\|^{2} ]$$
- **Remark**: We showed that $\text{R}(\widehat{w}_{\text{LS}};w_{0})=\sigma^{2} \frac{d}{n}$
---
#### 1.2 Bayes-Optimal Estimator
> [!definition] 
> For linear regression problem, 
> 1. the ***Bayes optimal estimator*** for a distribution $P\in \Delta(\mathbb{R}^d)$ with $w\sim P$ is defined as: $$\widehat{w}_{P}:\mathbb{R}^n\to \mathbb{R}^d,\quad y\mapsto \mathbb{E}_{P}[w|Xw+\varepsilon=y]$$
---
> [!lemma] Theorem 1 (Bayes-Optimal Estimator is optimal)
> Let $P\in \Delta(\mathbb{R}^d)$ with $w\sim P$. For any estimator $\widehat{w}:\mathbb{R}^n\to \mathbb{R}^d$, 
> $$\mathbb{E}_{w}[\text{R}(\widehat{w};w)]\geq \mathbb{E}_{w}[\text{R}(\widehat{w}_{P};w)]$$

> [!proof]-
> Let $\widehat{w}$ be some estimator. We further define $y:=Xw+\varepsilon$ and $\widehat{w}:=\widehat{w}(y)$. Then, $$\begin{align}\mathbb{E}_{w}[\text{R}(\widehat{w}_{P};w)]&=\mathbb{E}_{w}[\mathbb{E}_{\varepsilon}[\left\| \widehat{w}_{P}(y)-w \right\| ^{2}]]=\mathbb{E}_{\varepsilon}[\mathbb{E}_{w}[\left\| \mathbb{E}[w|y]-w \right\| ^{2}]]\end{align}$$Let us define the random variables: $$A:(w,\varepsilon)\mapsto \widehat{w}-\mathbb{E}[w|y],\quad B:(w,\varepsilon)\mapsto \mathbb{E}[w|y]-w$$
> Then, by [[Product Measure|Fubini-Tonelli]]:$$\begin{align}\mathbb{E}_{w}[\text{R}(\widehat{w};w)]&=\mathbb{E}_{w}[\mathbb{E}_{\varepsilon}[\left\| \widehat{w}-w \right\| ^{2}]]=\mathbb{E}_{\varepsilon}[\mathbb{E}_{w}[\left\| A+B \right\| ^{2}]]\\&=\mathbb{E}_{\varepsilon}[\underbrace{ \mathbb{E}_{w}[\left\| A \right\| ^{2}] }_{ \geq 0 }+\mathbb{E}_{w}[\|B\|^{2}]+2\mathbb{E}_{w}[\braket{ A , B } ]]\\&\geq \mathbb{E}_{\varepsilon}\mathbb{E}_{w}[\|B\|^{2}]+2\mathbb{E}_{\varepsilon}\mathbb{E}_{w}[\braket{ A , B } ]\\&\geq \mathbb{E}_{w}[\text{R}(\widehat{w}_{P};w)]+2\mathbb{E}_{\varepsilon}\mathbb{E}_{w}[\braket{ A , B } ]\end{align}$$However, we have that: $$\mathbb{E}_{w}[\braket{ A , B}|y]=\braket{ a ,\mathbb{E}_{w}[B|y]  }=\braket{ a , \mathbb{E}_{w}[\mathbb{E}[w|y]-w|y] }  =\braket{ a , \mathbb{E}[w|y]-\mathbb{E}[w|y] }=\braket{ a , 0 } =0 $$Hence, $$\mathbb{E}_{w}[\braket{ A , B } ]=\mathbb{E}_{w}[\mathbb{E}_{w}[\braket{ A , B } |y]]=0$$and we have the statement.

---
#### 1.3 Minimax Optimality

> [!lemma] Theorem 2 (Every Estimator has some Risk)
> Let $\widehat{w}:\mathbb{R}^n\to \mathbb{R}^d$ be an estimator and $\sigma^{2}=1$. Then, 
> $$\sup_{w_{0}\in \mathbb{R}^d}\text{R}(\widehat{w};w_{0})\geq \frac{d}{n}$$

> [!proof]-
> Fix an estimator $\widehat{w}:\mathbb{R}^n\to \mathbb{R}^d$ and $t\geq 1$. We will show that: $$\mathbb{E}_{w\sim \mathcal{N}(0,t\cdot I_{d})}[\text{R}(\widehat{w};w)]\geq  \frac{d}{n+1/ t}$$If this holds, then we have $\sup_{w}\text{R}(\widehat{w};w)\geq \frac{d}{n+1 / t}$ for all $t\geq 1$ and $\sup_{w}\text{R}(\widehat{w};w)\geq \frac{d}{n}$. 
> 
> ---
> First assume that $X=(\sqrt{ n }I_{d},0)$, i.e. $y_{i}=\sqrt{ n }w_{i}+\varepsilon_{i}$ for all $i\in [d]$. We show that there exists $\alpha\in \mathbb{R}$ s.t. $z_{i}:=w_{i}-\alpha y_{i}$ is independent to $y_{i}$ for all $i\in[d]$.
> 
> As $w,\varepsilon$ are jointly Gaussian, we have that so are $y_{i},z_{i}$ for all $i\in[d]$. Hence, to show that they are independent we need that $y_{i},z_{i}$ are uncorrelated i.e. $\mathbb{E}[y_{i}z_{i}]=\mathbb{E}[y_{i}]\mathbb{E}[z_{i}]=0$. Notice that $z_{i}=w_{i}-\alpha(\sqrt{ n }w_{i}+\varepsilon_{i})=(1-\alpha\sqrt{ n })w_{i}-\alpha\varepsilon_{i}$. Therefore, $y_{i},z_{i}$ are uncorrelated if and only if: $$\begin{align}0&=\mathbb{E}[y_{i}z_{i}]=\sqrt{ n }(1-\alpha \sqrt{ n })\mathbb{E}[w_{i}^{2}]-\alpha \mathbb{E}[\varepsilon_{i}^{2}]=t\sqrt{ n }(1-\alpha \sqrt{ n })-\alpha\\\alpha&=t\sqrt{ n }(1-\alpha \sqrt{ n })\\(1+tn)\alpha&=t\sqrt{ n }\\\alpha&=\frac{\sqrt{ n }}{n+1 /t}\end{align}$$
> 
> By setting $z:=z_{1:d}\in \mathbb{R}^d$, we have that: $$\begin{align}\mathbb{E}[z]=(1-\alpha \sqrt{ n })\underbrace{ \mathbb{E}[w] }_{ =0 }-\alpha \underbrace{ \mathbb{E}[\varepsilon_{1:d}] }_{ =0 }=0\end{align}$$and $\mathbb{E}[zz^\top]=(1-\alpha \sqrt{ n })^{2}t\cdot I_{d}+\alpha^{2} I_{d}$.
> 
> Therefore, we have that $z|y=z\sim \mathcal{N}(0,\mathbb{E}[zz^\top])$ as $z \bot y$. Hence, $$w|y=z+\alpha y_{1:d}|y\sim \mathcal{N}(\alpha y_{1:d}, \mathbb{E}[zz^\top])=\mathcal{N}\left( \frac{1}{n+1/t}X^\top y, \frac{1}{n+1 / t}I_{d} \right)$$
> 
> ---
> Now, assume that $X$ is general. Then, there exists $U$ orthogonal s.t. $$X':=(\sqrt{ n }I_{d},0)=UX$$Then, $$(w|Xw+\varepsilon=y)=(w|X'w+U\varepsilon=Uy)\sim\mathcal{N}\left( \frac{1}{n+1/t} X^\top \underbrace{ U^\top U }_{ =I }y, \frac{1}{n+ 1 / t}I_{d}\right) $$
> 
> ---
> Therefore, we have that $w|y\sim \mathcal{N}\left( \frac{1}{n+ 1 / t}X^\top y, \frac{1}{n+ 1 / t}I_{d} \right)$ and from Bayes-Optimal estimator:$$\begin{align}\mathbb{E}_{w}[\text{R}(\widehat{w};w)]&\geq \mathbb{E}_{w}[\text{R}(\widehat{w}_{P};w)]\\&=\mathbb{E}_{(w,\varepsilon)}[\left\| \widehat{w}_{P} -w\right\|^{2} ]\\&=\mathbb{E}_{(w,\varepsilon)}[\mathbb{E}[\left\| \widehat{w}_{P} -w\right\|^{2}|y] ]\\&=\mathbb{E}_{(w,\varepsilon)}\left[ \sum_{i=1}^{d}\text{Var}(w_{i}|y)  \right]\\&=\mathbb{E}_{(w,\varepsilon)}\left( \frac{d}{n+ 1 / t} \right) \\&=\frac{d}{n+1 / t}\end{align}$$

---
#### 1.4 Sparsity and Regression
We consider the case where from the $d$ features, only $k\ll d$ are relevant. If we know the $k$ features, then using minimax we can reach $\frac{k}{n}$ risk.

What do we do when the $k$ relevant features are unknown? 

---
##### 1.4.1 Sparse Linear Regression
> [!definition]
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ be known vectors. For an unknown $w_{0}\in \mathbb{R}^d$ we observe $y:=Xw_{0}+\varepsilon$ where $\varepsilon \sim \mathcal{N}(0,I_{n})$.
> 1. In ***sparse linear regression***, we aim to find $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\ \left\| Xw-y \right\| ^2_{2}$$where $w$ is $k$-sparse, i.e. $\|w_{0}\|_{0}\leq k$.

---
> [!lemma] Theorem 1 (Best-Subset-Selection)
> Let $\widehat{\beta}\in \underset{ \beta\in\mathbb{R}^d, k\text{-sparse} }{ \arg\min }$