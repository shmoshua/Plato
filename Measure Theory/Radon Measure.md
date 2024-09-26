#Definition #MeasureTheory 

> [!definition]
> For a [[topological Space]] $X$, a ***Radon measure*** is a positive [[Borel measure]] $\mu:\mathcal{P}(X)\to[0,+\infty]$ s.t.
> 1. it is [[Borel Regular Measure|outer regular]] and [[Borel Regular Measure|inner regular for open sets]].
> 4. for every compact set $K \subseteq X$, $\mu(K)<\infty$.
---
##### Properties
> [!lemma] Theorem 1
> Let $\mu$ be a Radon measure on $\mathbb{R}^n$.
> 1. For every $A \subseteq \mathbb{R}^n$, it holds that $$\mu(A)=\inf\{ \mu(G):A \subseteq G, G\text{ open} \}$$
> 2. For every $\mu$-measurable set $A \subseteq \mathbb{R}^n$, it holds that $$\mu(A)=\sup \{ \mu(F): F \subseteq A, F\text{ compact}\}$$

> [!proof]-
> Let $A \subseteq \mathbb{R}^n$.
> 1. If $\mu(A)=+\infty$, then it holds trivially. Therefore, assume $\mu(A)<+\infty$.
>    
>      Firstly, assume that $A$ is Borel. Then, for any $\varepsilon>0$, there exists an open set $G \supseteq A$ s.t. $\mu(G \backslash A)<\varepsilon$. Therefore, $\mu(G)<\mu(A)+\varepsilon$. 
>      
>      If $A$ is not Borel, as $\mu$ is Borel regular, there exists a Borel set $B\in \mathcal{B}(\mathbb{R}^n)$ s.t. $A \subseteq B$ and $\mu(A)=\mu(B)$. Therefore, $$\mu(A)=\mu(B)=\inf\{ \mu(G):B \subseteq G,G\text{ open} \}\ge\inf\{ \mu(G):A \subseteq G,G\text{ open} \}$$
> 2. Let $A$ be $\mu$-measurable. We have two cases:
> 	1. If $\mu(A)<+\infty$, $\nu_{A}(\cdot)=\mu(A \cap \cdot)$ is a Radon measure. Then, for all $\varepsilon>0$, there exists an open set $G \supseteq \mathbb{R}^n \backslash A$ and: $$\nu_{A}(G)<\nu_{A}(\mathbb{R}^n \backslash A)+\varepsilon = \varepsilon$$
> 		Let $C := \mathbb{R}^n \backslash G$. Then, $C$ is closed and $C \subseteq A$.  Moreover, $$\mu(A \backslash C)=\mu(A\cap (\mathbb{R}^n \backslash C))=\nu_{A}(\mathbb{R}^n \backslash C)=\nu_{A}(G)<\varepsilon$$Therefore, $\mu(A)<\mu(C)+\varepsilon$. Therefore, $$\mu(A)=\sup\{ \mu(C):C\subseteq A, C \text{ closed} \}$$
> 	2. If $\mu(A)=+\infty$, we define $D_{k}:=\{ x: k-1\leq \left| x \right|<k \}$. Then, $A=\bigcup_{k=1}^{\infty}(D_{k}\cap A)$. Since $\mu$ is a Radon measure, $\mu(D_{k}\cap A)<+\infty$. Then, from case 1, it holds that for all $k$, there exists a closed set $C_{k} \subseteq D_{k }\cap A$ s.t. $$\mu(C_{k})\geq \mu(D_{k}\cap A)-\frac{1}{2^k}$$Then, $$\lim_{ m \to \infty } \mu \left(  \bigcup_{k=1}^{m}C_{k}\right)=\mu \left( \bigcup_{k=1}^{\infty}C_{k} \right) =\sum_{k=1}^{\infty}\mu(C_{k})\geq \sum_{k=1}^{\infty}\mu(D_{k}\cap A)-\frac{1}{2^k}\geq \mu(A)-1=\infty $$As $\bigcup_{k=1}^{m}C_{k}$ is closed for all $m$.
> 	
> 	If $C$ is closed, we have that $\mu(C)=\lim_{ m \to \infty }\mu(C \cap\overline{B(0,m)})$. This proves the statement.
---
> [!lemma] Theorem 2
> Let $\mu$ be a Radon measure on $\mathbb{R}^n$ and $A\subseteq \mathbb{R}^n$. The following two are equivalent:
> 1. $A$ is $\mu$-measurable.
> 2. For all $\varepsilon>0$, there exists an open set $G \supseteq A$ s.t. $\mu(G \backslash A)<\varepsilon$

