#Definition #Algorithms 

> [!definition]
> Let $U\in \mathbb{N}$. In ***linear probing***, we have an hash table $H$ of size $n$. Let $h:[U]\to[m]$ be a [[k-wise Independent Hash Function|hash function]]. Further, we have the following operations:
> 1. $\text{INSERT}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. Then, $H[k]\gets x$.
> 2. $\text{DELETE}(x)$: Find $k$ s.t. $H[k]=x$. Then, $H[k]\gets {\bot}$. Recursively find $y\in[U]$ with $h(y)\leq k$ but stored after $H[k]$. Move it down to $H[k]$. 
> 3. $\text{IsMEMBER}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. If there exists $j\in[i,k]$ with $H[j]=x$ return yes, otherwise no.

^ccfb2c

- **Remark**: The invariant is that, if $x=H[k]$, then $H[h(x)],\dots,H[k-1]$ are not empty. 
---
##### Properties
> [!lemma] Theorem 1
> Let $h \sim \mathcal{H}_{5,U,m}$ where $m\geq \frac{3}{2}n$. Then, every operation takes $\text{O}(1)$ in expectation.

^279bcf

> [!proof]+
> For $x\in [U]$, let $R(x):=\{ j\geq h(x):H[j]\neq {\bot} \}$. Then, every operation has runtime $\text{O}(\left| R(x) \right|+1)$. Hence, it suffices to show that $\left| R(x) \right|\in \text{O}(1)$ for all $x\in[U]$ in expectation.
> 
> Assume $m=2^k$. We have that: $$\mathbb{E}[\left| R(x) \right| ]\leq\sum_{\ell=1}^{k}2^{\ell}\mathbb{P}(2^{\ell-1}\leq\left| R(x) \right|< 2^{\ell})$$Hence, let's analyze $\mathbb{P}(2^{\ell-1}\leq\left| R(x) \right|< 2^{\ell})$. Let $S$ denote the dynamic collection of the hash table. Further, for every $0\leq \ell\leq k$, let $I_{\ell,i}:=[i\cdot 2^{\ell},(i+1)\cdot 2^{\ell})$
> 1. **Claim 1**: if $2^{\ell+2}\leq\left| R(x) \right|<2^{\ell+3}$ then there exists at least one interval $I_{\ell,i}$ s.t. $I_{\ell,i}\cap R(x)\neq \varnothing$ and $|h^{-1}(I_{\ell,i})\cap S \backslash \{ x \}|\geq \frac{3}{4}2^{\ell}$.
>    
>    Let $I_{0},I_{1},I_{2},I_{3}$ be the first four intervals at depth $\ell$ that intersect $R(x)$. As the run is at least $2^{\ell+2}$, $I_{1},I_{2},I_{3}$ are full and $I_{0}$ contains at least one item. But at the same time, we know that the run started in $I_{0}$ and so all items in the first four intervals hashed into $I_{0},I_{1},I_{2}$ or $I_{3}$. But since at least $3\cdot 2^{\ell}+1$ items hashed into these four intervals, we have that at least $3\cdot2^{\ell}$ elements without $x$ hashed into these intervals. This proves the statement.
> 
> Now, we have that:$$\mathbb{P}(2^{\ell+2}\leq \left| R(x) \right| <  2^{\ell+3})\leq (2^3+1)\mathbb{P}\left(\left| h^{-1}(I_{\ell,i})\cap S \backslash \{ x \} \right|\geq \frac{3}{4}2^\ell \right)$$where $I_{\ell,i}\cap R(x)\neq \varnothing$. Let $I:=I_{\ell,i}$. Then, for any $y\in S \backslash \{ x \}$, let $X_{y}$ be the indicator variable for $h(y)\in I$. Let $X:=\sum_{y\in S \backslash \{ x \}}^{}X_{y}$ and then we have that:
> 1. $\mathbb{E}[X]\leq n \cdot 2^{\ell} / m\leq \frac{2}{3}\cdot 2^{\ell}$.
> 
> Further, as $\{ X_{y} \}_{y\in S \backslash \{ x \}}$ are $4$-wise independent as $h$ is $5$-wise independent, we have that: 
> 1. If $2^{\ell} / m\geq \frac{1}{n}$, then: $$\begin{align}\mathbb{P}\left(\left| h^{-1}(I)\cap S \backslash \{ x \} \right|\geq \frac{3}{4}2^\ell \right)\leq\mathbb{P}\left( X-\mu\geq \frac{1}{12}2^{\ell}\right)\leq\mathbb{P}\left( X-\mu> \frac{1}{10}\sqrt{ 2 ^\ell \mu}\right)\end{align}$$Hence, by [[Moment|Theorem 1]], $$\mathbb{P}\left(\left| h^{-1}(I)\cap S \backslash \{ x \} \right|\geq \frac{3}{4}2^\ell \right)< \frac{40000}{2^{2\ell}}$$Therefore, $\mathbb{P}(2^{\ell+2}\leq \left| R(x) \right| <  2^{\ell+3})=\text{O}(2^{-2\ell})$. 
> 2. If $2^{\ell} / m< \frac{1}{n}$, then 
> 3. 
> 4. Hence, $$\mathbb{E}[\left| R(x) \right| ]\leq \sum_{\ell=1}^{k}2^{\ell}\text{O}(2^{-2\ell})=\sum_{\ell=1}^{k}\text{O}(2^{-\ell})=\text{O}(1)$$

^2204d7
