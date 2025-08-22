#Roadmap #Algorithms 

### 1. Linear Regression

> [!outlook] Setting (Linear Regression)
> We have the setting:
> 1. **Unknown data**: $\beta^0\in \mathbb{R}^d$.
> 2. **Known data**: 
> 	- $X\in \mathbb{R}^{n,d}$ with $\text{rnk}(X)=d$ and $\frac{1}{n}X^\top X=I_{d}$
> 	- $y:= X\beta^0+w$ where $w\sim \mathcal{N}(0,\sigma^{2}I_{n})$. 

---

##### 1.1.1 Least-Squares Estimator

> [!lemma] Proposition 1
> For the least squares solution $\widehat{\beta}:=\underset{ \beta\in \mathbb{R}^d }{ \arg\max }\left\| X\beta-y \right\|^{2}_{2}$ we have that: $$\mathbb{E}[\|\beta^0-\widehat{\beta}\|^{2}]=\sigma^{2} \cdot  \frac{d}{n}$$

> [!proof]-
> 
> Notice that: $$\nabla_{\beta}\|X\beta-y\|^{2}=2((X\beta-y)^\top X)^\top=2X^\top(X\beta-X\beta^0-w)=2n(\beta-\beta^0)-2X^\top w$$Hence, from the optimality of $\widehat{w}$, we get that $\widehat{\beta}-\beta ^0=\frac{1}{n}X^\top w$ and: $$\|\widehat{\beta}-\beta^0\|^{2}=\frac{1}{n^{2}}w^\top X X^\top w$$Therefore, 
> 
 $$\begin{align} \mathbb{E}[\left\|\widehat{\beta}- \beta^0 \right\| ^{2}]=\frac{1}{n^{2}}\text{tr}(XX^\top \mathbb{E}[ww^\top])=\frac{\sigma^{2}}{n^{2}}\text{tr}(XX^\top)=\frac{\sigma^{2}}{n}\text{tr}\left( \frac{1}{n}X^\top X \right)=\sigma^{2} \cdot  \frac{d}{n}\end{align}$$

---
- **Related definition**: Let $\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^d,y\mapsto \widehat{\beta}(y)$ be an estimator of $\beta^0$. Then, 
	1. the ***risk*** is defined as:$$\text{R}(\widehat{\beta};\beta^0):=\mathbb{E}_{w}\left[ \left\| \widehat{\beta}(X\beta^0+w)-\beta^0 \right\|^{2}  \right] $$
- **Remark**: We showed that $\text{R}(\widehat{\beta}_{\text{LS}};\beta^0)=\sigma^{2} \frac{d}{n}$
---
##### 1.1.2 Bayes-Optimal Estimator
> [!definition] 
> For linear regression problem, 
> 1. the ***Bayes optimal estimator*** for a distribution $P\in \Delta(\mathbb{R}^d)$ with $\beta^0\sim P$ is defined as: $$\widehat{\beta}_{P}:= \mathbb{E}[\beta^0|X\beta^0+w]$$More specifically,$$\widehat{\beta}_{P}:\mathbb{R}^n\to \mathbb{R}^d,\quad y\mapsto \mathbb{E}[\beta^0|X\beta^0+w=y]$$
---
> [!lemma] Theorem 1 (Bayes-Optimal Estimator is optimal)
> Let $P\in \Delta(\mathbb{R}^d)$ with $\beta^0\sim P$. For any estimator $\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^d$, 
> $$\mathbb{E}_{P}[\text{R}(\widehat{\beta};\beta^0)]\geq \mathbb{E}_{P}[\text{R}(\widehat{\beta}_{P};\beta^0)]$$

> [!proof]-
> Let $\widehat{\beta}$ be some estimator. For $\beta^0\sim P$, we further define $y:=X\beta^0+w$ and $\widehat{\beta}:=\widehat{\beta}(y)$. Then, $$\begin{align}\mathbb{E}_{P}[\text{R}(\widehat{\beta}_{P};\beta^0)]&=\mathbb{E}_{P}\mathbb{E}_{w}\left[ \left\| \widehat{\beta}_{P}(y)-\beta^0 \right\| ^{2} \right]=\mathbb{E}_{P}\mathbb{E}_{w}\left[ \left\| \mathbb{E}[\beta|X\beta+\varepsilon=y]-\beta^0 \right\| ^{2} \right] \end{align}$$Let us define the random variables: $$A:(\beta^0,w)\mapsto \widehat{\beta}(y)-\widehat{\beta}_{P}(y),\quad B:(\beta^0,w)\mapsto \widehat{\beta}_{P}(y)-\beta^0$$
> Then, by [[Product Measure|Fubini-Tonelli]]:$$\begin{align}\mathbb{E}_{P}[\text{R}(\widehat{\beta};\beta^0)]&=\mathbb{E}_{P}\mathbb{E}_{w}\left[ \left\| \widehat{\beta}(y)-\beta^0 \right\| ^{2} \right] =\mathbb{E}_{w}\mathbb{E}_{P}\left[ \left\| A+B \right\| ^{2} \right] \\&=\mathbb{E}_{w}\underbrace{ \mathbb{E}_{P}[\left\| A \right\| ^{2}] }_{ \geq 0 }+\mathbb{E}_{w}\mathbb{E}_{P}[\|B\|^{2}]+2\mathbb{E}_{w}\mathbb{E}_{P}[\braket{ A , B } ]\\&\geq \mathbb{E}_{w}\mathbb{E}_{P}[\|B\|^{2}]+2\mathbb{E}_{w}\mathbb{E}_{P}[\braket{ A , B } ]\\&\geq \mathbb{E}_{P}[\text{R}(\widehat{\beta}_{P};\beta^0)]+2\mathbb{E}_{w}\mathbb{E}_{P}[\braket{ A , B } ]\end{align}$$However, we have that for a fixed $\varepsilon$:$$\mathbb{E}[\braket{ A , B}|y]=\braket{ A ,\mathbb{E}[B|y]  }=\braket{ A, \mathbb{E}[\mathbb{E}[w|y]-w|y] }  =\braket{ A , \mathbb{E}[w|y]-\mathbb{E}[w|y] }=\braket{ A , 0 } =0 $$Hence, $$\mathbb{E}_{P}[\braket{ A , B } ]=\mathbb{E}_{P}[\mathbb{E}[\braket{ A , B } |y]]=0$$and we have the statement.

---
##### 1.1.3 Minimax Optimality

> [!lemma] Theorem 2 (Every Estimator has some Risk)
> Let $\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^d$ be an estimator and $\sigma^{2}=1$. Then, 
> $$\sup_{\beta^0\in \mathbb{R}^d}\text{R}(\widehat{\beta};\beta^0)\geq \frac{d}{n}$$

