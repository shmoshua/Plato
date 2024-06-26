#Definition #Algebra 
> [!definition]
> Let $K$ be a [[Field|subfield]] of $L$. An [[Ring Homomorphism|automorphism]] $\sigma\in \text{Aut}(L)$ is called a ***$K$-automorphism*** of $L$ is $$\sigma|_{K}=\text{id}_{K}$$Then, 
> 1. the ***Galois group  of $L:K$*** is the group of all $K$-automorphism of $L$, denotes as $\text{Gal}(L : K)$ or $\text{Aut}_{K}L$.
> 2. the ***Galois group of $f\in K[X]$*** is $\text{Gal}(L : K)$ where $L$ is the splitting field of $f$ over $K$.
---
##### Properties
> [!lemma] Theorem 1
> For a field extension $L:K$, the set of all $K$-automorphisms of $L$ forms a [[group]] with composition.

> [!proof]-
> If $\sigma,\gamma \in \text{Aut}_{K}L$, then clearly $\sigma \circ\gamma\in \text{Aut}(L)$ and if $k\in K$, $$(\sigma \circ \gamma)(k)=\sigma(\gamma(k))=\sigma(k)=k$$Further, $\text{id}_{L}\in \text{Aut}_{K}(L)$ and for $\sigma ^{-1}\in \text{Aut}(L)$, $$\sigma ^{-1}(k)=(\sigma ^{-1}\circ \sigma)(k)=k$$
---
> [!lemma] Lemma 2
> Let $f\in K[X]$ and $L$ is a [[splitting field]] of $f$ over $K$. Let $R(f)\subseteq L$ be the set of the roots of $f$. Then, $\text{Gal}(L:K)$ permutes the roots of $f$.

> [!proof]-
> Let $f(x):=a_{n}x^n+\dots +a_{0}\in K[X]$, $\alpha\in R(f)$ and $\sigma\in \text{Gal}(L:K)$. Then, $$0=\sigma(f(\alpha))=\sigma(a_{n}\alpha^n+\dots+a_{0})=a_{n}\sigma(\alpha)^n+\dots+a_{0}$$which implies that $\sigma(\alpha)\in R(f)$ and $\sigma(R(f))\subseteq R(f)$. However, as $\sigma$ is injective and $R(f)$ is finite, $\sigma(R(f))=R(f)$.
- **Remark**: For $K\subseteq L$ if $c\in L$ is a root of $f\in K[X]$, then so is $\sigma(c)$ for any $\sigma\in \text{Gal}(L:K)$ and they share the minimal polynomial.
---
> [!lemma] Lemma 3
> Let $L$ be a splitting field of $f\in K[X]$. Then, $$\begin{array}{cccc} {}&{\text{Gal}(L:K)}&\to&{S(R(f))}\\&{\sigma} &\mapsto & {\sigma|_{R(f)}} \end{array}{}$$is an injective group homomorphism. In particular, $\text{Gal}(L:K)\cong H\leq S(R(f))$.

> [!proof]-
> If $\sigma,\eta\in \text{Gal}(L:K)$, then: $$(\sigma \circ \eta)|_{R(f)}=\sigma|_{R(f)}\circ \eta|_{R(f)}$$hence, the restriction is a homomorphism. Let $R(f)=\{ \alpha_{1},\dots,\alpha_{n} \}\subseteq L=K(\alpha_{1},\dots,\alpha_{n})$. Then, $$L=\left\{  \frac{p(\alpha_{1},\dots,\alpha_{n})}{q(\alpha_{1},\dots,\alpha_{n})} :p,q\in K[X_{1},\dots,X_{n}],q(\alpha_{1},\dots,\alpha_{n})\neq 0 \right\}$$ If $\sigma|_{R(f)}=\text{id}$, then $\sigma(\alpha_{i})=\alpha_{i}$ and as $\sigma(k)=k$ as well, $\sigma(\ell)=\ell$ for all $\ell\in L$. Therefore, $\sigma=\text{id}$ and the homomorphism is injective.
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
> Let $L:=\mathbb{Q}(\sqrt{ 2 },\sqrt{ 3 })$ and $K=\mathbb{Q}$. If $\sigma\in \text{Gal}(L:K)$ then $\sigma(1)=1$, $\sigma(\sqrt{ 2 })=\pm \sqrt{ 2 }$ and $\sigma(\sqrt{ 3 })=\pm \sqrt{ 3 }$.
> 
> It follows that $\text{Gal}(L:Q)\cong \mathbb{Z} / 2\mathbb{Z} \times \mathbb{Z} / 2\mathbb{Z}$.
