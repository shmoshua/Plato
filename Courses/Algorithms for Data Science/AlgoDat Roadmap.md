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
#### 1.4 Sparse Linear Regression
We consider the case where from the $d$ features, only $k\ll d$ are relevant. If we know the $k$ features, then using minimax we can reach $\frac{k}{n}$ risk.

What do we do when the $k$ relevant features are unknown? 

---

> [!definition]
> Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ be known vectors. For an unknown $w_{0}\in \mathbb{R}^d$ we observe $y:=Xw_{0}+\varepsilon$ where $\varepsilon \sim \mathcal{N}(0,I_{n})$.
> 1. In ***sparse linear regression***, we aim to find $$w^{*}\in \underset{ w\in \mathbb{R}^d }{ \arg\min }\ \left\| y-Xw^0 \right\| ^2_{2}$$where $w^0$ is $k$-sparse, i.e. $\|w_{0}\|_{0}\leq k$.
---
##### 1.4.1 BSS

> [!lemma] Theorem 1 (Best-Subset-Selection)
> Let $\widehat{w}(w_{0})\in \underset{ w\in\mathbb{R}^d, k\text{-sparse} }{ \arg\min }\|y-Xw_{0}\|^2$. Then, 
> $$\frac{1}{n}\left\| X(\widehat{w}-w^0) \right\| ^{2}\leq \frac{k}{n}\cdot O\left( \log \frac{2d}{k} \right)\text{ whp}, \quad \forall w_{0}\in \mathbb{R}^n$$

> [!proof]-
> Define $f:\mathbb{R}^n\to \mathbb{R},w\mapsto \frac{1}{2n}\left\| Xw-y \right\|^{2}$. Then, $$\nabla f(w_{0})=\frac{1}{n}X^\top(Xw_{0}-y)=-\frac{1}{n}X^\top\varepsilon$$Let $u:=\widehat{w}-w_{0}$. Then, $$f(w_{0})\geq f(w_{0}+u)=f(w_{0})-\frac{1}{n}uX^\top\varepsilon+\frac{1}{2n}\left\| Xu \right\| ^2_{2}$$Hence, $$\left\| Xu \right\| ^2_{2}\leq 2\varepsilon^\top X u,\quad \left\| Xu \right\| ^2_{2}\leq \frac{4\braket{ \varepsilon , Xu } ^2}{\left\| Xu \right\| ^2_{2}}$$Notice that $u$ is $2k$-sparse as if $u_i\neq 0$ then either $\widehat{w}_{i}\neq 0$ or $w_{i}^0\neq 0$. Hence, it suffices to show w.h.p that: $$\max_{u\in \mathbb{R}^d, 2k\text{-sparse}}\frac{\braket{ \varepsilon , Xu } ^{2}}{\left\| Xu \right\| ^2}\leq k\cdot O\left( \log \frac{2d}{k} \right)$$
> Now, for all $S\in {[d] \choose 2k}$, let $\phi_{S}\in \mathbb{R}^{n,2k}$ have orthonormal columns s.t. the columns $X_{i}$ of $X$ for $i\in S$ are all spanned by the columns of $\phi_{S}$. 
> 
> Then, by choosing $S\supseteq \text{supp }u$, we have that $Xu\in \text{span}(\phi_{S,1}\dots,\phi_{S,2k})$ and there exists $v$ with $\|v\|=1$ s.t. $\frac{Xu}{\left\| Xu \right\|}=\phi_{S}v$. Hence, $$\max_{u\in \mathbb{R}^d, 2k\text{-sparse}}\frac{\braket{ \varepsilon , Xu } ^{2}}{\left\| Xu \right\| ^2}\leq \max_{S\in {[d] \choose 2k}}\max_{v\in \mathbb{R}^{2k},\|v\|=1}\braket{ \varepsilon , \phi_{S}v } ^2\leq \max_{S\in {[d] \choose 2k}}\left\| \phi_{S}^\top \varepsilon \right\| ^2$$
> Notice that by rotational invariance of the distribution of $\varepsilon$, we have that $\left\| \phi^\top_{S}\varepsilon \right\|^{2}$ has the same distribution as $\varepsilon^{2}_{1}+\dots+\varepsilon_{2k}^2\sim \chi^2_{2k}$. Hence,
> 
> Therefore, for any $t\geq 2$: $$\begin{align}\mathbb{P}\left(\max_{S}\left\| \phi_{S}^\top  \varepsilon\right\|^2> t \cdot 2k \right)&\leq \sum_{S}\mathbb{P}(\left\| \phi^\top_{S}\varepsilon \right\|^{2}> t\cdot 2k )\\&\leq {d \choose 2k}\mathbb{P}(\chi^2_{2k}> t 2k)\\&\leq \left( \frac{4d}{2k} \right)^{2k}e^{-tk/10}\\&\leq e^{2k\log (2d/k)-tk/10}\end{align}$$By taking $t=30\log \frac{2d}{k}$, we have that:$$\mathbb{P}\left(\max_{S}\left\| \phi_{S}^\top  \varepsilon\right\|^2> t \cdot 2k \right)\leq e^{-k\log (2d / k)}=\left( \frac{2d}{k} \right)^{-k}\leq 2^{-k}$$Since $t 2k\leq k \cdot O\left( \log \frac{2d}{k} \right)$, we have that the statement holds with probability at least $1-2^{-k}$