> [!proof]-
> Fix an estimator $\widehat{\beta}:\mathbb{R}^n\to \mathbb{R}^d$ and $t\geq 1$. We will show that: $$\mathbb{E}_{\beta^0\sim \mathcal{N}(0,t\cdot I_{d})}[\text{R}(\widehat{\beta};\beta^0)]\geq  \frac{d}{n+1/ t}$$If this holds, then we have $\sup_{\beta^0}\text{R}(\widehat{\beta};\beta^0)\geq \frac{d}{n+1 / t}$ for all $t\geq 1$ and $\sup_{\beta}\text{R}(\widehat{\beta};\beta^0)\geq \frac{d}{n}$. 
> 
> ---
> First assume that $X=[\sqrt{ n }I_{d}|0]^\top$, i.e. $y_{i}=\sqrt{ n }\beta^0_{i}+w_{i}$ for all $i\in [d]$. We show that there exists $\alpha\in \mathbb{R}$ s.t. $z_{i}:=\beta^0_{i}-\alpha y_{i}$ is independent to $y_{i}$ for all $i\in[d]$.
> 
> As $\beta^0,w$ are jointly Gaussian, we have that so are $\beta^0_{i},w_{i}$ for all $i\in[d]$. Hence, to show that they are independent we need that $y_{i},z_{i}$ are uncorrelated i.e. $\mathbb{E}[y_{i}z_{i}]=\mathbb{E}[y_{i}]\mathbb{E}[z_{i}]=0$. Notice that $z_{i}=\beta^0_{i}-\alpha(\sqrt{ n }\beta^0_{i}+w_{i})=(1-\alpha\sqrt{ n })\beta^0_{i}-\alpha w_{i}$. Therefore, $y_{i},z_{i}$ are uncorrelated if and only if: $$\begin{align}0&=\mathbb{E}[y_{i}z_{i}]=\sqrt{ n }(1-\alpha \sqrt{ n })\mathbb{E}[(\beta^0_{i})^{2}]-\alpha \mathbb{E}[w_{i}^{2}]=t\sqrt{ n }(1-\alpha \sqrt{ n })-\alpha\\\alpha&=t\sqrt{ n }(1-\alpha \sqrt{ n })\\(1+tn)\alpha&=t\sqrt{ n }\\\alpha&=\frac{\sqrt{ n }}{n+1 /t}\end{align}$$
> 
> By setting $z:=z_{1:d}\in \mathbb{R}^d$, we have that: $$\begin{align}\mathbb{E}[z]=(1-\alpha \sqrt{ n })\underbrace{ \mathbb{E}[\beta^0] }_{ =0 }-\alpha \underbrace{ \mathbb{E}[w_{1:d}] }_{ =0 }=0\end{align}$$and $\mathbb{E}[zz^\top]=(1-\alpha \sqrt{ n })^{2}t\cdot I_{d}+\alpha^{2} I_{d}$.
> 
> Therefore, we have that $z|y=z\sim \mathcal{N}(0,\mathbb{E}[zz^\top])$ as $z \bot y$. Hence, $$\beta^0|y=z+\alpha y_{1:d}|y\sim \mathcal{N}(\alpha y_{1:d}, \mathbb{E}[zz^\top])=\mathcal{N}\left( \frac{1}{n+1/t}X^\top y, \frac{1}{n+1 / t}I_{d} \right)$$
> 
> ---
> Now, assume that $X$ is general. Then, there exists $U$ orthogonal s.t. $$X':=(\sqrt{ n }I_{d},0)=UX$$Then, $$(\beta^0|X\beta^0+w=y)=(\beta^0|X'\beta^0+Uw=Uy)\sim\mathcal{N}\left( \frac{1}{n+1/t} X^\top \underbrace{ U^\top U }_{ =I }y, \frac{1}{n+ 1 / t}I_{d}\right) $$
> 
> ---
> Therefore, we have that $\beta^0|y\sim \mathcal{N}\left( \frac{1}{n+ 1 / t}X^\top y, \frac{1}{n+ 1 / t}I_{d} \right)$ and from Bayes-Optimal estimator:$$\begin{align}\mathbb{E}_{\beta^0}[\text{R}(\widehat{\beta};\beta^0)]&\geq \mathbb{E}_{\beta^0}[\text{R}(\widehat{\beta}_{P};\beta^0)]\\&=\mathbb{E}_{(\beta^0,w)}[\left\| \widehat{\beta}_{P} -\beta^0\right\|^{2} ]\\&=\mathbb{E}_{(\beta^0,w)}[\mathbb{E}[\left\| \widehat{\beta}_{P} -\beta\right\|^{2}|y] ]\\&=\mathbb{E}_{(w,\varepsilon)}\left[ \sum_{i=1}^{d}\text{Var}(\beta_{i}^0|y_{i})  \right]\\&=\mathbb{E}_{(w,\varepsilon)}\left( \frac{d}{n+ 1 / t} \right) \\&=\frac{d}{n+1 / t}\end{align}$$

---
#### 1.2.1 Sparse Linear Regression
We consider the case where from the $d$ features, only $k\ll d$ are relevant. If we know the $k$ features, then using minimax we can reach $\frac{k}{n}$ risk.

What do we do when the $k$ relevant features are unknown? 

---

> [!outlook] Setting (Sparse Linear Regression)
> We have the setting:
> 1. **Unknown data**: $\beta^0\in \mathbb{R}^d$ which is $k$-sparse, i.e. $\left\| \beta^0 \right\|_{0}\leq k$.
> 2. **Known data**: 
> 	- $X\in \mathbb{R}^{n,d}$ with $\text{rnk}(X)=d$ and $\frac{1}{n}X^\top X=I_{d}$
> 	- $y:= X\beta^0+w$ where $w\sim \mathcal{N}(0,I_{n})$. 

---
##### 1.4.1 BSS

> [!lemma] Theorem 1 (Best-Subset-Selection)
> The ***BSS-estimator*** is $\widehat{\beta}(y)\in \underset{ \beta\in\mathbb{R}^d, k\text{-sparse} }{ \arg\min }\|X\beta-y\|^2$. Then, with high probability, 
> $$\frac{1}{n}\left\| X(\widehat{\beta}-\beta^0) \right\| ^{2}\leq \frac{k}{n}\cdot O\left( \log \frac{2d}{k} \right), \quad \forall \beta^0\in B_{\leq k}(0)_{\|\cdot \|_{0}}$$

> [!proof]-
> Define $f:\mathbb{R}^n\to \mathbb{R},\beta\mapsto \frac{1}{2n}\left\| X\beta-y \right\|^{2}$. Then, $$\nabla f(\beta^0)=\frac{1}{n}X^\top(X\beta^0-y)=-\frac{1}{n}X^\top w$$Let $u:=\widehat{\beta}-\beta^0$. Then, $$f(\beta^0)\geq f(\beta^0+u)=f(\beta^0)-\frac{1}{n}u^\top X^\top w+\frac{1}{2n}\left\| Xu \right\| ^2_{2}$$Hence, $$\left\| Xu \right\| ^2_{2}\leq 2w^\top X u,\quad \left\| Xu \right\| ^2_{2}\leq \frac{4\braket{ w , Xu } ^2}{\left\| Xu \right\| ^2_{2}}$$Notice that $u$ is $2k$-sparse by triangle identity. Hence, it suffices to show w.h.p that: $$\max_{u\in \mathbb{R}^d, 2k\text{-sparse}}\frac{\braket{ w , Xu } ^{2}}{\left\| Xu \right\| ^2}\leq k\cdot O\left( \log \frac{2d}{k} \right)$$
> Now, for all $S\in {[d] \choose 2k}$, let $\phi_{S}\in \mathbb{R}^{n,2k}$ have orthonormal columns s.t. the columns $X_{i}$ of $X$ for $i\in S$ are all spanned by the columns of $\phi_{S}$. 
> 
> Then, by choosing $S\supseteq \text{supp }u$, we have that $Xu\in \text{span}(\phi_{S,1}\dots,\phi_{S,2k})$ and there exists $v$ with $\|v\|=1$ s.t. $\frac{Xu}{\left\| Xu \right\|}=\phi_{S}v$. Hence, $$\max_{u\in \mathbb{R}^d, 2k\text{-sparse}}\frac{\braket{ w , Xu } ^{2}}{\left\| Xu \right\| ^2}\leq \max_{S\in {[d] \choose 2k}}\max_{v\in \mathbb{R}^{2k},\|v\|=1}\braket{ w , \phi_{S}v } ^2\leq \max_{S\in {[d] \choose 2k}}\left\| \phi_{S}^\top w \right\| ^2$$Now, we have that for any $S\in {[d] \choose 2k}$, $\phi^\top_{S}w\sim \mathcal{N}(0,\phi^\top_{S}\phi_{S}=I_{2k})$ and $\|\phi^\top_{S}w\|^{2}\sim \chi^{2}_{2k}$. 
> 
> Therefore, for any $t\geq 2$: $$\begin{align}\mathbb{P}\left(\max_{S}\left\| \phi_{S}^\top  \varepsilon\right\|^2> t \cdot 2k \right)&\leq \sum_{S}\mathbb{P}(\left\| \phi^\top_{S}\varepsilon \right\|^{2}> t\cdot 2k )\\&\leq {d \choose 2k}\mathbb{P}(\chi^2_{2k}> t 2k)\\&\leq \left( \frac{4d}{2k} \right)^{2k}e^{-tk/10}\\&\leq e^{2k\log (2d/k)-tk/10}\end{align}$$By taking $t=30\log \frac{2d}{k}$, we have that:$$\mathbb{P}\left(\max_{S}\left\| \phi_{S}^\top  \varepsilon\right\|^2> t \cdot 2k \right)\leq e^{-k\log (2d / k)}=\left( \frac{2d}{k} \right)^{-k}\leq 2^{-k}$$Since $t 2k\leq k \cdot O\left( \log \frac{2d}{k} \right)$, we have that the statement holds with probability at least $1-2^{-k}$

- **Remark**: However, BSS optimization problem is NP-hard in worst case!

---
##### 1.4.2 LASSO Slow Rate
> [!lemma] Theorem 2 (LASSO slow rate)
> Assume that $R:=\left\| \beta^0 \right\|_{1}$ is known. Let $\widehat{\beta}(y)\in \underset{ \beta \in \mathbb{R}^d,\|\beta\|_{1}\leq R }{ \arg\min }\left\| X\beta -y\right\|^2$. 
> 1. If $\left\| X_{i} \right\|^2=n$ for all columns $X_{i}$, $$\mathbb{E}\left[ \frac{1}{n}\left\| X(\widehat{\beta}-\beta^0) \right\| ^2 \right] \leq \frac{R}{\sqrt{ n }}\cdot O(\log d)^{1/2}$$

