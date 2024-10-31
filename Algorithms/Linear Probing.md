#Definition #Algorithms 

> [!definition]
> Let $U\in \mathbb{N}$. In ***linear probing***, we have an hash table $H$ of size $n$. Let $h:[U]\to[m]$ be a [[k-wise Independent Hash Function|hash function]]. Further, we have the following operations:
> 1. $\text{INSERT}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. Then, $H[k]\gets x$.
> 2. $\text{DELETE}(x)$: Find $k$ s.t. $H[k]=x$. Then, $H[k]\gets {\bot}$. Recursively find $y\in[U]$ with $h(y)\leq k$ but stored after $H[k]$. Move it down to $H[k]$. 
> 3. $\text{IsMEMBER}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. If there exists $j\in[i,k]$ with $H[j]=x$ return yes, otherwise no.
- **Remark**: The invariant is that, if $x=H[k]$, then $H[h(x)],\dots,H[k-1]$ are not empty. 
---
##### Properties
> [!lemma] Theorem 1
> Let $h \sim \mathcal{H}_{5,U,m}$ where $m\geq \frac{3}{2}n$. Then, every operation takes $\text{O}(1)$ in expectation.

> [!proof]+
> For $x\in [U]$, let $R(x):=\{ j\geq h(x):H[j]\neq {\bot} \}$. Then, every operation has runtime $\text{O}(\left| R(x) \right|+1)$.
> 
> Assume $m=2^k$. For every $0\leq \ell\leq k$, let $I_{\ell,i}:=[i\cdot 2^{\ell},(i+1)\cdot 2^{\ell})$