- **Remark**: However, BSS optimization problem is NP-hard in worst case!

---
##### 1.4.2 LASSO Slow Rate
> [!lemma] Theorem 2 (LASSO slow rate)
> Assume that $R:=\left\| w_{0} \right\|_{1}$ is known. Let $\widehat{w}(w_{0})\in \underset{ w \in \mathbb{R}^d,\|w\|_{1}\leq R }{ \arg\min }\left\| Xw_{0} -y\right\|^2$. 
> 1. If $\left\| X_{i} \right\|^2=n$ for all columns $X_{i}$, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^2]\leq \frac{\left\| w_{0} \right\| _{1}}{\sqrt{ n }}\cdot O(\log 2d)^{1/2}$$

> [!proof]-
> Let $u:= \widehat{w}-w_{0}$. Then, similarly to the Theorem 1, $$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top \varepsilon } \leq \|u\|_{1}\left\| X^\top\varepsilon \right\| _{\infty}$$However, notice that $\|u\|_{1}\leq\|\widehat{w}\|_{1}+\|w_{0}\|_{1}\leq 2\|w_{0}\|_{1}$ and: $$\mathbb{E}[\left\| X^\top\varepsilon \right\| _{\infty}]\leq \sqrt{ n }\cdot O(\log 2d)^{1/2}$$Therefore, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^{2}_{2}]\leq \frac{\left\| w_{0} \right\| _{1}}{\sqrt{ n }}O(\log 2d)^{1/2}$$

---
##### 1.4.2 LASSO Fast Rate
- **Related definition**: For $S\subseteq[d]$,  $C(S):=\{ u\in \mathbb{R}^d:\|u_{S}\|_{1}\geq \|u_{\overline{S}}\|_{1} \}$.
- **Related definition**: $X\in \mathbb{R}^{n,d}$ has ***restricted eigenvalue property*** with $\gamma>0$, i.e. ***$\gamma$-RE*** for $S\subseteq [d]$ if: $$\frac{1}{n}\left\| Xu \right\| ^2\geq\gamma \|u\|^2,\quad \forall u\in C(S)$$

---
> [!lemma] Lemma 3
> Let $w,w_{0}\in \mathbb{R}^d$.
> 1. if $\|w\|_{1}\leq \|w_{0}\|_{1}$, then $w-w_{0}\in C(\text{supp}(w_{0}))$.
> 2. for all $S\subseteq[d]$ and $v\in C(S)$, $\|v\|_{1}\leq 2\sqrt{ \left| S \right| }\cdot\|v\|_{2}$. 