> [!proof]-
> Let $u:= \widehat{\beta}-\beta^0$. Then, similarly to the Theorem 1, $$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top w } \leq \|u\|_{1}\left\| X^\top w \right\| _{\infty}$$However, notice that $\|u\|_{1}\leq\|\widehat{\beta}\|_{1}+\|\beta^0\|_{1}\leq 2R$ and: $$\mathbb{E}\left[ \left\| X^\top w \right\| _{\infty} \right] =\mathbb{E}\left[ \max_{i\in[d]} \left| \braket{ X_{i} , w }  \right|  \right] \leq \sqrt{ n }\cdot O(\log 2d)^{1/2}$$as $\braket{ X_{i},w }\sim \mathcal{N}(0,\underbrace{ X_{i}^\top X_{i} }_{ =n })$. To show the last inequality: 
> 1. As $x\mapsto x^{2}$ is convex, by Jensen:$$\left( \mathbb{E}\left[ \frac{1}{\sqrt{ n }}\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \right)^{2}\leq \mathbb{E}\left[ \frac{1}{n}\max_{i\in[d]}\braket{ X_{i} , w }   ^{2} \right]=\mathbb{E}\left[ \max_{i\in[d]}\left\langle \frac{1}{\sqrt{ n }}X_{i},w\right\rangle^{2} \right]$$where$\braket{ \frac{1}{\sqrt{ n }}X_{i} ,  w}\sim \mathcal{N}(0,1)$. Hence, by [[Concentration Bounds|maximum of squares]], we get that: $\left( \mathbb{E}\left[ \frac{1}{\sqrt{ n }}\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \right)^{2}\leq O(\log d)$. Finally, $$\mathbb{E}\left[\max_{i\in[d]}\left| \braket{ X_{i} , w }  \right|  \right]  \leq \sqrt{ n }\cdot O(\log d)^{1/2}$$
> 
> Therefore, $$\frac{1}{n}\mathbb{E}[\left\| X(\widehat{w}-w_{0}) \right\| ^{2}_{2}]\leq \frac{R}{\sqrt{ n }}O(\log d)^{1/2}$$

---
##### 1.4.2 LASSO Fast Rate
- **Related definition**: For $S\subseteq[d]$,  $C(S):=\{ u\in \mathbb{R}^d:\|u_{S}\|_{1}\geq \|u_{\overline{S}}\|_{1} \}$.
- **Related definition**: $X\in \mathbb{R}^{n,d}$ has ***restricted eigenvalue property*** with $\gamma>0$, i.e. ***$\gamma$-RE*** for $S\subseteq [d]$ if: $$\frac{1}{n}\left\| Xu \right\| ^2_{2}\geq\gamma \|u\|^2_{2},\quad \forall u\in C(S)$$

---
> [!lemma] Lemma 3
> Let $\beta,\beta^0\in \mathbb{R}^d$.
> 1. if $\|\beta\|_{1}\leq \|\beta^0\|_{1}$, then $\beta-\beta^0\in C(\text{supp}(\beta^0))$.
> 2. for all $S\subseteq[d]$ and $v\in C(S)$, $\|v\|_{1}\leq 2\sqrt{ \left| S \right| }\cdot\|v\|_{2}$. 

> [!proof]+
> We have:
> 1. Let $S:=\text{supp}(\beta^0)$. Then, 
>    $$\left\| (\beta-\beta^0)_{\overline{S}} \right\| _{1}=\sum_{i\notin S}\left| \beta_{i}-\beta_{i}^0 \right| =\sum_{i\notin S}\left| \beta_{i} \right| =\|\beta_{\overline{S}}\|_{1}=\|\beta\|_{1}-\|\beta_{S}\|_{1}\leq \|\beta^0\|_{1}-\|\beta_{S}\|_{1}$$However, notice that $\|\beta^0\|_{1}=\|\beta^0_{S}\|_{1}$ by definition of $S$. Hence, $$\left\| (\beta-\beta^0)_{\overline{S}} \right\| _{1}\leq\|\beta^0_{S}\|_{1}-\|\beta_{S}\|_{1}\leq \|(\beta-\beta^0)_{S}\|_{1}$$by triangle inequality.
> 2. By Cauchy-Schwarz, we have that: $$\|v\|_{1}^{2}=(\|v_{S}\|_{1}+\|v_{\overline{S}}\|_{1})^2\leq 4\|v_{S}\|_{1}^{2}=4\left( \sum_{i\in S}^{} \left| v_{i} \right| \right)^{2}\leq 4\left| S \right| \left( \sum_{i\in S}^{}v_{i}^{2} \right)\leq 4\left| S \right| \|v\|_{2}^2$$
---


> [!lemma] Theorem 4 (LASSO fast rate)
> Assume that $R:=\left\| \beta^0 \right\|_{1}$ is known. Let $\widehat{\beta}(y)\in \underset{ \beta \in \mathbb{R}^d,\|\beta\|_{1}\leq R }{ \arg\min }\left\| X\beta -y\right\|^2$. 
> 1. If $\left\| X_{i} \right\|^2=n$ for all columns $X_{i}$ and $X$ is $\gamma$-RE w.r.t. $\text{supp}(\beta^0)$, then:$$\mathbb{E}\left[ \frac{1}{n}\left\| X(\widehat{\beta}-\beta^0) \right\| ^2 \right] \leq \frac{k}{\gamma n}\cdot O(\log d)$$

> [!proof]-
> Let $u:= \widehat{\beta}-\beta_{0}$. Then, similarly to the Theorem 1, $$\frac{1}{2}\left\| Xu \right\| ^2_{2}\leq \braket{ u , X^\top w } \leq \|u\|_{1}\left\| X^\top w \right\| _{\infty}$$Now, let $S:=\text{supp}(\beta^0)$. From Lemma 3, $u\in C(S)$ and: $$\|u\|_{1}\leq 2\sqrt{ k }\|u\|_{2}\leq 2\sqrt{ \frac{k}{\gamma n} }\|Xu\|_{2}$$Hence, $$\left\| Xu \right\| ^2_{2}\leq 4\sqrt{ \frac{k}{\gamma n} }\|Xu\|_{2}\|X^\top w\|_{\infty}$$ and $\|Xu\|^2_{2}\leq \frac{16k}{\gamma n}\|X^\top w\|_{\infty}^2$. Using, $\mathbb{E}[\left\| X^\top w \right\| _{\infty}^{2}]\leq nO(\log d)$ from the proof of LASSO slow rate, we get that, $$\mathbb{E}\left[ \frac{1}{n}\left\| X(\widehat{\beta}-\beta^0) \right\| ^{2}_{2} \right] \leq \frac{16k}{\gamma n^{2}}\mathbb{E}\left[ \left\| X^\top w \right\| ^{2}_{\infty} \right] \leq \frac{k}{\gamma n}\cdot O(\log d)$$

---
##### 1.4.2.1 Sufficient Conditions for Restricted Eigenvalue Property
- **Related definition**: Let $X\in \mathbb{R}^{n,d}$ be a matrix s.t. $\left\| X_{1} \right\|^2=\dots=\left\| X_{d} \right\|^2=n$. Then, the ***pairwise incoherence*** of $X$ is defined as:$$\delta_{\text{PW}}(X):=\max_{i\neq j} \frac{1}{n}\left| \braket{ X_{i} ,  X_{j}}  \right| $$

---
> [!lemma] Theorem 5
> Let $X\in \mathbb{R}^{n,d}$ with $\left\| X_{1} \right\|^2=\dots=\left\| X_{d} \right\|^2=n$.
> 1. If $\delta_{\text{PW}}(X)\leq \frac{1}{8k}$, then $X$ is $\frac{1}{2}$-RE for every $S\subseteq [d]$ of size at most $k$.

> [!proof]-
> Let $S\subseteq [d]$ with size at most $k$ and $u\in C(S)$. Further, let $\delta:=\frac{1}{8k}$. We want to show that: $$\frac{1}{n}\left\| Xu \right\| ^{2}\geq \frac{1}{2}\|u\|^{2}$$We have that: $$\frac{1}{n}\left\| Xu \right\| ^{2}=\frac{1}{n}\sum_{i,j}\braket{ X_{i} , X_{j} } u_{i}u_{j}$$Then, $$\left| \sum_{i\neq j}^{} \frac{1}{n}\braket{ X_{i} , X_{j} } u_{i}u_{j} \right|\leq \sum_{i,j}^{}\left| u_{i} \right| \left| u_{j} \right| \delta= \delta\|u\|_{1}^2\leq 4k\delta\|u\|^2_{2}$$Hence, $$\frac{1}{n}\|Xu\|^2=\left( \sum_{i}^{} \frac{1}{n}\|X_{i}\|^2 u_{i}^2 \right)+\sum_{i\neq j}^{} \frac{1}{n}\braket{ X_{i} , X_{j} } u_{i}u_{j}\geq(1-4k\delta)\|u\|^2_{2}\geq\frac{1}{2}\|u\|^2_{2} $$
---
> [!h] Example 1
> Let $X$ be a Gaussian random matrix, i.e. $X_{1},\dots,X_{d}\sim \mathcal{N}(0,I_{n})$ i.i.d. for $d\geq n\geq 2$. Then, 
> 1. for $k=\Omega\left( \sqrt{ \frac{n}{\log d} } \right)$, w.h.p., $X$ is $\frac{1}{2}$-RE for all $S\subseteq [d]$ with $\left| S \right|\leq k$.

> [!proof]-
> We have that: $$\mathbb{E}[\braket{ X_{i} , X_{j} } ]=\begin{cases}n&i=j\\0&i\neq j\end{cases}$$Hence, we get that: $$\frac{\braket{ X_{i} , X_{j} } }{n}\leq \frac{1}{n}O(\sqrt{ n\log d })$$and $\delta_{\text{PW}}(X)\lesssim \sqrt{ \frac{\log d}{n} }$. The rest follows from Theorem 5.

---
### 2. Linear Regression with Oblivious Outliers
> [!outlook] Setting (Oblivious Outliers)
> We have:
> 1. **Design**: $X\in \mathbb{R}^{n,d}$ with $\frac{1}{n}X^\top X=I_{d}$.
> 2. **Observation**: $y=X\beta ^{0}+\eta$ for unknown $\beta ^{0}\in \mathbb{R}^d$.
> 3. **Noise**: $\eta$ with $\{ \eta \}=\{ -\eta \}$ and $\eta_{1},\dots,\eta_{n}$ are independent.

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
> Let $\alpha:=\min_{i}\mathbb{P}(\left| \eta_{i} \right|\leq 1)$. Let $x_{1},\dots,x_{n}\in \mathbb{R}^d$ be the rows of $X$ and $C:=\frac{1}{\sqrt{ d }}\max_{i}\|x_{i}\|$. 
> 1. if $n= \Omega\left( \frac{d^{2}C^2}{\alpha^{2}} \right)$ then for the Huber loss estimator $\widehat{\beta}$ with probability $0.99$: $$\left\| \widehat{\beta}-\beta ^{*} \right\| ^{2}\leq O\left( \frac{d}{\alpha^{2}n} \right)$$

> [!proof]-
> We define: $$f:\mathbb{R}^d\to \mathbb{R},\quad \beta\mapsto \frac{1}{n}\sum_{i\in[n]}^{}\Phi(\braket{ x_{i} , \beta } -y_{i})$$Then, $\nabla f(\beta)=\frac{1}{n}\sum_{i\in[n]}^{}\Phi'(\braket{ x_{i} , \beta } -y_{i})x_{i}$ where: $$\Phi'(t)=\begin{cases}\text{sgn}(t)\cdot \left| t \right|&\left| t \right|\leq 2\\2\cdot  \text{sgn}(t)&\left| t \right|\geq 2\end{cases}=\text{sgn}(t)\cdot\min\{ \left| t \right|,2 \}, \quad \Phi''(t)=\mathbb{1}_{\{ \left| t \right| \leq 2 \}}$$
> Let $M^{\text{low}}:=\frac{1}{2n}\sum_{i=1}^{n}\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}x_{i}x_{i}^\top$. Then:
> 1. **Claim 1: For any unit vector $u\in \mathbb{R}^d$, we have that:** $$\frac{1}{n}\sum_{i\in[n]}\braket{ x_{i} , u } ^{4}\leq C^{2}d$$Firstly, note that: $$\frac{1}{n}\sum_{i\in[n]}^{}\braket{  x_{i},u}^{2}=\frac{1}{n }u^\top X^\top X u=u^\top u=\|u\|^2=1 $$Now, using Cauchy-Schwarz, it follows that:$$\frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i}, u } ^4\leq \frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^2\underbrace{ \left\| x_{i} \right\| ^{2} }_{ \leq C^{2}d }\underbrace{ \|u\|^{2} }_{ =1 }\leq C^{2}d\left( \frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2} \right) =C^{2}d$$
> 2. **Claim 2**: **For a unit vector $u\in \mathbb{R}^d$, we have that with probability $\geq 1-2\exp\left( -\frac{2n\alpha^{2}}{24^{2}C^2d} \right)$** $$\left| u^\top\left( M^\text{low}-\frac{\alpha}{2}\text{id} \right)u \right|\leq \frac{\alpha}{24} $$Notice that:$$u^\top M^{\text{low}}u=\frac{1}{2n}\sum_{i=1}^{n}\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}u^\top x_{i}x_{i}^\top u=\frac{1}{2n}\sum_{i=1}^{n} \mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}\braket{  x_{i} ,u} ^{2}$$ As $\eta_{i}$ are independent, so are $\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}$. Hence, we have: $$\frac{1}{2n}\sum_{i=1}^{n}\mathbb{E}[\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}\braket{ x_{i} , u } ^{2}]\geq\frac{\alpha}{2n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^{2}=\frac{\alpha}{2n}u^\top X^\top X u =u^\top \left( \frac{\alpha}{2}I_{d} \right) u$$Hence, by [[Expected Value|Hoeffding]], using $0\leq \mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}\braket{ x_{i} , u }^{2}\leq \braket{ x_{i} , u }^{2}$, $$\begin{align}\mathbb{P}\left( \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right)u \right| \geq \frac{\alpha}{24} \right)&=\mathbb{P}\left(\frac{1}{n} \left|  \sum_{i=1}^{n}(\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}-\mathbb{E}[\mathbb{1}_{\{ \left| \eta_{i} \right|\leq 1 \}}])\braket{ x_{i} , u } ^{2}\right| \geq \frac{\alpha}{12} \right)\\&\leq 2 \exp \left( -\frac{2n\alpha^{2}}{12^{2}\cdot \frac{1}{n}\sum_{i=1}^{n}\braket{ x_{i} , u } ^4}\cdot \right) \leq2\exp \left( -\frac{2n\alpha^{2}}{12^2 C^{2}d} \right)\end{align} $$This proves the statement.
> 3. **Claim 3: With probability $\geq 1-\exp(-d)$ we have:** $$\left| u^\top\left( M^\text{low}-\frac{\alpha}{2}\text{id} \right)u \right|\leq \frac{\alpha}{6},\quad \forall u\in S^{d-1}$$First, as $S^{d-1}$ is compact, there exists a $1/4$-net $\mathcal{N}_{1/4}$ where $\left| \mathcal{N}_{ 1 / 4} \right|\leq 10^d$. Then, for any symmetric matrix $A$, let $u\in \arg\max_{v\in S^{d-1}}\left| v^\top Av \right|$. Then, there exists $w\in \mathcal{N}_{1 / 4}$ with $\|u-w\|\leq \frac{1}{4}$. Notice that: $$u^\top Au=w^\top Aw+w^\top A(u-w)+(u-w)^\top A u=w^\top Aw+(u-w)^\top A (u+w)$$Hence, $$\begin{align}\left| u^\top Au \right| &\leq \left| w^\top Aw \right| +\left| (u-w)^\top A (u+w) \right| \\&\leq \left| w^\top Aw \right| +\|u-w\|\| A \|\|u+w\|  \\&\leq \max_{v\in \mathcal{N}_{1 / 4}}\left| w^\top Aw \right| +\frac{1}{2}\| A \| \end{align}$$We know that $\left\| A \right\|=\left| \lambda\right|$ for some eigenvalue $\lambda$. Let $v\in S^{d-1}$ be an eigenvector. Then, $$\left\| A \right\| =\left| \lambda \right| =\left| \lambda v^\top v \right| =\left| v^\top  Av \right|\leq \left| u^\top Au \right|  $$Hence, we can conclude that: $$\max_{v\in S^{d-1}}\left| v^\top Av \right| =\left| u^\top Au \right| \leq 2\max_{v\in \mathcal{N}_{1 / 4}}\left| v^\top Av \right| $$Therefore, for $A:=M_{\text{low}}-\frac{\alpha}{2}I_{d}$ symmetric, $$\begin{align}\mathbb{P}\left( \exists u\in S^{d-1}: \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{6}\right)&=\mathbb{P}\left(\max_{u\in S^{d-1}} \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{6}\right)\\&\leq \mathbb{P}\left(\max_{u\in \mathcal{N}_{1 / 4}} \left| u^\top\left( M_{\text{low}}-\frac{\alpha}{2}I_{d} \right) u \right| \geq \frac{\alpha}{24}\right)\\&\leq 10^d  \cdot 2\exp \left( -\frac{2n\alpha^{2}}{24^{2}\cdot C^{2}d} \right) \end{align}$$which is less than $\exp(-d)$ for the given $n$. 
> 
> Therefore, we have that w.h.p: $$u^\top M^{\text{low}}u\geq\frac{\alpha}{2}-\frac{\alpha}{6}=\frac{\alpha}{3}\|u\|^{2}_{2},\quad \forall u\in S^{d-1}$$and this is scalable for any $u\in\mathbb{R}^d$. 
>    
> 4. **Claim 4**: for $R:= \frac{1}{C\sqrt{ d }}$ and for all $u$ with $\|u\|\leq  R$, we have that: $$f(\beta^0+u)\geq f(\beta ^{0})-\left\| \nabla f(\beta ^{0}) \right\|\cdot \|u\|+\frac{\alpha}{10}\|u\|^{2}$$
>    
>    From [[Taylor's Theorem|2nd order Hamadard Lemma]], $$f(\beta ^{0}+u)=f(\beta ^{0})+\braket{ \nabla f(\beta ^{0}) , u } +\underbrace{ u^\top \left( \int_{0}^{1} (1-t)\text{H}_{f}(\beta ^{0}+tu) \, dt  \right)u }_{ =: M(u) }  $$Now, we have that: 
>    
>    $$\text{H}_{f}(\beta ^{*}+tu)=\frac{1}{n}\sum_{i\in[n]}^{}\Phi''(t\braket{ x_{i} ,u } -\eta_{i})x_{i}x_{i}^\top=\frac{1}{n}\sum_{i\in[n]}^{} \mathbb{1}_{\{ \left| t\braket{ x_{i} , u } -\eta_{i} \right| \leq 2 \}}x_{i}x_{i}^\top$$ and:$$\begin{align}M(u)&= \frac{1}{n}\sum_{i\in[n]}\left( \int_{0}^{1}  (1-t) \underbrace{ \mathbb{1}_{\{ \left| t\braket{ x_{i} , u } -\eta_{i} \right| \leq 2 \}} }_{ \geq \mathbb{1}_{\{ \left| \braket{ x_{i} , u }  \right|\leq 1   \}}\mathbb{1}_{\{ \left| \eta_i \right|\leq 1  \}} } \, dt \right)\braket{ x_{i} , u }^{2}\\&\geq \frac{1}{2n}\sum_{i\in[n]}\mathbb{1}_{\{ \left| \braket{ x_{i} , u } \right| \leq 1 \}}\mathbb{1}_{\{ \left| \eta_{i}\right| \leq 1 \}}\braket{ x_{i} , u }^{2}\\&\geq \mathbb{1}_{\{ \left| C\sqrt{ d }\cdot R\right| \leq 1  \}}\left( u^\top M^{\text{low}} u \right)\\&\geq \frac{\alpha}{3}\|u\|^{2}\end{align}$$This proves the statement.
>    
> 
> 
> Now, define $u:= \widehat{\beta}-\beta ^{0}$, we show that $\|u\|\leq 1 / (C\sqrt{ d })$. 
> 
> we have $f(\beta ^{0})\geq f(\widehat{\beta})=f(\beta ^{0}+u)$ and further that: $$\left\| \nabla f(\beta ^{0}) \right\|\cdot \|u\|\geq \frac{\alpha}{10}\|u\|^{2},\quad \left\| \widehat{\beta}-\beta ^{0} \right\| \leq \frac{10}{\alpha}\left\| \nabla f(\beta ^{0}) \right\| $$
> 
> By noting that $\nabla f(\beta ^{0})=\frac{1}{n}\sum_{i\in[n]}^{}\Phi'(\eta_{i})x_{i}$ we have:$$\begin{align}\mathbb{E}[\left\| \nabla f(\beta ^{0}) \right\| ^{2}]=\frac{1}{n^{2}}\sum_{i\in [n]}^{}\|x_{i}\|^2\cdot \underbrace{ \mathbb{E}[\Phi'(\eta_{i})^{2}] }_{ \leq 4 }+\frac{1}{n^{2}}\sum_{i\neq j}^{}\braket{ x_{i} , x_{j} } \underbrace{ \mathbb{E}[\Phi'(\eta_{i})\Phi'(\eta_{j})] }_{ =\mathbb{E}[\Phi'(\eta_{i})]\mathbb{E}[\Phi'(\eta_{j})]=0 }\leq \frac{4}{n^{2}}dn=\frac{4d}{n}\end{align}$$
> 
> Therefore, $$\mathbb{P}\left( \left\| \widehat{\beta}- \beta ^{*}\right\| ^{2}\geq \frac{40000 d}{\alpha^{2}n}\right)\leq  \frac{\mathbb{E}\left[ \left\| \widehat{\beta}- \beta ^{*}\right\| ^{2} \right] }{40000d / \alpha^{2}n}\leq \frac{\mathbb{E}\left[ \left\| \nabla f(\beta ^{*}) \right\| ^{2} \right] }{400d / n}\leq0.01$$
> This proves the statement.

