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

> [!proof]+
> Fix an estimator $\widehat{w}:\mathbb{R}^n\to \mathbb{R}^d$ and $t\geq 1$. We will show that: $$\mathbb{E}_{w\sim \mathcal{N}(0,t\cdot I_{d})}[\text{R}(\widehat{w};w)]\geq  \frac{d}{n+1/ t}$$If this holds, then we have $\sup_{w}\text{R}(\widehat{w};w)\geq \frac{d}{n+1 / t}$ for all $t\geq 1$ and $\sup_{w}\text{R}(\widehat{w};w)\geq \frac{d}{n}$. 
> 
> 