> [!proof]-
> We have:
> 1. Let $S:=\text{supp}(w^0)$. Then, 
>    $$\left\| (w-w^0)_{\overline{S}} \right\| _{1}=\sum_{i\notin S}\left| w_{i}-w_{i}^0 \right| =\sum_{i\notin S}\left| w_{i} \right| =\|w_{\overline{S}}\|_{1}=\|w\|_{1}-\|w_{S}\|_{1}\leq \|w^0\|_{1}-\|w_{S}\|_{1}$$However, notice that $\|w^0\|_{1}=\|w^0_{S}\|_{1}$ by definition of $S$. Hence, $$\left\| (w-w^0)_{\overline{S}} \right\| _{1}\leq\|w^0_{S}\|_{1}-\|w_{S}\|_{1}\leq \|(w-w^0)_{S}\|_{1}$$by triangle inequality.
> 2. By Cauchy-Schwarz, we have that: $$\|v\|_{1}^{2}=(\|v_{S}\|_{1}+\|v_{\overline{S}}\|_{1})^2\leq 4\|v_{S}\|_{1}^{2}=4\left( \sum_{i\in S}^{} \left| v_{i} \right| \right)^{2}\leq 4\left| S \right| \left( \sum_{i\in S}^{}v_{i}^{2} \right)\leq 4\left| S \right| \|v\|_{2}^2$$
---


> [!lemma] Theorem 4 (LASSO fast rate)
> Assume that $R:=\left\| w^{*} \right\|_{1}$ is known. Let $\widehat{w}(w^{*})\in \underset{ w \in \mathbb{R}^d,\|w\|_{1}\leq R }{ \arg\min }\left\| Xw^{*} -y\right\|^2$. 
> 1. If $\left\| X_{i} \right\|^2=n$ for all columns $X_{i}$ and $X$ is $\gamma$-RE w.r.t. $\text{supp}(w^{*})$, then:$$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w^{*}) \right\| ^2]\leq \frac{k}{\gamma n}\cdot O(\log d)$$

> [!proof]-
> Let $u:= \widehat{w}-w_{0}$. Then, similarly to the Theorem 1, $$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top \varepsilon } \leq \|u\|_{1}\left\| X^\top\varepsilon \right\| _{\infty}$$Now, let $S:=\text{supp}(w^{*})$. From Lemma 3, $u\in C(S)$ and: $$\|u\|_{1}\leq 2\sqrt{ k }\|u\|_{2}\leq 2\sqrt{ \frac{k}{\gamma n} }\|Xu\|_{2}$$Hence, $$\left\| Xu \right\| ^2_{2}\leq 4\sqrt{ \frac{k}{\gamma n} }\|Xu\|_{2}\|X^\top\varepsilon\|_{\infty}$$ and $\|Xu\|^2_{2}\leq \frac{16k}{\gamma n}\|X^\top \varepsilon\|_{\infty}^2$. Using, $\mathbb{E}[\left\| X^\top\varepsilon \right\| _{\infty}]\leq \sqrt{ n }\cdot O(\log 2d)^{1/2}$ we get that, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^{2}_{2}]\leq \frac{k}{\gamma n}\cdot O(\log d)$$

---
##### 1.4.2.1 Sufficient Conditions for Restricted Eigenvalue Property
- **Related definition**: Let $X\in \mathbb{R}^{n,d}$ be a matrix s.t. $\left\| X_{1} \right\|^2=\dots=\left\| X_{d} \right\|^2=n$. Then, the ***pairwise incoherence*** of $X$ is defined as:$$\delta_{\text{PW}}(X):=\max_{i\neq j} \frac{1}{n}\left| \braket{ X_{i} ,  X_{j}}  \right| $$

