#Definition #Algorithms 

> [!definition]
> Let $U\in \mathbb{N}$. In ***linear probing***, we have an hash table $H$ of size $n$. Let $h:[U]\to[m]$ be a [[k-wise Independent Hash Function|hash function]]. Further, we have the following operations:
> 1. $\text{INSERT}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. Then, $H[k]\gets x$.
> 2. $\text{DELETE}(x)$: Find $k$ s.t. $H[k]=x$. Then, $H[k]\gets {\bot}$. Recursively find $y\in[U]$ with $h(y)\leq k$ but stored after $H[k]$. Move it down to $H[k]$. 
> 3. $\text{IsMEMBER}(x)$: Let $k:=\min\{ j\geq h(x):H[j]={\bot} \}$. 