---
### 3. Low-Rank Factorization Models and PCA
#### 3.1 Single Spike Model
> [!outlook] Setup (Single-Spike)
> We have:
> 1. **Observation**: $Y:= X^{*}+W$ for unknown $X^{*}\in \mathbb{R}^{m,n}$ with $\text{rk}(X^{*})=1$.
> 2. **Noise**: $W\in \mathbb{R}^{m,n}$ where $W_{i,j}\sim \mathcal{N}(0,1)$ i.i.d.

---
> [!definition]
> Consider the setup as above. 
> 1. the ***rank-1 estimator*** is given by: $$\widehat{X}\in\underset{ \text{rank}(X)\leq 1 }{ \arg\min }\|X-Y\|^{2}_{F}$$
---
> [!lemma] Theorem 1 (Guarantees of Best Rank-1 Approximation)
> In single-spike model, we have that: $$\frac{1}{nm}\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq O\left( \frac{1}{n}+\frac{1}{m} \right) $$

> [!proof]-
> Let $U:= \widehat{X}-X^{*}$. We have that: $$0\leq \left\| X^{*}-Y \right\| ^2_{F}-\left\| \widehat{X}-Y \right\| ^2_{F}=\left\| W \right\| ^2_{F}-\left\| U-W \right\| ^{2}_{F}=2\braket{ U , W } -\left\| U \right\| ^{2}_{F}$$ where $\braket{ U , W }:=\sum_{i,j}^{}U_{ij}W_{ij}$. Further, $\text{rk}(U)\leq \text{rk}(\widehat{X})+\text{rk}(X^{*})\leq 2$. Hence, $$\left\| U \right\| _*\leq \sqrt{ 2 }\|U\|_{F}$$Therefore, by Hölder, $$\left\| U \right\| ^{2}_{F}\leq 2\braket{ U , W } \leq 2 \|U\|_{*}\|W\|\leq 2\sqrt{ 2 }\|U\|_{F}\|W\|$$Hence, $\|U\|^2_{F}\leq 8\|W\|^{2}$. We can conclude by: $$\frac{1}{nm}\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq \frac{8}{nm}\mathbb{E}[\left\| W \right\| ^{2}]\leq O\left( \frac{n+m}{nm} \right)=O\left( \frac{1}{n}+\frac{1}{m} \right)$$