---
> [!lemma] Theorem 5
> Let $X\in \mathbb{R}^{n,d}$ with $\left\| X_{1} \right\|^2=\dots=\left\| X_{d} \right\|^2=n$.
> 1. If $\delta_{\text{PW}}(X)\leq \frac{1}{8k}$, then $X$ is $\frac{1}{2}$-RE for every $S\subseteq [d]$ of size at most $k$.

> [!proof]-
> Let $S\subseteq [d]$ with size at most $k$ and $u\in C(S)$. Further, let $\delta:=\frac{1}{8k}$. We want to show that: $$\frac{1}{n}\left\| Xu \right\| ^{2}\geq \frac{1}{2}\|u\|^{2}$$We have that: $$\frac{1}{n}\left\| Xu \right\| ^{2}=\frac{1}{n}\sum_{i,j}\braket{ X_{i} , X_{j} } u_{i}u_{j}$$Then, $$\left| \sum_{i\neq j}^{} \frac{1}{n}\braket{ X_{i} , X_{j} } u_{i}u_{j} \right|\leq \sum_{i,j}^{}\left| u_{i} \right| \left| u_{j} \right| \delta= \delta\|u\|_{1}^2\leq 4k\delta\|u\|^2_{2}$$Hence, $$\frac{1}{n}\|Xu\|^2=\left( \sum_{i}^{} \frac{1}{n}\|X_{i}\|^2 u_{i}^2 \right)+\sum_{i\neq j}^{} \frac{1}{n}\braket{ X_{i} , X_{j} } u_{i}u_{j}\geq(1-4k\delta)\|u\|^2_{2}=\frac{1}{2}\|u\|^2_{2} $$
---
> [!h] Example 1
> Let $X$ be a Gaussian random matrix, i.e. $X_{1},\dots,X_{d}\sim \mathcal{N}(0,I_{n})$ i.i.d. for $d\geq n\geq 2$. Then, 
> 1. for $k=\Omega\left( \sqrt{ \frac{n}{\log d} } \right)$, w.h.p., $X$ is $\frac{1}{2}$-RE for all $S\subseteq [d]$ with $\left| S \right|\leq k$.

> [!proof]-
> We have that: $$\mathbb{E}[\braket{ X_{i} , X_{j} } ]=\begin{cases}n&i=j\\0&i\neq j\end{cases}$$Hence, we get that: $$\frac{\braket{ X_{i} , X_{j} } }{n}\leq \frac{1}{n}O(\sqrt{ n\log d })$$and $\delta_{\text{PW}}(X)\lesssim \sqrt{ \frac{\log d}{n} }$. The rest follows from Theorem 5.

---
### 2. Linear Regression with Oblivious Outliers
> [!outlook] Setup
> We have:
> 1. **Design**: $X\in \mathbb{R}^{n,d}$ with $\frac{1}{n}X^\top X=I_{d}$.
> 2. **Observation**: $y=X\beta ^{*}+\eta$ for unknown $\beta ^{*}\in \mathbb{R}^d$.
> 3. **Noise**: $\eta$ with $p(\eta)=p(-\eta)$ and $\eta_{1},\dots,\eta_{n}$ are independent.

---
> [!h] Example 1
> Let $w\sim \mathcal{N}(0,I_{n})$ and $Q\in \mathbb{R}^n$ arbitrary. Then, 
> $$\eta_{i}:=\begin{cases}w_{i}&\text{with probability }\alpha\\Q_{i}&\text{with probability } \frac{1}{2}(1-\alpha)\\-Q_{i}&\text{with probability } \frac{1}{2}(1-\alpha)\end{cases}$$

---
#### 2.1 Huber Loss Estimator
> [!definition] 
> Consider the setup as above and the Huber loss function: $$\Phi:\mathbb{R}\to \mathbb{R}_{\geq 0},\quad t\mapsto \begin{cases} \frac{1}{2}t^{2}&\left| t \right| \leq 2\\2\left| t \right| -2&\left| t \right| \geq 2\end{cases}$$and it's component-wise extension $\Phi:=\bigoplus_{i=1}^n\Phi:\mathbb{R}^n\to \mathbb{R}_{\geq 0}$. Then, 
> 1. the ***Huber loss estimator*** is given by: $$\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^d,\quad y\mapsto \underset{ \beta\in \mathbb{R}^d }{ \arg\min }\ \Phi(X\beta-y)$$

