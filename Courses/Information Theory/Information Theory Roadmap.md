#InformationTheory #Roadmap 

### 0. Probability Basics
#### 0.1 Lemmas
![[Expected Value#^d75029]]
![[Expected Value#^36878b|p]]

---
![[Expected Value#^0e786a]]
![[Expected Value#^f56d8e|p]]

---
![[Technical Lemmas#^e84229]]
![[Technical Lemmas#^d6a2dd|p]]

---
#### 0.2 Convergence in Probability
> [!definition] 
> Let $X_{1},\dots,X_{n},X$ be random variables. Then, 
> 1. $X_{n}$ ***converges to $X$ almost surely***, if $\mathbb{P}(\lim_{ n \to \infty }X_{n}=X)=1$.
> 2. $X_{n}$ ***converges to $X$ in probability***, if for all $\varepsilon>0$, $$\lim_{ n \to \infty } \mathbb{P}(\left| X_{n}-X \right| > \varepsilon)=0$$
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. if $X_{n}\to X$ almost surely, then $X_{n}\to X$ in probability.

> [!proof]-
> See [[Convergence in Measure|Theorem 1]].
---
> [!lemma] Theorem 2 (Weak LLN)

---
### 1. Basic Definitions
#### 1.1 Entropy
![[Entropy#^2cc2de]]
![[Entropy#^09ddcf]]

---
![[Entropy#^bf1bbb]]
![[Entropy#^049dcb|p]]

---
![[Entropy#^1d6ace]]

---
##### 1.1.2 Relative Entropy

![[Relative Entropy#^c8e329]]

---
![[Relative Entropy#^c12de7]]
![[Relative Entropy#^819eb1|p]]

---
![[Relative Entropy#^e6cf2f]]
![[Relative Entropy#^9f110f|p]]

---
![[Entropy#^4eec02]]
![[Entropy#^6a94ef|p]]

---
![[Entropy#^f62e41]]
![[Entropy#^8e99d6|p]]

---
##### 1.1.3 Mutual Information
![[Mutual Information#^b7d647]]

---
![[Mutual Information#^f92807]]
![[Mutual Information#^7e7455|p]]

---
![[Entropy#^8e1dbc]]
![[Entropy#^38bd1d|p]]

---
![[Mutual Information#^3fabf6]]
![[Mutual Information#^8b584b|p]]

---
![[Mutual Information#^569dc2]]
![[Mutual Information#^612399|p]]

---
##### 1.1.4 Fano's Inequality
![[Entropy#^730b6a]]
![[Entropy#^9dcdf7|p]]

---
### 2. Source Codes
![[Code#^bc3afd]]
![[Code#^a0f71e]]
![[Code#^f40365|q]]
![[Code#^e75eeb|q]]
![[Code#^8239b2|q]]
![[Code#^92dedb|q]]

---
![[Code#^866846]]
![[Code#^dd6b98|p]]

---
![[Code#^25cc1f]]
![[Code#^74678f|p]]

---
![[Code#^c8b0bf]]
![[Code#^0a6de9|p]]
![[Code#^7f2436]]

---
![[Code#^c590a0]]
![[Code#^a729b7|p]]

---
#### 2.1 Huffman Coding and Arithmetic Coding
![[Code#^eb82e8]]
![[Code#^6a34a3|p]]

---
![[Code#^816bcd]]
![[Code#^9ef8e6|p]]
![[Code#^5c5f45]]

---
#### 2.2 Shannon Coding
![[Code#^8f4e0a]]
![[Code#^f81c1c|p]]

---
### 3. Asymptotic Equipartition Property
#### 3.1 Typical Sequences
![[Typical Sequence#^a981a4]]
![[Typical Sequence#^331f26]]
![[Typical Sequence#^1b4717|q]]

---
![[Typical Sequence#^997b29]]
![[Typical Sequence#^d52844|p]]

---
![[Typical Sequence#^93c318]]
![[Typical Sequence#^067ee1|p]]

---
![[Typical Sequence#^012426]]
![[Typical Sequence#^d76625|p]]

---
![[Typical Sequence#^3cf8af]]
![[Typical Sequence#^d9ff78|p]]

---
> [!lemma] Theorem 6 
> Let $X_{1},..,X_{n}$ be i.i.d over a finite $\mathcal{X}$ with pmf $p$, where $H(p)=\log \pi$. For every $k\in \mathbb{Z}_{\geq 0}$ $$W_{k}:=2^{-k}\left\lfloor 2^k\cdot \left( \prod_{i=1}^{n}p(X_{i}) \right)^{1/n} \right\rfloor $$Then, $\lim_{ n \to \infty }H(W_{k})=0$.

> [!proof]-
> We have that: $$\log \left( \prod_{i=1}^{n}p(X_{i}) \right)^{1/n}=\frac{1}{n}\sum_{i=1}^{n}\log p(X_{i})\to -H(p)=-\log \pi$$in probability. Hence by continuity, $$\left( \prod_{i=1}^{n}p(X_{i}) \right)^{1 / n} \to \frac{1}{\pi}$$in probability. Hence, for any $\varepsilon>0$, $$\lim_{ n \to \infty } \mathbb{P}\left( \left| \left( \prod_{i=1}^{n}p(X_{i}) \right)^{1/n}- \frac{1}{\pi} \right| >\varepsilon \right)=0$$As $1 / \pi$ is irrational, for a fixed $k$, there always will be $\varepsilon$ small enough s.t. 
---
#### 3.2 Log-Sum Inequality
![[Technical Lemmas#^676db7]]
![[Technical Lemmas#^af9688|p]]

---
![[Relative Entropy#^0ed2a9]]
![[Relative Entropy#^ab9003|p]]

---
#### 3.3 Shearer's Lemma
> [!lemma] Theorem 1 (Shearer)
> Let $\mathcal{F}$ be a family of subsets of $[n]$ with each $i\in[n]$ included in at least $t$ members of $\mathcal{F}$. For a random vector $(X_{1},\dots,X_{n})$, $$H(X_{1},\dots,X_{n})\leq \frac{1}{t}\sum_{F\in \mathcal{F}}^{}H(X_{F})$$

> [!proof]-
> We write $F:=\{ i_{1},\dots,i_{k} \}$ with $i_{1}<i_{2}<\dots< i_{k}$. Then, $$H(X_{F})=H(X_{i_{1}},\dots,X_{i_{k}})=\sum_{j=1}^{k}H(X_{i_{j}}|X_{i_{1:j-1}})\geq \sum_{j=1}^{k}H(X_{i_{j}}|X_{1},\dots,X_{i_{j}-1})$$Therefore, $$\sum_{F\in \mathcal{F}}^{}H(X_{F})\geq t\sum_{j=1}^{n}H(X_{j}|X_{1},\dots,X_{j-1})=t\cdot H(X_{1},..,X_{n})$$
> 
---
### 4. Channel Coding
#### 4.1 DMC
![[Discrete Memoryless Channel (DMC)#^caee85]]
![[Discrete Memoryless Channel (DMC)#^1491bf]]

---
![[Discrete Memoryless Channel (DMC)#^bc8814]]
![[Discrete Memoryless Channel (DMC)#^67dcbf|p]]

---
![[Discrete Memoryless Channel (DMC)#^0b1214]]
![[Discrete Memoryless Channel (DMC)#^2662b0|p]]

---
![[Mutual Information#^eb14f8]]
![[Mutual Information#^986f22|p]]

---
![[Discrete Memoryless Channel (DMC)#^21b4e0]]
![[Discrete Memoryless Channel (DMC)#^3b43b6|q]]

---
![[Discrete Memoryless Channel (DMC)#^79c0ff]]

---
![[Discrete Memoryless Channel (DMC)#^45755d]]
![[Discrete Memoryless Channel (DMC)#^45d60f|p]]

---
![[Discrete Memoryless Channel (DMC)#^5ed592]]
![[Discrete Memoryless Channel (DMC)#^fe29b9|p]]

---
![[Discrete Memoryless Channel (DMC)#^54476c]]
![[Discrete Memoryless Channel (DMC)#^dac41a|p]]

---
![[Discrete Memoryless Channel (DMC)#^9f9b95]]

---
![[Discrete Memoryless Channel (DMC)#^ca15d1]]
![[Discrete Memoryless Channel (DMC)#^39768b|p]]

---
![[Discrete Memoryless Channel (DMC)#^16812e]]
![[Discrete Memoryless Channel (DMC)#^9d31e1|p]]

---
![[Discrete Memoryless Channel (DMC)#^84bff1]]
![[Discrete Memoryless Channel (DMC)#^dd8236|p]]

---
![[Discrete Memoryless Channel (DMC)#^f9cb80]]
![[Discrete Memoryless Channel (DMC)#^2e8a65|p]]

---
![[Discrete Memoryless Channel (DMC)#^dec724]]
![[Discrete Memoryless Channel (DMC)#^836fb4|p]]

---
![[Discrete Memoryless Channel (DMC)#^536f0b]]
![[Discrete Memoryless Channel (DMC)#^cba0cb|p]]

---
> [!h] Example 10
> Consider the DMC given by: $$W:=\begin{bmatrix}1&0\\ \frac{1}{2}& \frac{1}{2}\\ \frac{2}{3}& \frac{1}{3}\end{bmatrix}$$Then, $C(W)$

> [!proof]+
> Let $q=(a,b,c)$. We show that it suffices to assume that $c=0$. Let $q':=\left( a+\frac{1}{3}c,b+\frac{2}{3}c,0 \right)$. Then, $qW=q'W$ and: $$\begin{align}I(q',W)&=H(q'W)-\left( a+\frac{1}{3}c \right)H(W(\cdot |0))-\left( b+\frac{2}{3}c \right)H(W(\cdot |1))\end{align}$$Then, we have that by concavity: $$\frac{1}{3}H(W(\cdot |0))+\frac{2}{3}H(W(\cdot |1))\leq H\left( W(\cdot |2) \right)$$Hence, $I(q',W)\geq H(qW)-aH(W(\cdot|0))-bH(W(\cdot|1))-cH(W(\cdot|2))=I(q,W)$. This proves the claim. 
> 
> 
---
#### 4.2 Feedback
![[Discrete Memoryless Channel (DMC)#^ec9f89]]
![[Discrete Memoryless Channel (DMC)#^1f04d3|p]]

---
#### 4.3 Source Channel Separation
> [!lemma] Theorem 1 (Source Channel Separation Theorem)
> Let $\mathcal{U}$ be a finite alphabet. A ***source channel code*** consists of the following maps: $$\begin{array}{ccccc}
\mathcal{U}^n&\xrightarrow{f}& \mathcal{X}^n&\xrightarrow{W}&\mathcal{Y}^n &\xrightarrow{\phi} &\mathcal{U}^n&\\U_{1:n}&\mapsto &X_{1:n}(U_{1:n})&\mapsto &Y_{1:n}&\mapsto &\widehat{U}_{1:n}
\end{array}$$
> with the probability of error defined as:$$P^n_{e}:=\mathbb{P}(U_{1:n}\neq \widehat{U}_{1:n})=\sum_{y_{1:n}\in \mathcal{Y}^n}^{}\sum_{u_{1:n}\in \mathcal{U}^n}p(u_{1:n})p(y_{1:n}|x_{1:n}(u_{1:n}))\cdot \mathbb{1}_{\{ \phi (y_{1:n})\neq u_{1:n}\}}$$Then, 
> 1. if $U_{1},\dots,U_{n}\sim p$ i.i.d and $H(p)<C(W)$, there exists a source channel code with $P^n_{e}\to 0$.
> 2. if $H(p)>C(W)$, then $\lim_{ n \to \infty }P^n_{e}\neq 0$. 

> [!proof]-
> We have:
> 1. Notice that from [[Typical Sequence|AEP]], $\left| \mathcal{A}^n_{\varepsilon}(p) \right|\leq 2^{n(H(p)+\varepsilon)}$. Hence, we can only use $n(H(p)+\varepsilon)$ bits to transfer them.  Therefore, we use $\mathcal{U}^n\to \mathcal{M}_{n(H(p)+\varepsilon)}\to \mathcal{X}^n$ where the first map maps the weakly typical sequences and discards the rest.
>    
>    Hence, if $H(p)<C(W)$, there exists $\varepsilon>0$ s.t. $R:=H(p)+\varepsilon<C$. Then, the receiver can enumerate $\mathcal{A}^n_{\varepsilon}$ and choose the sequence corresponding to the index. Now, as $R<C$, there exists $(f_{n},\phi_{n})$ a $(\mathcal{M},R)$-code. 
>    
>    Then, for $n$ large enough, $$P^n_{e}=\mathbb{P}(U^n\notin \mathcal{A}^n_{\varepsilon}(p))+\mathbb{P}(\phi(Y^n)\neq U^n|U^n\in \mathcal{A}^n_{\varepsilon})\leq2\varepsilon$$and we have that $P^n_{e}\to 0$. 
> 2. Conversely, we will show that $P^n_{e}\to 0$ implies $H(p)\leq C$. By Fano, we have: $$H(U_{1:n}|\widehat{U}_{1:n})\leq 1+P^n_{e}\cdot n\cdot \log \left| \mathcal{U} \right| $$Hence, $$\begin{align} H(p)&\leq \frac{H(U_{1:n})}{n}\leq\frac{1}{n}I(U_{1:n};\widehat{U}_{1:n})+\frac{1}{n}+P^n_{e} \cdot \log \left| \mathcal{U} \right| \\&\leq\frac{1}{n}I(X_{1:n};Y_{1:n})+\frac{1}{n}+P^n_{e} \cdot \log \left| \mathcal{U} \right| \\&\leq C(W)+\frac{1}{n}+P^n_{e}\cdot \log \left| \mathcal{U} \right| \end{align}$$Hence, $H(p)\leq C(W)$.

- **Corollary**: This can be extended to the case where the number of source symbols and number of channel uses differ. In that case the condition becomes $H(p)\rho_{S}<C\rho_{C}$ where $\rho_{S}$ measures the number of source symbols per second and $\rho_{C}$ measures the number of channel uses per second. 
- **Related definition**: ***Symbol error rate*** talks about $\frac{1}{k}\sum_{i}^{}\mathbb{P}(U_{i}\neq \widehat{U}_{i})$ instead of $P^n_{e}$. However, for symbol error rate, the same conditions as the theorem apply. 
---
> [!lemma] Theorem 2 (Source Channel For Multiple Inputs)
> A memoryless binary source emits $\text{Ber}(p)$ symbols at a rate of $\rho_{s}$ source-symbols-per-second. Independently of that, binary data are generated i.i.d $\text{Ber}(0.5)$ at rate $R_{\text{data}}$ data-bits-per second. To transmit the source sequence and the data sequence, a $\text{BSC}(\varepsilon)$ can be used $\rho_{c}$ times per second.
> 1. if $\rho_{s}H_{b}(p)+R_{\text{data}}<\rho_{C}\cdot (1-H_{p}(\varepsilon))$, then there exists a source channel code with $P^n_{\varepsilon}\to 0$.
> 2. if $\rho_{s}H_{b}(p)+R_{\text{data}}> \rho_{C}(1-H_{p}(\varepsilon))$, then $\lim_{ n \to \infty }P^n_{\varepsilon}\neq 0$.

> [!proof]-
> We have that:
> 1. We construct the following scheme:
> 	1. encode input $U^{t\cdot\rho_{s}}$ with $n_{1} H_{b}(p)$ bits and denote the result by $M_{1}$. 
> 	2. concatenate $M_{1}$ with $V^{t\cdot R_{\text{data}}}$ and get $M$ of length $n_{1}H_{b}(p)+tR_{\text{data}}$.
> 	3. transfer $M$ through channel and get $\widehat{M}$.
> 	4. split $\widehat{M}$ into $\widehat{M}_{1}$ and $\widehat{V}^{t\cdot R_{\text{data}}}$.
> 	5. decode $\widehat{U}^{t\cdot p_{s}}$ from $\widehat{M}_{1}$. 
> 	   
> 	Then, we have that: $$\begin{align}P^n_{\varepsilon}&\leq \mathbb{P}(U^{n_{1}}\neq \widehat{U}^{n_{1}})+\mathbb{P}(V^{n_{2}}\neq\widehat{V}^{n_{2}})\\&\leq \mathbb{P}(M_{1}\neq \widehat{M}_{1})+\mathbb{P}(U^{n_{1}}\neq \widehat{U}^{n_{1}}|M_{1}=\widehat{M}_{1})+\mathbb{P}(V^{n_{2}}\neq \widehat{V}^{n_{2}})\\&=\mathbb{P}(M\neq \widehat{M})+\mathbb{P}(U^{n_{1}}\neq \widehat{U}^{n_{1}}|M_{1}=\widehat{M}_{1})\end{align}$$Notice that: 
> 2. For converse, if $\mathbb{P}(U^{n_{1}}\neq \widehat{U}^{n_{1}}\lor V^{n_{2}}\neq \widehat{V}^{n_{2}})<\delta$, then the individual events are also bounded by $\delta$ and by Fano, $$H(U^{n_{1}}|\widehat{U}^{n_{1}})\leq 1+\delta n_{1},\quad H(V^{n_{2}}|\widehat{V}^{n_{2}})\leq 1+\delta n_{2}$$Hence, by data processing: $$\begin{align}I(X^{n_{3}};Y^{n_{3}})&\geq I(U^{n_{1}},V^{n_{2}};\widehat{U}^{n_{1}},\widehat{V}^{n_{2}})\\&=H(U^{n_{1}},V^{n_{2}})-H(U^{n_{1}},V^{n_{2}}|\widehat{U}^{n_{1}},\widehat{V}^{n_{2}})\\&=H(U^{n_{1}})+H(V^{n_{2}})-H(U^{n_{1}}|\widehat{U}^{n_{1}})-H(V^{n_{2}}|\widehat{U}^{n_{1}},\widehat{V}^{n_{2}})\\&\geq H(U^{n_{1}})+H(V^{n_{2}})-H(U^{n_{1}}|\widehat{U}^{n_{1}})-H(V^{n_{2}}|\widehat{V}^{n_{2}})\\&\geq n_{1}H_{b}(p)+n_{2}-1-\delta n_{1}-1-\delta n_{2}\\&=t(\rho_{s}H_{b}(p)+R_{\text{data}}-\delta\rho_{s}-\delta R_{\text{data}})-2\end{align}$$where $I(X^{n_{3}};Y^{n_{3}})\leq n_{3}(1-H_{b}(\varepsilon))$. Therefore, $$\rho_{S}H_{b}(p)+R_{\text{data}}\leq \rho_{c}(1+H_{b}(\varepsilon))$$
---
### 5. Rate Distortion Theory

![[Distortion#^97cce4]]
![[Distortion#^773ed2]]
![[Distortion#^62f7b8|q]]
![[Distortion#^d477f3|q]]

---
![[Distortion#^12f644]]
![[Distortion#^4e63b5|p]]

---
![[Distortion#^1bb529]]
![[Distortion#^a1d9ae|p]]

---
![[Distortion#^b3795d]]
![[Distortion#^540794|p]]

---
![[Distortion#^412c24]]
![[Distortion#^0f936d|p]]

---
![[Distortion#^a63827]]
![[Distortion#^00635f|p]]

---
![[Distortion#^8fd3b7]]
![[Distortion#^93d3ce|p]]

---
![[Distortion#^389ab1]]
![[Distortion#^6181cf|p]]

---
![[Distortion#^d42208]]
![[Distortion#^45ac3c|p]]

---
![[Distortion#^898bec]]
![[Distortion#^1a38d4|p]]

---
![[Distortion#^b26a0f]]
![[Distortion#^ba7db9|p]]

---
> [!h] Example 6
> Let $\mathcal{X}:=\{ 0,1 \}$ with $X\sim \text{Ber}(p)$ and $\mathcal{Y}:=\{ 0,1,5 \}$. For distortion function $d(x,y):=2\left| x-y \right|$, 
> 1. $R(D)=\begin{cases}H_{b}(p)-H_{b}(D /2)& D\leq 2\min \{ p,1-p \}\\0&D\geq 2 \min \{ p,1-p \}\end{cases}$

> [!proof]-
> We claim that in the optimal scheme, symbol $5$ is never used, i.e. $$R(D)=\min_{p_{Y|X}: \mathbb{E}[d(X,Y)]<D}I(X;Y)=\min_{p_{Y|X}: \mathbb{E}[d(X,Y)]<D, p_{Y|X}(5|i)=0, i=0,1}I(X;Y)$$Let us define a function $f:\mathcal{Y}\to \mathcal{Y}$ where $f|_{\{ 0,1 \}}=\text{id}$ and $f(5)=1$. Then, $(X,Y,f(Y))$ forms a Markov chain and the transition matrix is given by: $$p'_{Y|X}(y|x)=\begin{cases}p_{Y|X}(0|x)&y=0\\p_{Y|X}(1|x)+p_{Y|X}(5|x)&y=1\\0&y=5\end{cases}$$Then, $d(x,f(y))\leq d(x,y)$ and we have: $\mathbb{E}[d(X,f(Y))]\leq \mathbb{E}[d(X,Y)]$. Further, by data processing: $$I_{p'}(X;Y)=I_{p}(X;f(Y))\leq I_{p}(X;Y)$$Therefore, $$\min_{p_{Y|X}: \mathbb{E}[d(X,Y)]<D}I(X;Y)\geq\min_{p_{Y|X}: \mathbb{E}[d(X,Y)]<D, p_{Y|X}(5|i)=0, i=0,1}I(X;Y)$$The other inequality is trivial. 
---