> [!proof]-
> Same as the proof for [[Lebesgue Measure|Theorem 3]] but with Theorem 1.
---
##### Examples
> [!claim] Proposition 3
> The [[Lebesgue Measure]] $\mathcal{L}^n$ is a Radon measure on $\mathbb{R}^n$.

> [!proof]-
> Firstly, we know that $\mathcal{L}^n$ is Borel regular from [[Lebesgue Measure|Theorem 7]]. Furthermore, for any compact set $K \subseteq \mathbb{R}^n$, it is bounded, i.e. there exists $r>0$ s.t. $K \subseteq B_{<r}(0)$. Therefore, $$\mathcal{L}^n(K)\leq \mathcal{L}^n(B_{<r}(0))=w_{n}r^n<+\infty$$
---
> [!claim] Proposition 4
> For $s<n$ , the [[Hausdorff Measure|$s$-dimensional Hausdorff measure]] $\mathcal{H}^s$ is not a Radon measure on $\mathbb{R}^n$.

> [!proof]-
> We have that for the closed unit ball $B_{\leq 1}(0)$, $\mathcal{H}^n(B_{\leq 1}(0))=1$. Therefore, by [[Hausdorff Measure|Lemma 3]], for $s<n$, $$\mathcal{H}^s(B_{\leq 1}(0))=\infty$$
---
> [!claim] Proposition 5
> If $\mu$ is a Borel-regular measure on $\mathbb{R}^n$ and $A\subseteq \mathbb{R}^n$ is $\mu$-measurable with $\mu(A)<+\infty$, the measure $\nu_{A}:\mathcal{P}(\mathbb{R}^n)\to[0,+\infty]$ defined as: $$\nu_{A}(B)=\mu(A\cap B)$$ is Radon in $\mathbb{R}^n$.
 
> [!proof]-
> We will show as follows: 
> 1. **$\nu_{A}$ is a measure**
>    Firstly, $\nu_{A}(\varnothing)=\mu(A \cap \varnothing)=0$. Further, for all $B \subseteq \bigcup_{i=0}^{\infty}B_{i}$, $$\nu_{A}(B)=\mu(A\cap B)\leq \sum_{i=0}^{\infty}\mu(A \cap B_{i})=\sum_{i=0}^{\infty}\nu_{A}(B_{i})$$
> 2. **$\nu_{A}$ is metric, therefore Borel**
> 	For any $B,C\in \mathbb{R}^n$ s.t. $d(B,C)>0$, we have that $d(A\cap B,A\cap C)>0$. Therefore, $$\nu_{A}(B)+\nu_{A}(C)=\mu(A\cap B)+\mu(A\cap C)=\mu(A\cap(B\cup C))=\nu_{A}(B\cup C)$$
> 3. **$\nu_{A}$ is Borel regular**
> 	For $B\subseteq \mathbb{R}^n$, we have $B'\in \mathcal{B}(\mathbb{R}^n)$ s.t. $B \subseteq B'$ and $\mu(B)=\mu(B')$.  Then, $$\nu_{A}(B)=\mu(A \cap B)\leq\mu(A \cap B')=\nu_{A}(B')$$Furthermore, $$\nu_{A}(B')=\mu(B')-\mu(B' \backslash A)\leq\mu(B)-\mu(B\backslash A)=\mu(A \cap B)=\nu_{A}(B)$$
> 	Therefore, $\nu_{A}(B)=\nu_{A}(B')$.
> 4. **For every compact set $K \subseteq \mathbb{R}^n$, $\mu(K)<+\infty$.** 
>    We have that for any compact set $K$, $$\nu_{A}(K)=\mu(A \cap K)\leq \mu(A)<+\infty$$
>    
> Therefore, $\nu_{A}$ is Radon in $\mathbb{R}^n$.
---