---
#### 3.2 Multiple-Spike Model

> [!outlook] Setup (Multiple-Spike)
> We have:
> 1. **Observation**: $Y:= X^{*}+W$ for unknown $X^{*}\in \mathbb{R}^{m,n}$ with $\text{rk}(X^{*})\leq r$.
> 2. **Noise**: $W\in \mathbb{R}^{m,n}$ where $W_{i,j}\sim \mathcal{N}(0,1)$ i.i.d.

---
> [!definition]
> Consider the setup as above. 
> 1. the ***rank-r estimator*** is given by: $$\widehat{X}\in\underset{ \text{rank}(X)\leq r }{ \arg\min }\|X-Y\|^{2}_{F}$$
---
> [!lemma] Theorem 1 (Guarantees of Best Rank-r Approximation)
> In multiple-spike model, we have that: $$\frac{1}{nm}\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq r \cdot  O\left( \frac{1}{n}+\frac{1}{m} \right) $$

> [!proof]-
> Let $U:= \widehat{X}-X^{*}$. We have that: $$0\leq \left\| X^{*}-Y \right\| ^2_{F}-\left\| \widehat{X}-Y \right\| ^2_{F}=\left\| W \right\| ^2_{F}-\left\| U-W \right\| ^{2}_{F}=2\braket{ U , W } -\left\| U \right\| ^{2}_{F}$$ where $\braket{ U , W }:=\sum_{i,j}^{}U_{ij}W_{ij}$. Further, $\text{rk}(U)\leq \text{rk}(\widehat{X})+\text{rk}(X^{*})\leq 2r$. Hence, $$\left\| U \right\| _*\leq \sqrt{ 2r }\|U\|_{F}$$Therefore, by Hölder, $$\left\| U \right\| ^{2}_{F}\leq 2\braket{ U , W } \leq 2 \|U\|_{*}\|W\|\leq 2\sqrt{ 2r }\|U\|_{F}\|W\|$$Hence, $\|U\|^2_{F}\leq 8r\|W\|^{2}$. We can conclude by: $$\frac{1}{nm}\mathbb{E}\left[  \left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\right]\leq \frac{8r}{nm}\mathbb{E}[\left\| W \right\| ^{2}]\leq  r \cdot O\left( \frac{n+m}{nm} \right)=r \cdot O\left( \frac{1}{n}+\frac{1}{m} \right)$$

---
### 4. Matrix Completion Model
#### 4.1 Matrix Bernstein Inequality
> [!lemma] Theorem (Matrix Bernstein)
> Let $Z$ be a $\mathbb{R}^{d,d}$-valued random variable with $d\geq 2$ s.t. $\mathbb{E}[Z]=0$ and $\{ Z \}=\{ Z^\top \}$. 
> 1. if $Z$ is $(\sigma,b)$-Bernstein, i.e. $$\left\| \mathbb{E}[\left\| Z \right\| ^{j-2}ZZ^\top ]\right\|\leq j!\cdot  b^{j-2}\cdot \sigma^{2} ,\quad \forall j\geq 2$$then with probability $1-d^{-100}$, for $Z_{1},\dots,Z_{n}\sim \{ Z \}$ iid, $$\left\| \frac{1}{n}\sum_{i\in[n]}^{}Z_{i} \right\| \lesssim \sigma \sqrt{ \frac{\log d}{n} }+b\frac{\log d}{n}$$
---
> [!lemma] Theorem (Matrix Bernstein)
> Let $Z_{1},\dots,Z_{m}$ be independent $\mathbb{R}^{n,n}$-valued random variables s.t. $\mathbb{E}[Z_{i}]=0$ and $\{ Z_{i} \}=\{ Z_{i}^\top \}$. 
> 1. if it holds that: $$\left\| \sum_{i=1}^{m} \mathbb{E}[Z_{i}Z_{i}^\top] \right\| \leq \sigma^{2},\quad \left\| Z_{i} \right\| \leq b$$ then w.h.p.:$$\left\| \sum_{i\in[m]}^{}Z_{i} \right\| \lesssim \sigma \sqrt{ \log n}+b\log n$$


