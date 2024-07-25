#Definition #Algebra 
> [!definition]
> For a [[field extension]] $L:K$,
> 1. the ***Galois group  of $L:K$*** $\text{Gal}(L:K):=\text{Aut}_{K}(L)$, i.e. the group of all $K$-automorphism of $L$.
> 2. the ***Galois group of $f\in K[X]$*** is $\text{Gal}(L : K)$ where $L$ is the splitting field of $f$ over $K$.
- **Remark**: For $\sigma\in \text{Gal}(L:K)$ is $K$-linear, i.e. $\sigma(kx+y)=\sigma(k)\sigma(x)+\sigma(y)=k\sigma(x)+\sigma(y)$.
---
##### Properties

> [!lemma] Lemma 1
> Let $f\in K[X]$ and $L$ be a [[splitting field]] of $f$ over $K$. Then, 
> 1. $\text{Gal}(L:K)$, i.e. the Galois group of $f$ permutes the roots of $f$.
> 2. $\text{Gal}(L:K)\to S(R(f)),\sigma\mapsto \sigma_{R(f)}$ is an injective group homomorphism, where $R(f)\subseteq L$ is the set of roots of $f$.
> 3. $\text{Gal}(L:K)$ is isomorphic to a subgroup of a symmetric group.

> [!proof]-
> We have: 
> 1. Let $f(x):=a_{n}x^n+\dots +a_{0}\in K[X]$ and $R(f)\subseteq L$ denote the set of roots of $f$. For $\alpha\in R(f)$ and $\sigma\in \text{Gal}(L:K)$, $$0=\sigma(f(\alpha))=\sigma(a_{n}\alpha^n+\dots+a_{0})=a_{n}\sigma(\alpha)^n+\dots+a_{0}$$which implies that $\sigma(\alpha)\in R(f)$ and $\sigma(R(f))\subseteq R(f)$. However, as $\sigma$ is injective and $R(f)$ is finite, $\sigma(R(f))=R(f)$.
> 2. For $\sigma,\eta\in \text{Gal}(L:K)$, $(\sigma \circ \eta)|_{R(f)}=\sigma|_{R(f)}\circ \eta|_{R(f)}$ and the restriction is a group homomorphism. To check the injectivity, let $R(f)=:\{ \alpha_{1},\dots,\alpha_{n} \}$. Then, $L=K(\alpha_{1},\dots,\alpha_{n})$ and: $$L:=\left\{  \frac{p(\alpha_{1},\dots,\alpha_{n})}{q(\alpha_{1},\dots,\alpha_{n})}:p,q\in K[X_{1},\dots,X_{n}], q(\alpha_{1},\dots,\alpha_{n})\neq 0  \right\}$$ If $\sigma|_{R(f)}=\text{id}_{R(f)}$, then $\sigma(\alpha_{i})=\alpha)_i$ for all $i$ and as $\sigma(k)=k$ as well for all $k\in K$, $\sigma(\ell)=\ell$ for all $\ell\in L$. Therefore, $\sigma=\text{id}_{L}$.
- **Remark**: For $K\subseteq L$ if $c\in L$ is a root of $f\in K[X]$, then so is $\sigma(c)$ for any $\sigma\in \text{Gal}(L:K)$ and they share the minimal polynomial.
---
> [!lemma] Theorem 4
> If $L$ is a splitting field of $f\in K[X]$ over $K$, then: $$\left| \text{Gal}(L:K) \right| \leq [L:K]$$with equality when $f$ is [[Separable Extension|separable]]. 


> [!proof]-
> Applying [[Splitting Field|Theorem 2]] on $\tilde{K}=K$ and $\tilde{L}=L$ with $\varphi=\text{id}$, then, the extensions of $\varphi$ are precisely the elements of $\text{Gal}(L:K)$.
---
##### Examples
> [!h] Example 1
> Let $\sigma\in \text{Gal}(\mathbb{C} :\mathbb{R})$ and $j:=\sigma(i)$. Then, 
> 1. $j^{2}=(\sigma(i))^{2}=\sigma(-1)=-1$ and $j=\pm i$.
> 2. $\text{Gal}(\mathbb{C}:\mathbb{R})\cong \mathbb{Z} / 2\mathbb{Z}$
---
> [!h] Example 2
> Let $\sigma\in \text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})$ where $\alpha$ is the real root of $x^3-2$. Then, $$\sigma(\alpha)^3=\sigma(\alpha^{3})=\sigma(2)=2$$Therefore, $\sigma(\alpha)$ is a root of $x^3-2$ and $\sigma(\alpha)=\alpha$. Therefore, $\text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})\cong \{ \text{id} \}$.
---
> [!h] Example 3
> Consider $\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q}$. 
> 1. $[\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q}]=4$.
> 4. If $\sigma\in \text{Gal}(\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q})$ then $\sigma(1)=1$, $\sigma(\sqrt{ 2 })=\pm \sqrt{ 2 }$ and $\sigma(\sqrt{ 3 })=\pm \sqrt{ 3 }$.
> 5. $\{ 1,\sqrt{ 2 },\sqrt{ 3 },\sqrt{ 6 } \}$ forms a basis of $\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 })$ over $\mathbb{Q}$. 
> 6. $\text{Gal}(\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q})\cong \mathbb{Z} / 2\mathbb{Z} \times \mathbb{Z} / 2\mathbb{Z}$.
> 7. $\left| \text{Gal}(\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q}) \right|=[\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 }):\mathbb{Q}]$.
---
> [!h] Example 4
> Consider $\mathbb{Q}(\sqrt[4]{ 2 }):\mathbb{Q}$. Then, for $\sigma\in \text{Gal}(\mathbb{Q}(\sqrt[4]{ 2 }):\mathbb{Q})$,
> 1. $2=\sigma(2)=\sigma(\sqrt[4]{2  })^4$ and $\sigma(\sqrt[4]{ 2 })=\pm \sqrt[4]{ 2 }$.
> 2. $\sigma(\sqrt{ 2 })=\sqrt{ 2 }$ and no $\mathbb{Q}$-automorphism sends $\sqrt{ 2 }$ to $-\sqrt{ 2 }$.
---
