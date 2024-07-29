#Definition #Algebra 

> [!definition]
> Let $L:K$ be an [[Algebraic and Transcendental Element|algebraic extension]]. A ***normal closure*** of $L:K$ is an extension $N:L$ s.t. 
> 1. $N:K$ is [[Normal Extension|normal]].
> 2. If $L\subseteq M\subseteq N$ and $M:K$ is normal then $M=N$.
---
##### Properties
> [!lemma] Theorem 1 (Existence and Unique of Normal Closures)
> Let $L:K$ be a finite extension. Then, 
> 1. there exists a normal closure $N$ of $L:K$ s.t. $N:K$ is finite.
> 2. if $M$ is another normal closure of $L$, then $M:K$ and $N:K$ are isomorphic.

> [!proof]-
> We have:
> 1. Let $\alpha_{1},\dots,\alpha_{n}$ be a basis of $L$ over $K$. As $L:K$ is algebraic, let $m_{i}:=m_{\alpha_{i},K}$ be the minimal polynomial. Let $N$ then be the splitting field of $m_{1}\dots m_{n}$ over $K$. Then, by [[Normal Extension|Theorem 1]], $N:K$ is normal and finite. 
>    
>    Further, let $L\subseteq M\subseteq N$ and $M:K$ be normal. Then, $m_{i}\in L[X]$ has to split in $M$ as it has a root in $M$. As $N$ is a splitting field, $N\subseteq M$ and $N=M$.
> 2. Let $M$ now be another normal closure. Then, trivially $M$ is a splitting field of $f:=m_{1}\dots m_{n}$ over $K$. Then, we of course have an isomorphism $\sigma:N\to M$ that extends $\text{id}_{K}$. 
---
> [!lemma] Lemma 2
> Suppose $K\subseteq L\subseteq N\subseteq M$ where $L:K$ is finite and $N$ is a normal closure of $L:K$.
> 1. for $\phi\in \text{Mono}_{K}(L,M)$, we have $\phi(L)\subseteq N$.

> [!proof]-
> Suppose $\alpha\in L$. Let $m:=m_{\alpha,K}$ be its minimal polynomial. Then, 
> $$m(\phi(\alpha))=\phi(m(\alpha))=\phi(0)=0$$Therefore, $\phi(\alpha)$ is also a root of $m$. However, as $N:K$ is normal, $\phi(\alpha)\in N$.
- **Corollary**: if $L:K$ is normal and finite where $K\subseteq L\subseteq M$, then $\text{Mono}_{K}(L,M)=\text{Aut}_{K}(L)$ as $\phi(L)\subseteq L$ and $L:K$ is finite. 
---
> [!lemma] Theorem 3
> Suppose $L:K$ is finite and separable. Then, for a normal closure $N$ of $L:K$, $$\left| \text{Mono}_{K}(L,N) \right| =[L:K]$$

> [!proof]-
> We will use an induction on $[L:K]=:n$. 
> 1. if $[L:K]=1$, then the result is clear.
> 2. if $[L:K]>1$, let $\alpha\in L$ and $m$ be the minimal polynomial of $\alpha$ over $K$. If $\alpha\notin K$, then  $$\deg m=[K(\alpha):K]=r>1$$As $N:K$ is normal, $m$ splits in $N$ and its zeros $\alpha_{1},\dots,\alpha_{r}$ are distinct by separability. Then, by induction, we have that: $$\left| \text{Mono}_{K(\alpha)}(L,N) \right| =[L:K(\alpha)]$$given by $\text{Mono}_{K(\alpha)}(L,N)=\{ \rho_{1},\dots,\rho_{s} \}$ where $s= n / r$. Then by [[Normal Extension|Theorem 3.2]], there exists $\tau_{1},\dots,\tau_{r}\in \text{Aut}_{K}(N)$ s.t. $\tau_{i}(\alpha)=\alpha_{i}$. Therefore, the maps: $$\varphi_{ij}:=\tau_{i}\rho_{j},\quad i\in [r],j\in [s]$$are $K$-monomorphisms from $L$ to $N$. 
>    
>    We want to show that they are distinct. Suppose $\varphi_{ij}=\varphi_{kl}$. Then, $\tau_{i}\rho_{j}=\tau_{k}\rho_{l}$ and we have: $$\alpha_{i}=\tau_{i}(\alpha)=\tau_{i}(\rho_{j}(\alpha))=\tau_{k}(\rho_{l}(\alpha))=\tau_{k}(\alpha)=\alpha_{k}$$Therefore, $i=k$ and $\tau_{k}^{-1}\tau_{i}=\rho_{l}\rho_{j}^{-1}$ on $\rho_{j}(L)$ where the LHS is the identity. Therefore, for any $x\in L$, $\rho_{j}(x)=\rho_{l}(x)$ and $\rho_{j}=\rho_{l}$.
>    
>    Lastly, we want to show that these are the only $K$-monomorphisms from $L$ to $N$. Let $\tau\in \text{Mono}_{K}(L:N)$. Then, $\tau(\alpha)$ is also a zero of $m$ and therefore, $\tau(\alpha)=\alpha_{i}$ for some $i$. Then, $\varphi:=\tau_{i}^{-1}\tau$ is a $K(\alpha)$-monomorphism $L\to N$ and from the induction hypothesis $\varphi=\rho_{j}$ for some $j$. Therefore, $\tau=\tau_{i}\rho_{j}=\varphi_{ij}$.
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$ is not normal.
> 2. $\mathbb{Q}(\sqrt[3]{2  },\exp(2\pi i /3))$ is the normal closure of $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$.