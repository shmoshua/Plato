#Definition #Algebra 

> [!definition]
> Let $L:K$ be an [[Algebraic and Transcendental Element|algebraic extension]]. A ***normal closure*** of $L:K$ is an extension $N:L$ s.t. 
> 1. $N:K$ is [[Normal Extension|normal]].
> 2. If $L\subseteq M\subseteq N$ and $M:K$ is normal then $M=N$.
---
##### Properties
> [!lemma] Theorem 1 (Existence and Unique of Normal Closures)
> Let $L:K$ be a finite algebraic extension. Then, 
> 1. there exists a normal closure $N$ of $L:K$ s.t. $N:K$ is finite.
> 2. if $M$ is another normal closure of $L$, then $M:K$ and $N:K$ are isomorphic.

> [!proof]+
> We have:
> 1. Let $\alpha_{1},\dots,\alpha_{n}$ be a basis of $L$ over $K$. As $L:K$ is algebraic, let $m_{i}:=m_{\alpha_{i},K}$ be the minimal polynomial. Let $N$ then be the splitting field of $m_{1}\dots m_{n}$ over $K$. Then, by [[Normal Extension|Theorem 1]], $N:K$ is normal and finite. 
>    
>    Further, let $L\subseteq M\subseteq N$ and $M:K$ be normal. Then, $m_{i}\in L[X]$ has to split in $M$ as it has a root in $M$. As $N$ is a splitting field, $N\subseteq M$ and $N=M$.
> 2. Let $M$ now be another normal closure. Then, trivially $M$ is a splitting field of $m_{1}\dots m_{n}$ over $K$. 
---
> [!lemma] Lemma 2
> Suppose $K\subseteq L\subseteq N\subseteq M$ where $L:K$ is finite and $N$ is a normal closure of $L:K$.
> 1. for $\phi\in \text{Mono}_{K}(L,M)$, we have $\phi(L)\subseteq N$.

> [!proof]-
> Suppose $\alpha\in L$. Let $m:=m_{\alpha,K}$ be its minimal polynomial over $K$. Then, $$0=m(\alpha)=\phi(m(\alpha))=m(\phi(\alpha))$$Therefore, $\phi(\alpha)$ is also a root of $m$. However, as $N:K$ is normal, $\phi(\alpha)\in N$.
- **Corollary**: if $L:K$ is normal and finite where $K\subseteq L\subseteq M$, then $\text{Mono}_{K}(L,M)=\text{Aut}_{K}(L)$ as $\phi(L)\subseteq L$ and $L:K$ is finite. 
---
> [!lemma] Theorem 3
> Suppose $L:K$ is finite and separable of degree $n$. Then, for a normal closure $N$ of $L:K$, $$\left| \text{Mono}_{K}(L:N) \right| =n$$
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$ is not normal.
> 2. $\mathbb{Q}(\sqrt[3]{2  },\exp(2\pi i /3))$ is the normal closure of $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$.