---
#### 4.2 Matrix Completion Model
> [!outlook] Setup
> For $r,d,n\geq2$.
> 1. **Unknown**: $\Theta ^{0}\in \mathbb{R}^{d,d}$ with $\text{rnk}(\Theta ^{0})\leq r$
> 2. **Observation**: $\{ (E_{a(i),b(i)},y_{i}) \}_{i\in [n]}$ where 
> 	- $y_{i}:= \braket{ E_{a(i),b(i)} , \Theta ^{0} }+w_{i}$ for $w_{i}\sim \mathcal{N}(0,\sigma^{2})$ and $a_{i},b_{i}\sim \text{Uni}([d])$ i.i.d. 
> 3. **Error measure**: For estimator $\widehat{\Theta}$, the error is given as $$\text{err}(\widehat{\Theta}):=\frac{1}{d^{2}}\left\| \widehat{\Theta}-\Theta ^{0} \right\|^{2}_{F}$$
- **Remark**: Following are the observations:
	1. $n\gg rd$ as \#observations has to be greater than \#degree of freedom.
	2. $n\gg d\log d$ as all rows and columns have to be covered.
- **Remark**: Let $\Theta^0:=\pm\alpha E_{1,1}$ for $\sigma=0$. Then, if $n\ll d^{2}$$$\mathbb{P}(\Theta^0_{1,1}\text{ not observed})=\left( 1-\frac{1}{d^{2}} \right)^n\geq 1-\frac{n}{d^{2}}\approx 1$$and $\mathbb{E}[\text{err}(\widehat{\Theta})|\Theta^0_{1,1}\text{ is not observed}]\geq \alpha^{2} /d^{2}$. Hence, the error grows with $\left\| \Theta^0 \right\|_{\text{max}}$.
---
> [!definition]
> In the given setup,
> 1. The ***maximum likelihood estimator*** is given by: $$\widehat{\Theta}\in \underset{ \text{rank}(\Theta)\leq r }{ \arg\min } \sum_{i=1}^{n}(\braket{ E_{a(i),b(i)} , \Theta  } -y_{i})^{2}$$
- **Remark**: Computing the MLE is NP-hard in the worst case.
---
> [!lemma] Theorem 1 
> Consider the polytime estimator: $$\widehat{\Theta}:=\underset{ \text{rnk}(\Theta)\leq r }{ \arg\min }\left\| \Theta-\frac{d^{2}}{n}\sum_{i\in[n]}^{}y_{i}E_{a(i),b(i)} \right\| ^{2}_{F}$$Then, if $n\geq d\log d$, then w.h.p.:
> $$\text{err}(\widehat{\Theta})\lesssim \frac{rd\log d}{n}(\sigma^{2}+\left\| \Theta^0 \right\| _{\text{max}}^{2})$$

> [!proof]-
> Let $Y:=\frac{d^{2}}{n}\sum_{i\in[n]}^{}y_{i}E_{a(i),b(i)}$. We have that:
> 1. **Claim 1: $\mathbb{E}[Y]=\Theta^0$.**
>    Notice that for any $i,j$, $$\mathbb{E}[Y_{p,q}]=\frac{d^{2}}{n}\sum_{i=1}^{n}\mathbb{E}[y_{i}\mathbb{1}_{a(i),p}\mathbb{1}_{b(i),q}]=\frac{d^{2}}{n}\sum_{i=1}^{n}\Theta^0_{p,q}\cdot \frac{1}{d^{2}}=\Theta^0_{p,q}$$
> 
> Let $U:= \widehat{\Theta}-\Theta^0$. From Claim 1, we can write $Y=\Theta^0+W$ where $\mathbb{E}[W]=0$. Hence, from Multiple-Spike Theorem 1 proof, $\left\| U \right\|^{2}_{F}\leq 8r\left\| W \right\|^{2}$. Now, $$\begin{aligned}W&=Y-\Theta^0\\&=\frac{d^{2}}{n}\sum_{i\in[n]} y_{i}E_{a(i),b(i)}-\Theta^0\\&=\frac{1}{n}\sum_{i\in[n]} (d^{2}y_{i}E_{a(i),b(i)}-\Theta^0)\\&=\frac{1}{n}\sum_{i\in[n]} \underbrace{ (\braket{ E_{a(i),b(i)} , \Theta^0 } d^{2} E_{a(i),b(i)}-\Theta^0) }_{ =:Z^1_{i} }+\frac{1}{n}\sum_{i\in[n]}^{}\underbrace{ w_{i}d^{2}E_{a(i),b(i)} }_{ =:Z^{2}_{i} }\end{aligned}$$
> 
> 2. **Claim 2: w.h.p $\left\| \frac{1}{n}\sum_{i\in[n]}^{}Z^1_{i} \right\|^{2}\lesssim \left\| \Theta^0 \right\|^{2}_{\text{max}}\frac{d^3 \log d}{n}$**.
>    We use the matrix Bernstein identity. Firstly, $$\mathbb{E}[Z^1_{i}]_{p,q}=\mathbb{E}[d^{2}\Theta^0_{a(i),b(i)}\mathbb{1}_{a(i),p}\mathbb{1}_{b(i),q}-\Theta^0_{p,q}]=\Theta^0_{p,q}-\Theta^0_{p,q}=0$$Further, $\{ Z^1_{i} \}=\{ (Z^1_{i})^\top \}$. Therefore, it suffices to show that $Z^1_{i}$ is $(\left\| \Theta^0 \right\|_{\text{max}}\cdot d^{3/2},2\left\| \Theta^0 \right\|_{\text{max}}d^{2})$-Bernstein. We have: $$\begin{aligned}\left\| Z^1_{i} \right\| &\leq \left\| \braket{ E_{a(i),b(i)} , \Theta^0 } d^{2}E_{a(i),b(i)} \right\| +\left\| \Theta^0 \right\| \\&\leq \left| \Theta^0_{a(i),b(i)} \right| d^{2}+\left\| \Theta^0 \right\| _{\text{max}}d\\&\leq 2\left\| \Theta^0 \right\|_{\text{max}}d^{2} \end{aligned}$$Now, as $\mathbb{E}[\braket{ E_{a(i),b(i)} , \Theta^0 } d^{2} E_{a(i),b(i)}]=\mathbb{E}[Z^1_{i}+\Theta^0]=\Theta^0$,$$\begin{aligned}0\leq \mathbb{E}[Z^1_{i} (Z_{i}^1)^\top]&=\mathbb{E}[\braket{ E_{a(i),b(i)} , \Theta^0 } ^{2}d^4E_{a(i),a(i)}]-\Theta^0(\Theta^0)^\top\\&\leq \left\| \Theta^0 \right\|_{\text{max}}^{2}d^3 I_{d}  \end{aligned}$$Therefore, $$\begin{aligned}\left\| \mathbb{E}[\left\| Z^1_{i} \right\| ]^{j-2}Z^1_{i}( Z^1_{i})^\top \right\| &\leq (2\left\| \Theta^0 \right\| _{\text{max}}d^{2})^{j-2}\left\|  \mathbb{E}[ Z^1_{i}( Z^1_{i})^\top ]\right\| \\&\leq (2\left\| \Theta^0 \right\| _{\text{max}}d^{2})^{j-2}\left\| \Theta^0 \right\|_{\text{max}}^{2}d^3\end{aligned}$$Hence, $$\left\| \frac{1}{n}\sum_{i\in[n]}^{}Z^1_{i} \right\| \lesssim \left\| \Theta^0 \right\| _{\text{max}}\left( d^{3/2}\sqrt{ \frac{\log d}{n} }+d^{2}\frac{\log d}{n} \right)\leq \left\| \Theta^0 \right\| _{\text{max}} d^{3/2}\sqrt{ \frac{\log d}{n} }$$
> 3. **Claim 3: w.h.p $\left\| \frac{1}{n}\sum_{i\in[n]}^{}Z^2_{i} \right\|\lesssim \sigma^{2} \frac{d^3\log d}{n}$.**
>    We use Bernstein again. Firstly, $\mathbb{E}[Z^2_{i}]=0$ as $\mathbb{E}[w_{i}]=0$ and symmetrically distributed. We show that $Z^2_{i}$ is $(\sigma d^{3/2},\sigma d^{2})$-Bernstein. We have $\left\| Z^{(2)}_{i} \right\|=\left| w_{i} \right|d^{2}$ and: $$\begin{aligned}\mathbb{E}\left[ \left\| Z^{(2)}_{i} \right\| ^{j-2}Z^{(2)}_{i}(Z^{(2)}_{i})^\top \right] =\mathbb{E}\left[ \left| w_{i} \right| ^jd^{2j} E_{a(i),a(i)} \right]=\mathbb{E}[\left| w_{i} \right| ^j]d^{2j}\cdot \frac{1}{d}I_{d}\end{aligned}$$As $\mathbb{E}[\left| w_{i} \right|^j]\leq\sigma^j(j-1)!!\leq \sigma^j j!$ and we have that the spectral norm is bounded by $j!\cdot\sigma^j d^{2j-1}=j!(\sigma d^2)^{j-2}(\sigma^2 d^3)$. Hence, $$\left\| \frac{1}{n}\sum_{i\in[n]}^{}Z^{(2)}_{i} \right\| \leq\sigma d^{3/2}\sqrt{ \frac{\log d}{n} }+\sigma d^{2} \frac{\log d}{n}\leq 2\sigma d^{3/2}\sqrt{ \frac{\log d}{n} }$$
>    
>  Therefore, we have that: $$\begin{aligned}\text{err}(\widehat{\Theta})=\frac{1}{d^{2}}\left\| U \right\| ^{2}_{F}\leq \frac{8r}{d^{2}}\left\| W \right\| ^{2}&\leq \frac{16r}{d^{2}}\left( \left\| \frac{1}{n}\sum_{i=1}^{}Z^{(1)}_{i}  \right\|^{2}+\left\| \frac{1}{n}\sum_{i=1}^{}Z^{(2)}_{i}  \right\|^{2}  \right)\\& \lesssim \frac{rd\log d}{n}(\sigma^{2}+\left\| \Theta^0 \right\| ^{2}_{\text{max}})\end{aligned}$$
---
### 4. Community Detection
> [!outlook] Setup
> For $\varepsilon\in [0,1]$ and $d\geq 1$, 
> 1. **Unknown**: $x^{0}\in \{ \pm 1 \}^n$. 
> 2. **Observation**: A $n$-vertex [[graph]] $G$ where: $$\mathbb{P}(ij\in E(G))=(1+\varepsilon x^{0}_{i}x^{0}_{j}) \frac{d}{n}$$
> 3. **Error measure**: For an estimator $\widehat{X}$ of $X^0:=x^0(x^0)^\top\in\mathbb{R}^{n,n}$ we have: $$\text{err}(\widehat{X}):=\frac{1}{n^{2}}\left\| \widehat{X}-X^0 \right\| ^{2}_{F}$$