---
> [!lemma] Lemma 1
>  Let $R>0$. Let $f:\mathbb{R}^d\to \mathbb{R}$ be convex s.t. for $\kappa>0$:$$f(u)\geq f(0)-\left\| \nabla f(0) \right\| \cdot \|u\|+\kappa\|u\|^{2},\quad \forall u\in B_{\leq R}(0)$$
>  1. if $R\geq 2\left\| \nabla f(0) \right\| / \kappa$, then for $u^{*}\in \arg\min f$, $$\|u^{*}\|\leq \left\| \nabla f(0) \right\| / \kappa$$

> [!proof]-
> Let $v$ be an arbitrary unit vector. Then, for $0<\lambda\leq R$, $$f(\lambda v)\geq f(0)-\lambda\left\| \nabla f(0) \right\|+\lambda^{2}\kappa $$Now, let $\ell:\mathbb{R}\to \mathbb{R}$ be an affine function s.t. 
> 1. $\ell(0)=f(0)$ and 
> 2. $\ell(R)=f(Rv)$.
>  
>  As $f$ is convex, $f(\lambda v)\leq \ell(\lambda)$ for all $\lambda\in[0,R]$ and $f(\lambda v)\geq \ell(\lambda)$ for all $\lambda\notin [0,R]$. Now, $$\ell(R)=f(Rv)\geq f(0)-R\left\| \nabla f(0) \right\|+R^{2} \kappa> f(0)=\ell(0) $$Hence, $\ell$ is increasing and the minimum of $\ell$ is found in $[0,R]$. Therefore, this shows that: $$\left\| u^{*} \right\| \leq \left\| \nabla f(0) \right\|/ \kappa$$ 
---
> [!lemma] Theorem 1
> Let $\alpha:=\min_{i}\mathbb{P}(\eta_{i}\leq 1)$. Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ be the rows of $X$ and $C:=\frac{1}{\sqrt{ d }}\max_{i}\|x_{i}\|$. 
> 1. if $n= \Omega\left( \frac{d^{2}C^2}{\alpha^{2}} \right)$ then for the Huber loss estimator $\widehat{\beta}$ with probability $0.99$: $$\left\| \widehat{\beta}-\beta ^{*} \right\| ^{2}\leq O\left( \frac{d}{\alpha^{2}n} \right)$$

