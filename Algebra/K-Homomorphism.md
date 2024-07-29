#Definition #Algebra 

> [!definition]
> Let $K$ be a subfield of $M,L$. 
> 1. A ***$K$-homomorphism*** from $M$ to $L$ is a homomorphism $\phi\in \text{Hom}(M,L)$ that fixes $K$, i.e.:$$\phi|_{K}=\text{id}_{K}$$The set of $K$-homomorphisms are denoted as $\text{Hom}_{K}(M,L)$.
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
> [!lemma] Theorem 2 (K-automorphisms build a group)
> Let $L:K$ be a [[field extension]]. Then, 
> 1. $\text{Aut}_{K}(L)\leq \text{Aut}(L)$ 

> [!proof]-
> We have that for $\sigma,\gamma\in \text{Aut}_{K}(L)$, $$\sigma (\gamma ^{-1}(t))=\sigma(t)=t,\quad \forall t\in K$$Therefore, $\sigma \circ\gamma ^{-1}\in \text{Aut}_{K}(L)$. 
---
##### Q-Automorphisms and R-Automorphisms
> [!lemma] Proposition 1
> Let $K:\mathbb{Q}$. Then, 
> 1. $\text{Aut}(K)=\text{Aut}_{\mathbb{Q}}(K)$.

> [!proof]-
> Let $\sigma\in \text{Aut}(K)$. Then, as $\sigma(1)=1$, we have that for any $n\in \mathbb{Z}$, $$\sigma(n)=\sigma(n\cdot 1)=n\sigma(1)=n$$Further, for any $\frac{p}{q}\in \mathbb{Q}$, $$q\sigma\left( \frac{p}{q} \right)=\sigma(p)=p$$therefore, $\sigma|_{\mathbb{Q}}=\text{id}_{\mathbb{Q}}$.
---
> [!lemma] Proposition 2
> For $\sigma\in \text{Aut}(\mathbb{R})$, we have:
> 1. $x\leq y\implies\sigma(x)\leq\sigma(y)$
> 2. $\sigma$ is continuous.
> 3. $\text{Aut}(\mathbb{R})=\{ \text{id}_{\mathbb{R}} \}$

> [!proof]-
> We have:
> 1. For $x\leq y$, $y-x\geq 0$ and there exists $z\in \mathbb{R}$ s.t. $y-x=z^{2}$. Therefore, $$\sigma(y)-\sigma(x)=\sigma(y-x)=\sigma(z^{2})=\sigma(z)^{2}\geq 0$$
> 2. Let $(a,b)\subseteq \mathbb{R}$. We want to show that its preimage is open. let $a<\sigma(x)< b$. As $\sigma$ is surjective, there exists $\alpha,\beta\in \mathbb{R}$ s.t. $a=\sigma(\alpha)$ and $b=\sigma(\beta)$. Hence, $\sigma(\alpha)<\sigma(x)<\sigma(\beta)$. 
>    
>    As $\sigma ^{-1}\in \text{Aut}(\mathbb{R})$ as well, it is increasing and $(\alpha,\beta)=\sigma ^{-1}(a,b)$. Hence, $\sigma$ is continuous.
>  3. For $\sigma\in \text{Aut}(\mathbb{R})$, as $\sigma$ and $\text{id}_{\mathbb{R}}$ are both continuous and they coincide on $\mathbb{Q}$ from Proposition 1, they must coincide on the whole $\mathbb{R}$. 
---
