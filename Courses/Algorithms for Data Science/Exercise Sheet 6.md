#Series #Algorithms 
#### Problem 1
1. We have that: $$\braket{ \widehat{x} , x^{*} } =\sum_{i\in[n]}^{} \widehat{x}_{i}x^{*}_{i}=N_{\geq }+(-1)N_{\leq}=N_{\geq} - N_{\leq}$$This shows the statement.
2. Let $S_{\geq }:=\{ i\in[n]:\widehat{x}_{i}x^{*}_{i}=1 \}$ and $S_{\leq }:=\{ i\in[n]:\widehat{x}_{i}x^{*}_{i}=-1 \}$. This forms a partition $[n]=S_{\geq}\sqcup S_{\leq}$. Now, let $\Delta:=(S_{\geq }\times S_{\leq})\sqcup (S_{\leq }\times S_{\geq})\subseteq[n]^{2}$ be the set of pairs $(i,j)$ s.t. they belong in different sets in the partition. 
   
   Then, notice that:$$\left\| X-X^{*} \right\| ^{2}_{F}=\sum_{i,j\in[n]}^{}\underbrace{ (x_{i}x_{j}-x^{*}_{i}x^{*}_{j})^{2} }_{ \geq 0 }\geq \sum_{(i,j)\in \Delta}^{}(x_{i}x_{j}-x^{*}_{i}x^{*}_{j})^{2}$$Now, using that $\widehat{x}_{i}:= \text{sgn}(x_{i})=x_{i} / \left| x_{i} \right|$ for all $i$, notice that if $(i,j)\in \Delta$,  $$(x^{*}_{i}x^{*}_{j}-x_{i}x_{j})^{2}\geq \underbrace{ (x^{*}_{i})^{2} }_{ =1 }\underbrace{ (x^{*}_{j})^{2} }_{ =1 }-2x_{i}x_{j}x^{*}_{i}x^{*}_{j}=1-2\left| x_{i} \right| \left| x_{j} \right| \underbrace{ \widehat{x}_{i}x^{*}_{i}\widehat{x}_{j}x^{*}_{j} }_{ =-1 }=1+2\left| x_{i} \right| \left| x_{j} \right| \geq 1$$Therefore, we conclude that $\left\| X-X^{*} \right\|^{2}_{F}\geq \left| \Delta \right|=2\left| S_{\geq} \right|\left| S_{\leq} \right|=2N_{\geq}N_{\leq}$. 


3. Let $\left\| X-X^{*} \right\|_{F}\leq 0.1n$. Then, $2N_{\geq}N_{\leq}\leq 0.01n^{2}$. Hence, $$\braket{ \widehat{x} , x^{*} } ^{2}=(N_{\geq }-N_{\leq})^{2}=(N_{\geq}+N_{\leq})^{2}-4N_{\geq}N_{\leq}\geq n^{2}-0.02n^{2}=0.98n^{2}$$This proves the statement.

---
#### Problem 2
We define $Y:=Y(G)\in \mathbb{R}^{n,n}$ as follows: $$Y_{ij}:=\begin{cases}\alpha_{1}:=\frac{1}{\varepsilon}\left( \frac{n}{d} -1\right)&ij\in E(G)\\\alpha_{0}:= -\frac{1}{\varepsilon} &ij\notin E(G)\\r-1&i=j\end{cases}$$Then, $\alpha_{1}-\alpha_{0}=\frac{1}{\varepsilon}\frac{n}{d}$ and$$\begin{aligned}\mathbb{E}[Y_{ij}]&=\mathbb{P}(ij\in E(G))(\alpha_{1}-\alpha_{0})+\alpha_{0}=(1+X^{*}_{ij}\varepsilon) \frac{1}{\varepsilon}-\frac{1}{\varepsilon}=X^{*}_{ij},\quad \forall i\neq j\end{aligned}$$Hence, $\mathbb{E}[Y]=X^{*}$. We now claim that $\widehat{X}:=\arg\min\{ \left\| X-Y \right\|^{2}_{F}|\text{rk}(X)\leq 1 \}$ satisfies the condition. Notice that $\widehat{X}$ can be computed efficiently using SVD. Now, by single spike model, we have that: $$\left\| \widehat{X}-X^{*} \right\| ^{2}_{F}\leq 10\left\|Y-X^{*}  \right\|^{2} $$Hence, it suffices to show that w.h.p $\left\| Y-X^{*} \right\|^{2}\leq 0.001 \left\| X^{*} \right\|^{2}_{F}$. Let $Z^{ij}:=(Y_{ij}-X^{*}_{ij})(e_{i}e_{j}^\top+e_{j}e_{i}^\top)$.

