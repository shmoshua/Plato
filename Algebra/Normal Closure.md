#Definition #Algebra 

> [!definition]
> Let $L:K$ be an [[Algebraic and Transcendental Element|algebraic extension]]. A ***normal closure*** of $L:K$ is an extension $N:L$ s.t. 
> 1. $N:K$ is [[Normal Extension|normal]].
> 2. If $L\subseteq M\subseteq N$ and $M:K$ is normal then $M=N$.
---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be a finite extension. Then, 
> 1. there exists a normal closure $N$ of $L:K$ s.t. $N:K$ is finite.
> 2. if there exists another normal closure $M$, then $M:K$ and $N:K$ are isomorphic.
---
> [!lemma] Lemma 2
> Suppose $K\subseteq L\subseteq N\subseteq M$ where $L:K$ is finite and $N$ is a normal closure of $L:K$.
> 1. for $\phi\in \text{Mono}_{K}(L,M)$, we have $\phi(L)\subseteq N$.

> [!proof]-
> Suppose $\alpha\in L$. Let $m:=m_{\alpha,K}$ be its minimal polynomial over $K$. Then, $$0=m(\alpha)=\phi(m(\alpha))=m(\phi(\alpha))$$Therefore, $\phi(\alpha)$ is also a root of $m$. However, as $N:K$ is normal, $\phi(\alpha)\in N$.
- **Remark**: if $L:K$ is normal, 
---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$ is not normal.
> 2. $\mathbb{Q}(\sqrt[3]{2  },\exp(2\pi i /3))$ is the normal closure of $\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}$.