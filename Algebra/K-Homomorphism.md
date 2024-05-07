#Definition #Algebra 

> [!definition]
> Let $K$ be a subfield of $M,L$. A ***$K$-homomorphism*** from $M$ to $L$ is a homomorphism $\phi\in \text{Hom}(M,L)$ that fixes $K$, i.e.:$$\phi|_{K}=\text{id}_{K}$$The set of $K$-homomorphisms are denoted as $\text{Hom}_{K}(M,L)$.
- **Related definition**: Following the definitions, we can also define $\text{Mono}_{K}(M,L), \text{Aut}_{K}(M)$ etc. 
---
##### Properties
> [!lemma] Theorem 1
> Let $K\subseteq M\subseteq L$. Then, 
> 1. for $\phi\in \text{Aut}_{K}(L)$, $\phi|_{M}\in \text{Mono}_{K}(M,L)$.
> 2. if $L:K$ is finite and normal, $\phi\in \text{Mono}_{K}(M,L)$ admits an extension $\sigma\in \text{Aut}_{K}(L)$.

> [!proof]-
> We have:
> 1. $\phi|_{M}$ is a monomorphism as $\phi$ is. Further, $(\phi|_{M})|_{K}=\phi|_{K}=\text{id}_{K}$.
> 2. Since $L:K$ is finite and normal, by [[Normal Extension|Theorem 1]] it is a splitting field of some polynomial $f\in K[X]$. Therefore, $L:K$ is also a splitting field of some polynomial $f\in M[X]$. Further, as $\phi$ is injective, it is a splitting field of $\phi(f)=f\in \phi(M)\subseteq L$. 
>    
>    As $L$ is a splitting field of $f$ over $K[X]\subseteq \phi(M)[X]$, using the [[Splitting Field|splitting field isomorphism theorem]], $\phi:M\to \phi(M)$ extends to an isomorphism $\sigma:L\to L$. One can easily see that $\sigma\in \text{Aut}_{K}(L)$
- **Corollary**: Let $L:K$ be finite and normal. Let $\alpha,\beta\in L$ be roots of some irreducible polynomial $f\in K[X]$. Then, there exists $\sigma\in \text{Aut}_{K}(L)$ s.t. $\sigma(\alpha)=\beta$. 
---