Let $i< j$. 
1. if $ij\in E(G)$, as $\mathbb{P}(ij\in E(G))\leq 1$, we have $r-1\leq \frac{1}{\varepsilon}\left( \frac{n}{d}-1 \right)$ and it follows that: $$\left| Y_{ij}-X^{*}_{ij} \right| =\left| \frac{1}{\varepsilon}\left( \frac{n}{d}-1 \right)-X^{*}_{ij}\right|\leq \frac{1}{\varepsilon}\left( \frac{n}{d}-1 \right)+1\leq \frac{n}{\varepsilon d}$$
2. if $ij\notin E (G)$ and $x_{i}^{*}= x^{*}_{j}$: $$\left| Y_{ij}-X^{*}_{ij} \right| =\left| -\frac{1}{\varepsilon}-r+1\right|=r-1+\frac{1}{\varepsilon}\leq \frac{1+\varepsilon(r-1)}{\varepsilon} $$
3. if $ij\notin E(G)$ and $x_{i}^{*}\neq x^{*}_{j}$: $$\left| Y_{ij}-X^{*}_{ij} \right| =\left| -\frac{1}{\varepsilon}+1 \right| =\frac{1}{\varepsilon}-1\leq  \frac{1-\varepsilon}{\varepsilon}\leq \frac{1+\varepsilon(r-1)}{\varepsilon}$$
   
Hence, by setting $b:= \frac{(1+\varepsilon(r-1)) n}{\varepsilon d}$, we have that $\left\| Z^{ij} \right\|=\left| Y_{ij}-X^{*}_{ij} \right|\leq b$. Further, $$$$


1. if $x^{*}_{i}=x^{*}_{j}$, then: $$\begin{aligned}\mathbb{E}[(Y_{ij}-X_{ij}^{*})^{2}]&=\mathbb{P}(ij\in E(G))(\underbrace{ \alpha_{1}-r+1 }_{ \in [0,\alpha_{1}] })^{2}+\mathbb{P}(ij\notin E(G))\left( 1-\frac{1}{\varepsilon}-r \right)^{2}\\&\leq (1+(r-1)\varepsilon) \cdot \frac{d}{n}\cdot  \frac{1}{\varepsilon^{2}}\left( \frac{n}{d}-1 \right)^{2}+\left( r-1+\frac{1}{\varepsilon} \right)^{2}\end{aligned}$$
2. if $i\neq j$ and $x^{*}_{i}\neq x^{*}_{j}$, then: $$\begin{aligned}\mathbb{E}[(Y_{ij}-X_{ij}^{*})^{2}]&=\mathbb{P}(ij\in E(G))( \alpha_{1}+1 )^{2}+\mathbb{P}(ij\notin E(G))\left( 1-\frac{1}{\varepsilon} \right)^{2}\\&\leq (1-\varepsilon) \cdot \frac{d}{n}\cdot  \frac{1}{\varepsilon^{2}}\left( \frac{n}{d}-1 \right)^{2}+\left( r-1+\frac{1}{\varepsilon} \right)^{2}\end{aligned}$$
3. $$\mathbb{E}[(Y_{ij}-X^{*}_{ij})^{2}]\leq (1+(r-1)\varepsilon) \frac{1}{\varepsilon^{2}}\left( \frac{n}{d}-1 \right)^{2}+\frac{1}{\varepsilon}  $$ $$\mathbb{E}[Z^{ij}(Z^{ij})^\top]=\mathbb{E}[(Y_{ij}-X^{*}_{ij})^{2}](e_{i}e_{j}^\top+e_{j}e_{i}^\top)\leq$$