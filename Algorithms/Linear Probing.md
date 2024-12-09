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
> For $S\subseteq[m]$, let $\text{supp }S$ denote the entries in the hash table that are "full". 
> 
> Assume $m=2^k$. For every $0\leq \ell\leq k$, let $I_{\ell,i}:=[i\cdot 2^{\ell},(i+1)\cdot 2^{\ell})$
> 1. **Claim 1**: if $\left| R(x) \right|\in [2^{\ell+2},2^{\ell+3})$ then there exists at least one interval $I_{\ell,i}$ s.t.  $|\text{supp }I_{\ell,i}|\geq 2^\ell \cdot \frac{3}{4}$ and $I_{\ell,i}\cap R(x)\neq \varnothing$.
>    
>    Let $I_{0},I_{1},I_{2},I_{3}$ be the first four intervals at depth $\ell$ that intersect $R(x)$. As the run is at least $2^{\ell+2}$. $I_{1},I_{2},I_{3}$ are full and $I_{0}$ contains at least one item. But at the same time, we know that the run started in $I_{0}$ and so all items in the first four intervals hashed into $I_{0},I_{1},I_{2}$ or $I_{3}$. But since at least $3\cdot 2^{\ell}+1$ items hashed into these four intervals, we have that at least $3\cdot2^{\ell}$ elements without $x$ hashed into these intervals. Thus, at least one of them has support $\geq 2^{\ell}\cdot \frac{3}{4}$. 
> 
> Now, let $P_{\ell}$

^2204d7