---
> [!lemma] Theorem 1
> Consider the polytime estimator:
>  $$\widehat{X}:=\underset{ \text{rnk}(X)\leq 1 }{ \arg\min }\left\| X-Y \right\| ^{2}_{F},\quad Y:= I+\frac{1}{\varepsilon }\left( \frac{n}{d}A-1 \right)$$where $A$ is the adjacency matrix of $G$.
> 1. if $d\geq \Omega( \log n / \varepsilon^{2})$.  then w.h.p $\text{err}(\widehat{X})\le 0.01$.

> [!proof]-
> We have that:
> 1. **Claim 1: $\mathbb{E}[Y]=X^0$.**
>    We have that for $i\neq j$:$$\mathbb{E}[Y_{ij}]=\frac{n}{\varepsilon d}\left( \mathbb{E}[A_{ij}]-\frac{d}{n} \right)=X^0_{ij}$$
>    For $i=j$, $\mathbb{E}[Y_{ii}]=1=X^0_{ii}$. 
> 
> Now, $Y-X^0=\sum_{i<j}^{}Z^{(i,j)}$ where $Z^{(i,j)}:=(Y_{ij}-X^0_{ij})( E_{ij}+E_{ji})$. We use the Bernstein Variant. Firstly, $\mathbb{E}[Z^{(i,j)}]=0$ and the distribution is symmetric. Now, $$\left\| Z^{(i,j)} \right\| \leq \left| Y_{ij}-X^0_{ij} \right| \leq 1+ \frac{1}{\varepsilon}\left( \frac{n}{d}-1 \right) \leq \frac{n}{\varepsilon d}$$and $$\begin{aligned}\mathbb{E}[(Y_{ij}-X^0_{ij})^{2}]&\leq \mathbb{E}[Y_{ij}^{2}]\leq (1+\varepsilon) \frac{d}{n}\left( \frac{1}{\varepsilon}\left( \frac{n}{d}-1 \right)  \right)^{2}+\frac{1}{\varepsilon^{2}}\\&\leq(1+\varepsilon) \frac{1}{\varepsilon^{2}}\left( \frac{n}{d}-2+\frac{d}{n}+\frac{1}{1+\varepsilon} \right) \\&\leq \frac{2n}{\varepsilon^{2}d}\end{aligned}$$Therefore, $$\mathbb{E}[Z^{(i,j)}(Z^{(i,j)})^\top]\leq\frac{ 2n}{\varepsilon^{2}d}(E_{ii}+E_{jj})$$and $$\sum_{i<j}\mathbb{E}[Z^{(i,j)}(Z^{(i,j)})^\top]\leq \frac{2n}{\varepsilon^{2} d}(n-1)I_{n},\quad \left\| \sum_{i<j}\mathbb{E}[Z^{(i,j)}(Z^{(i,j)})^\top] \right\| \leq \frac{2n^{2}}{\varepsilon^{2}d}$$Hence, by Bernstein whp, $$\left\| Y-X^0 \right\| =\left\| \sum_{i<j}^{}Z^{ij} \right\| \lesssim \sqrt{ \frac{2n^{2}\log n}{\varepsilon^{2} d} }+\frac{n}{\varepsilon d}\log n\lesssim\frac{n}{\varepsilon} \sqrt{ \frac{\log n}{d} }$$Further, $$\text{err}(\widehat{X})=\frac{1}{n^{2}}\left\| \widehat{X}-Y \right\| ^{2}_{F}\lesssim \frac{1}{n^{2}}\left\| Y-X^0 \right\| ^{2}\lesssim \frac{\log n}{\varepsilon^{2} d} \lesssim 1 $$
---
##### 4.1 Grothendieck's Inequality
> [!lemma] Proposition 1 (Supremum norm on a space)
> Let $\mathcal{C}\subseteq \mathbb{R}^{n,n}$ that is bounded and $\text{span}(\mathcal{C})=\mathbb{R}^{n,n}$. Let the $\mathcal{C}$-norm on $\mathbb{R}^{n,n}$ be defined as: $$\left\| \cdot  \right\| _{\mathcal{C}}:\mathbb{R}^{n,n}\to \mathbb{R},\quad M\mapsto \sup_{X\in \mathcal{C}}\left| \braket{ X , M }  \right| $$Then, 
> 1. $\left\| \cdot \right\|_{\mathcal{C}}$ is a norm.

> [!proof]-
> We have that:
> 1. For $a\in \mathbb{R}$, $$\left\| aM \right\| _{\mathcal{C}}=\sup_{X\in \mathcal{C}}\left| \braket{ X , aM }  \right| =\left| a \right| \sup_{X\in \mathcal{C}}\left| \braket{ X , M }  \right| =\left| a \right| \left\| M \right\| _{\mathcal{C}}$$Further, triangle inequality is given by supremum. Now, for homogeneity, if $\left\| M \right\|_{\mathcal{C}}=0$, then $M=0$.

---
> [!lemma] Proposition 2 (Grothendieck Norm)
> The ***Grothendieck norm*** is defined as:$$\left\| \cdot  \right\|_{G}:\mathbb{R}^{n,n}\to \mathbb{R},\quad A\mapsto\sup_{\begin{array}\ 0\leq W\in \mathbb{R}^{2n,2n}\\W_{ii}=1\end{array}}\left\langle W,\begin{bmatrix} 0&A\\0&0\end{bmatrix}\right\rangle$$

> [!proof]-
> To show that it is a norm, homogeneity and triangle inequality is obvious. For positive definiteness, assume $A\neq 0$. Then, there exists $p,q$ s.t. $A_{pq}\neq 0$. Let 
---
- **Related definition**: Let $\mathcal{C}_{\text{cut}}:=\{  uv^\top:u,v\in \{ \pm 1 \}^n \}$. Then, $\left\| \cdot \right\|_{\text{cut}}:=\left\| \cdot \right\|_{\mathcal{C}_{\text{cut}}}$ is a norm. 
---
> [!lemma] Lemma 3
> We have that:
> 1. $\left\| A \right\|_{\text{cut}}=\sup_{\|x\|_{\infty},\|y\|_{\infty}\leq 1}\braket{ x , Ay }=\sup_{x,y\neq 0}\frac{\braket{ x , Ay }}{\|x\|_{\infty}\|y\|_{\infty}}$
> 2. for any jointly distributed random vectors $x,y\in \mathbb{R}^{n}$, $$\mathbb{E}[\braket{ x , Ay } ]\leq \text{max}_{i}\{ \mathbb{E}[x_{i}^{2}],\mathbb{E}[y_{i}^{2}] \}\left\| A \right\| _{G}$$where the equality is achieved for jointly Gaussian $x,y$ with $\mathbb{E}[x_{i}^{2}]=\mathbb{E}[y_{i}^{2}]=1$. 

