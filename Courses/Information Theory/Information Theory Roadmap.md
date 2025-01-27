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
#### 3.2 Log-Sum Inequality
![[Technical Lemmas#^676db7]]
![[Technical Lemmas#^af9688|p]]

---
![[Relative Entropy#^0ed2a9]]
![[Relative Entropy#^ab9003|p]]

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
