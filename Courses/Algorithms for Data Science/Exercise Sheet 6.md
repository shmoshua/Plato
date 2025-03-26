#Series #Algorithms 
#### Problem 1
1. We have that: $$\braket{ \widehat{x} , x^{*} } =\sum_{i\in[n]}^{} \widehat{x}_{i}x^{*}_{i}=N_{\geq }+(-1)N_{\leq}=N_{\geq} - N_{\leq}$$This shows the statement.
2. Let $S_{\geq }:=\{ i\in[n]:\widehat{x}_{i}x^{*}_{i}=1 \}$ and $S_{\leq }:=\{ i\in[n]:\widehat{x}_{i}x^{*}_{i}=-1 \}$. This forms a partition $[n]=S_{\geq}\sqcup S_{\leq}$. Now, let $\Delta:=(S_{\geq }\times S_{\leq})\sqcup (S_{\leq }\times S_{\geq})\subseteq[n]^{2}$ be the set of pairs $(i,j)$ s.t. they belong in different sets in the partition. 
   
   Then, notice that:$$\left\| X-X^{*} \right\| ^{2}_{F}=\sum_{i,j\in[n]}^{}\underbrace{ (x_{i}x_{j}-x^{*}_{i}x^{*}_{j})^{2} }_{ \geq 0 }\geq \sum_{(i,j)\in \Delta}^{}(x_{i}x_{j}-x^{*}_{i}x^{*}_{j})^{2}$$Now, using that $\widehat{x}_{i}:= \text{sgn}(x_{i})=x_{i} / \left| x_{i} \right|$ for all $i$, notice that if $(i,j)\in \Delta$,  $$(x^{*}_{i}x^{*}_{j}-x_{i}x_{j})^{2}\geq \underbrace{ (x^{*}_{i})^{2} }_{ =1 }\underbrace{ (x^{*}_{j})^{2} }_{ =1 }-2x_{i}x_{j}x^{*}_{i}x^{*}_{j}=1-2\left| x_{i} \right| \left| x_{j} \right| \underbrace{ \widehat{x}_{i}x^{*}_{i}\widehat{x}_{j}x^{*}_{j} }_{ =-1 }=1+2\left| x_{i} \right| \left| x_{j} \right| \geq 1$$Therefore, we conclude that $\left\| X-X^{*} \right\|^{2}_{F}\geq \left| \Delta \right|=2\left| S_{\geq} \right|\left| S_{\leq} \right|=2N_{\geq}N_{\leq}$. 


3. Let $\left\| X-X^{*} \right\|_{F}\leq 0.1n$. Then, $2N_{\geq}N_{\leq}\leq 0.01n^{2}$. Hence, $$\braket{ \widehat{x} , x^{*} } ^{2}=(N_{\geq }-N_{\leq})^{2}=(N_{\geq}+N_{\leq})^{2}-4N_{\geq}N_{\leq}\geq n^{2}-0.02n^{2}=0.98n^{2}$$This proves the statement.

---
#### Problem 2
We define $Y:=Y(G)\in \mathbb{R}^{n,n}$ as follows: $$Y_{ij}:=\begin{cases}\alpha_{1}:=\frac{1}{\varepsilon}\left( \frac{n}{d} -1\right)&ij\in E(G)\\\alpha_{0}:= -\frac{1}{\varepsilon} &ij\notin E(G)\end{cases}$$Then, $\alpha_{1}-\alpha_{0}=\frac{1}{\varepsilon}\frac{n}{d}$ and$$\begin{aligned}\mathbb{E}[Y_{ij}]&=\mathbb{P}(ij\in E(G))(\alpha_{1}-\alpha_{0})+\alpha_{0}=(1+X^{*}_{ij}\varepsilon) \frac{1}{\varepsilon}-\frac{1}{\varepsilon}=X^{*}_{ij}\end{aligned}$$