> [!proof]-
> We have that:
> 1. Firstly, $$\left\| A \right\| _{\text{cut}}=\sup_{x,y\in \{ \pm 1 \}^n}\braket{ A , xy^\top } =\sup_{x,y\in \{ \pm 1 \}^n}\text{tr}(Ayx^\top) =\sup_{x,y\in\{ \pm 1 \}^n}\braket{ x , Ay } \leq \sup_{\|x\|_{\infty},\|y\|_{\infty}\leq 1}\braket{ x , Ay }$$The converse holds as the optimum is at the extremum. For the second equality, we can consider $x':= \frac{x}{\|x\|_{\infty}}$ and $y':=\frac{y}{\|y\|_{\infty}}$.
> 2. Let $x,y$ be jointly distributed. Then, define: $$W:=\mathbb{E}\left[ \begin{bmatrix}x\\y\end{bmatrix} \begin{bmatrix}x\\y\end{bmatrix}^\top\right] $$Then, clearly $0\leq W$ and we have that: $$\mathbb{E}[\braket{ x , Ay } ]=\mathbb{E}\left[ \left\langle W , \begin{bmatrix}0&A\\0&0\end{bmatrix}\right\rangle \right] $$
---
> [!lemma] Theorem 4 (Grothendieck's Inequality)
> Let $A\in \mathbb{R}^{n,n}$. Then, 
> 1. there exists a constant $k> 1$ s.t. $$\left\| A \right\| _{\text{cut}}\leq \left\| A \right\| _{\mathcal{G}}\leq k\left\| A \right\| _{\text{cut}}$$

---
##### 4.2 Community Detection with Grothendieck
> [!lemma] Theorem 1
> Consider the polytime estimator:
>  $$\widehat{X}:=\underset{ \text{rnk}(X)\leq 1 }{ \arg\min }\left\| X-Y \right\| ^{2}_{F},\quad Y:= I+\frac{1}{\varepsilon }\left( \frac{n}{d}A-1 \right)$$where $A$ is the adjacency matrix of $G$.
> 1. if $d\geq \Omega( 1/ \varepsilon^{2})$.  then w.h.p $\text{err}(\widehat{X})\le 0.01$.

> [!proof]-
> We have that: 
> 1. **Claim 1**: $\left\| \widehat{X}-X^0 \right\|^{2}_{F}\leq 4\left\| Y-X ^0\right\|_{G}$
>    As $Y-\widehat{X}=(Y-X^0)+(X^0-\widehat{X})$, we have that: $$\begin{aligned}\left\| \widehat{X}-X^0 \right\|^{2}_{F}&=\underbrace{ \left\| Y-\widehat{X} \right\| ^{2}_{F}-\left\| Y-X^0 \right\| ^{2}_{F} }_{ \leq 0 }-2\braket{ Y-X^0 , X^0-\widehat{X} } \\&\leq 2(\left| \braket{ X^0, Y-X^0 }  \right|+\left| \braket{ \widehat{X}, Y-X^0 }  \right| )\end{aligned} $$As $X^0,\widehat{X}$ are both in $\mathcal{C}_{G}:=\{ W^{(1,2)}:0\leq W\in \mathbb{R}^{2n,2n},\text{diag}(W)=1 \}$, we have that: $$\left\| \widehat{X}-X^0 \right\| ^{2}_{F}\leq 4\left\| Y-X^0 \right\| _{G}$$
> 2. **Claim 2**: $\left\| Y-X^0 \right\|_{\text{cut}}\leq 0.001 n^{2}$ **whp.**
>    Let $u,v\in \{ \pm 1 \}^{n}$. Then, from the earlier proof:$$\braket{ u , (Y-X^0)v } =\sum_{i<j}\braket{ u , Z^{(i,j)}v } =\sum_{i<j}^{}\underbrace{ (Y_{ij}-X^0_{ij})(u_{i}v_{j}+u_{j}v_{i} }_{ =:z^{ij} })$$Then, by Bernstein, we have $\mathbb{E}[z^{ij}]=0$ and $$\left| z^{ij} \right| \leq \frac{2n}{\varepsilon d}$$and $$\mathbb{E}[(z^{ij})^{2}]\leq \frac{8n}{\varepsilon^{2} d}$$Hence, $\mathbb{E}\left[ \sum_{i<j}^{}(z^{ij})^{2} \right]\leq \frac{8n^3}{\varepsilon^{2} d}$ and by Bernstein, with probability $\geq 1-2^{-3n}$, we have: $$\braket{ u , (Y-X^0)v } \lesssim \frac{n^{3/2}}{\varepsilon d^{1/2}}\sqrt{ n  } +\frac{n^{2}}{\varepsilon d}\lesssim \frac{n^2}{\varepsilon}\left( \frac{1}{\sqrt{ d }} \right) \lesssim n^{2}$$Therefore, by union bound, $\left\| Y-X^0 \right\|_{\text{cut}}> 0.0001n^{2}$ with probability $2^{2n}\cdot 2^{-3n}=2^{-n}$. 
> 
> Therefore, by Grothendieck:$$\text{err}(\widehat{X})=\frac{1}{n^{2}}\left\| \widehat{X}-X^0 \right\| ^{2}_{F}\leq \frac{4}{n^{2}}\left\| Y-X^0 \right\| _{G}\leq \frac{8}{n^{2}}\left\| Y-X^0 \right\| _{\text{cut}}\leq 0.01$$

---
### 5. Non-Negative Matrix Factorization
##### 5.1 Topic Models
> [!outlook] Setup
> Let $k,n,d,L\geq 1$.
> 1. **Unknown**: 
> 	- $A:=[A_{1}|\dots|A_{k}]\in\mathbb{R}^{d,k}_{\geq 0}$ where $\left\| A_{i} \right\|_{1}=1$. 
> 	- $W:=[W_{1}|\dots|W_{n}]\in \mathbb{R}^{k,n}_{\geq 0}$ where $\left\| W_{i} \right\|_{1}=1$.
> 	- $M:=[M_{1}|\dots|M_{n}]:=AW\in \mathbb{R}^{d,n}_{\geq 0}$
> 2. **Observation**: $D:=[D_{1}|\dots|D_{n}]\in \mathbb{R}^{d,n}_{\geq 0}$ where $D_{i}(j):=\frac{1}{L}\sum_{\ell\in [L]}[x_{i,\ell}=j]$ where $x_{i,1},\dots,x_{i,L}\sim M_{i}$ i.i.d.
> 3. **Goal**: Estimate $A$, up to permutations of the columns. 

- **Remark**: Notice that $\left\| M_{i} \right\|_{1}=\sum_{j\in[d]}^{}(AW)_{i,j}=\sum_{j\in [d]}^{}\sum_{p\in [k]}^{}A_{ip}W_{pj}=\sum_{p\in [k]}^{}A_{ip}=1$.
- **Remark**: If $L\gg d$, then $\mathbb{E}[D_{i}]=M_{i}$. However, we usually have that $L\ll d\ll n$.
- **Remark**: the SVD of $D$ does not work as for any invertible $R\in \mathbb{R}^{k,k}$, we have that $M=AW=(AR)(R^{-1}W)$. 
---
> [!definition] 
> For a matrix $M\in \mathbb{R}^{d,n}$, 
> 1. a ***rank-$k$ nonnegative matrix factorization (NMF)*** is a pair $(A,W)\in \mathbb{R}^{d,k}_{\geq 0}\times \mathbb{R}^{k,n}_{\geq 0}$ with $$M=AW$$
---
> [!lemma] Proposition 1
> Let $M$ be a column stochastic matrix with a rank-$k$ NMF. 
> 1. There exists an rank-$k$ NMF $(A,W)$ of $M$ s.t. $A,W$ are column stochastic. 

- **Remark**: If $W$ is column stochastic, the columns of $M$ are convex combinations of the columns of $A$. Hence, $M$ from our setting admits a rank-$k$ NMF if and only if there exists a $k$-corner polytope with non-negative coordinates that covers all the columns of $M$. This is however $NP$-hard.

---
- **Related definition**: A matrix $A$ is separable if $e_{1},\dots,e_{k}$ is in the rows of $A$ up to scaling. Further, word $i$ is an ***anchor*** for topic $j$ if row $i$ of $A$ is a multiple of $e_{j}$.
---
> [!lemma] Theorem 2
> Let $M=AW$ for a separable $A$ and full-rank $W$ and $M,A,W$ are column stochastic.
> Consider the following polytime algorithm given $M$:
> 1. Rescale the rows of $M$ to sum up to $1$.
> 2. Find the corners of the $\text{conv}(M_{1,:},\dots,M_{d,:})$ and set them to be the rows of $W$.
> 3. Solve the linear system $M=AW$ to find $A$.
> 
> Then, this algorithm returns $A$ up to permutation of the columns.

> [!proof]-
> As we rescale the rows of $M$, we may assume wlog that the rows of $A,W$ sum up to $1$ as well. Especially, rows of $M$ are a convex combination of rows of $W$. However, as $A$ is separable, the rows of $W$ are all contained in the rows of $M$. Notice that they are exactly the corners of the convex hull as $W$ is full-rank. This proves the theorem.
---
> [!lemma] Theorem 3
> Let $L\ll d\ll n$. 
- 