> [!proof]+
> We define: $$f:\mathbb{R}^d\to \mathbb{R},\quad \beta\mapsto \frac{1}{n}\sum_{i\in[n]}^{}\Phi(\braket{ x_{i} , \beta } -y_{i})$$Then, $\nabla f(\beta)=\frac{1}{n}\sum_{i\in[n]}^{}\Phi'(\braket{ x_{i} , \beta } -y_{i})x_{i}$ where: $$\Phi'(t)=\begin{cases}\text{sgn}(t)\cdot \left| t \right|&\left| t \right|\leq 2\\2\cdot  \text{sgn}(t)&\left| t \right|\geq 2\end{cases}=\text{sgn}(t)\cdot\min\{ \left| t \right|,2 \}, \quad \Phi''(t)=\mathbb{1}_{\{ \left| t \right| \leq 2 \}}$$
> 1. **Claim 1**: $f$
>    
> 2. **Claim 2**: for $R\geq 20 \|\nabla f(0)\| / \alpha$ and for all $u$ with $\|u\|\leq  R$, we have that: $$f(\beta ^{*}+u)\geq f(\beta ^{*})-\left\| \nabla f(\beta ^{*}) \right\|\cdot \|u\|+\frac{\alpha}{10}\|u\|^{2}$$
>    
>    From [[Taylor's Theorem|2nd order Hamadard Lemma]], $$f(\beta ^{*}+u)=f(\beta ^{*})+\braket{ \nabla f(\beta ^{*}) , u } +\underbrace{ u^\top \left( \int_{0}^{1} (1-t)\text{H}_{f}(\beta ^{*}+tu) \, dt  \right)u }_{ =: M(u) }  $$Now, we have that: $$\text{H}_{f}(\beta ^{*}+tu)=\frac{1}{n}\sum_{i\in[n]}^{}\Phi''(t\braket{ x_{i} ,u } -\eta_{i})x_{i}x_{i}^\top=\frac{1}{n}\sum_{i\in[n]}^{} \mathbb{1}_{\{ \left| t\braket{ x_{i} , u } -\eta_{i} \right| \leq 2 \}}x_{i}x_{i}^\top$$ and:$$\begin{align}M(u)&= \frac{1}{n}\sum_{i\in[n]}\left( \int_{0}^{1}  (1-t) \mathbb{1}_{\{ \left| t\braket{ x_{i} , u } -\eta_{i} \right| \leq 2 \}} \, dt \right)\braket{ x_{i} , u }^{2}\\&\geq \frac{1}{2n}\sum_{i\in[n]}\mathbb{1}_{\{ \left| \braket{ x_{i} , u } \right| \leq 1 \}}\mathbb{1_{\{ \left| \eta_{i}\right| \leq 1 \}}}\braket{ x_{i} , u }^{2}\\&\geq \mathbb{1}_{\{ \left| C\sqrt{ d }\cdot R\right| \leq 1  \}}\left( \frac{1}{2n}\sum_{i\in[n]}\mathbb{1_{\{ \left| \eta_{i}\right| \leq 1 \}}}\braket{ x_{i} , u }^{2} \right)\end{align}$$
>    
> 
> 
> Now, by seting $u:= \widehat{\beta}-\beta ^{*}$, we have $f(\beta ^{*})\geq f(\widehat{\beta})=f(\beta ^{*}+u)$ and further that: $$\left\| \widehat{\beta}-\beta ^{*} \right\| \leq \frac{10}{\alpha}\left\| \nabla f(\beta ^{*}) \right\| $$
> 
> $$\left\| \nabla f(\beta ^{*}) \right\|\cdot \|u\|\geq \frac{\alpha}{10}\|u\|^{2},\quad \frac{100}{\alpha^{2}} \left\| \nabla f(\beta ^{*}) \right\| ^{2}\geq \|u\|^{2} $$By noting that $\nabla f(\beta ^{*})=\frac{1}{n}\sum_{i\in[n]}^{}\Phi'(\eta_{i})x_{i}$ we have:$$\begin{align}\mathbb{E}[\left\| \nabla f(\beta ^{*}) \right\| ^{2}]=\frac{1}{n^{2}}\sum_{i\in [n]}^{}\|x_{i}\|^2\cdot \underbrace{ \mathbb{E}[\Phi'(\eta_{i})^{2}] }_{ \leq 4 }+\frac{1}{n^{2}}\sum_{i\neq j}^{}\braket{ x_{i} , x_{j} } \underbrace{ \mathbb{E}[\Phi'(\eta_{i})\Phi'(\eta_{j})] }_{ =0 }\leq \frac{4}{n^{2}}dn=\frac{4d}{n}\end{align}$$
> 
> Therefore, $$\mathbb{P}\left( \left\| \widehat{\beta}- \beta ^{*}\right\| ^{2}\geq \frac{40000 d}{\alpha^{2}n}\right)\leq  \frac{\mathbb{E}\left[ \left\| \widehat{\beta}- \beta ^{*}\right\| ^{2} \right] }{40000d / \alpha^{2}n}\leq \frac{\mathbb{E}\left[ \left\| \nabla f(\beta ^{*}) \right\| ^{2} \right] }{400d / n}\leq0.01$$
> This proves the statement.

$$f$$