#Definition #Algebra 

> [!definition]
> A [[field extension]] $L:K$ is ***radical*** if $L=K(\alpha_{1},\dots,\alpha_{m})$ where for each $i=1,\dots,m$, there exists an integer $n_{i}\in\mathbb{Z}$ s.t. $\alpha_{i}^{n_{i}}\in K(\alpha_{1},\dots,\alpha_{i-1})=:K_{i-1}$.
> 
> In other words, there exists a chain of intermediate fields: $$K=K_{0}\subseteq K_{1}\subseteq\dots \subseteq K_{m}=L$$s.t. $K_{i-1}(\alpha_{i})=K_{i}$ where $\alpha_{i}^{n_{i}}\in K_{i-1}$.
- **Related definition**: $\alpha_{i}$ form a ***radical sequence*** for $L:K$.
- **Related definition**: A polynomial $f\in K[X]$ is ***solvable by radicals*** if there exists a radical extension $M:K$ s.t. $f$ splits in $M[X]$, i.e. $L_{f}\subseteq M$.
---
##### Properties
> [!lemma] Theorem 1
> Let $K$ be a field with $\text{char }K=0$ and $L$ a finite [[normal extension]] of $K$. Then, the following are equivalent:
> 1. there exists $M:L$ s.t. $M:K$ is radical.
> 2. $\text{Gal}(L:K)$ is [[Solvable Group|solvable]].
---
> [!lemma] Lemma 2
> Let $L:K$ be a radical extension. Then, $L=K(\alpha_{1},\dots,\alpha_{n})$ with $\alpha_{i}^{p_{i}}\in K(\alpha_{1},\dots,\alpha_{i-1})$ where $p_{i}$'s are primes.

> [!proof]+
>
---
> [!lemma] Lemma 3
> For a radical extension $L:K$ and the [[normal closure]] $N$ of $L:K$, $N:K$ is radical. 

> [!proof]-
> Let $L=K(\alpha_{1},\dots,\alpha_{r})$ with $\alpha_{i}^{p_{i}}\in K(\alpha_{1},\dots,\alpha_{i-1})$ where $p_{i}$ prime. Let further $f_{i}$ be the minimal polynomial of $\alpha_{i}$ over $K$. Then, $N$ is a splitting field of $\prod_{i=1}^{r}f_{i}$.
> 
> Then, $N=K(\{ \beta_{ij} \})$ where $i=1,\dots,r$ and $\beta_{i 1},\dots,\beta_{i d_{i}}$ are roots of $f_{i}$. Let $K_{i}:=K(\{ \beta_{\ell j} \}_{\ell\leq i})$, i.e. the splitting field of $\prod_{\ell=1}^{i}f_{\ell}$. Then, $K_{i}$ contains $K(\alpha_{1},\dots,\alpha_{i})$ s.t. $\alpha_{i}^{p_{i}}\in K_{i-1}$. 
> 
> Further, as $\alpha_{i}$ and $\beta_{ij}$ have the same minimal polynomial over $K$, there exists a $K$-automorphism $\tau:N\to N$ s.t. $\tau(a_{i})=\beta_{ij}$. Therefore, $$\beta_{ij}^{p_{i}}=\tau(a_{i})^{p_{i}}=\tau(a_{i}^{p_{i}})\in \tau(K_{i-1})$$On the other hand, $K_{i-1}$ being a splitting field is normal. Therefore, $\tau(K_{i-1})=K_{i-1}$. It follows that $\beta_{ij}^{p_{i}}\in K_{i-1}$. Hence, $K_{i-1}\subseteq K_{i}$ is a radical extension.
---
> [!lemma] Theorem 4
> Let $K$ be a field with $\text{char }K=0$. For any normal radical extension $L:K$, $\text{Gal}(L:K)$ is solvable.

> [!proof]-
> We have:
> 1. **Claim: for $g(x)=x^p-1\in K[X]$ with $p$ prime, $\text{Gal}(L_{g}:K)$ is abelian**.
>    We have that $g'=px^{p-1}$. Therefore, $g$ and $g'$ have no common roots and $L_{g}=K(\xi)$ and for $\sigma_{i}(\xi)=\xi^i$, we have: $$(\sigma_{i}\sigma_{j})(\xi)=\xi^{ij}=(\sigma_{j}\sigma_{i})(\xi)$$Therefore, $\text{Gal}(L_{g}:K)$ is abelian.
> 2. **Claim: if $x^n-1$ splits in $K$, for $a\in K$ and $g(x):=x^n-a$, $\text{Gal}(L_{g}:K)$ is abelian**.
>    Let $\alpha$ be a zero of $x^n-a$ and $\xi\in K$ a zero of $x^n-1$, which exists. Then, all zeros of $x^n-a$ are of the form: $\alpha \xi_{i}$ where $\xi_{i}$ are the roots of $x^n-1$. 
>    
>    Let $L=K(\alpha)$ and $\tau,\sigma\in \text{Gal}(L_{g}:K)$. Then, for $\tau (\alpha)=\alpha \xi$ and $\sigma(\alpha)=\alpha\omega$ where $\xi,\omega\in K$, $$(\tau\sigma)(\alpha)=\tau(\alpha\omega)=\omega \tau(\alpha)=\omega\alpha \xi$$ $$(\sigma \tau)(\alpha)=\sigma(\alpha \xi)=\xi\sigma(\alpha)=\xi\alpha\omega$$Therefore, $\tau\sigma=\sigma \tau$ and $\text{Gal}(L_{g}:K)$ is abelian.
>  3. **Proving that $\text{Gal}(L:K)$ is solvable**.
>     Suppose $L=K(\alpha_{1},\dots,\alpha_{n})$ with $\alpha_{i}^{p_{i}}\in K_{i-1}$. In particular, there exists $\alpha_{1}$ and $p$ s.t. $\alpha_{1}^p\in K$. 
>     
>     By induction on $n$, if $\alpha_{1}\in K$, then $L=K(\alpha_{2},\dots,\alpha_{n})$ and $\text{Gal}(L:K)$ will be solvable by induction. Conversely, if $\alpha_{1}\notin K$, let $f$ be the minimal polynomial of $\alpha_{1}$ over $K$. Since $L:K$ is normal and $\alpha_{1}\in L$, $f$ splits in $L$. Since $\alpha_{1}\notin K$, $\text{deg }f\geq 2$ and let $\beta$ be the other root. Then, as $\alpha_{1}^p\in K$, $\alpha_{1}$ is a root of $x^p-\alpha_{1}^p\in K[X]$. So $f|(x^p-\alpha_{1}^p)$. 
>     
>     However, as $f(\beta)=0$, $\beta^p=\alpha_{1}^p$. Therefore, by defining $\varepsilon:= \alpha_{1} / \beta$, we have that $\varepsilon\neq 1$ and $\varepsilon^p=1$. Then, $1,\varepsilon,. ..,\varepsilon^{p-1}$ are distinct roots of $x^p-1$. Let $M$ be the splitting field of $x^p-1$, then $M=K(\varepsilon)$. 
>     
>     Now, consider the extension $L:M(\alpha_{1}):M:K$. Then, $M(\alpha_{1})$ is the splitting field of $x^p-\alpha_{1}^p$ over $M$. Therefore, by Claim 2, $\text{Gal}(M(\alpha_{1}):M)$ is abelian. As $L:K$ is normal, $L:M$ is normal and Galois. As $M(\alpha_{1}):M$ is normal, using the [[Galois Correspondence|fundamental theorem]], $$\text{Gal}(L:M(\alpha_{1}))\unlhd \text{Gal}(L:M)$$Moreover, $\text{Gal}(M(\alpha):M)\cong \text{Gal}(L:M) / \text{Gal}(L:M(\alpha_{1}))$. Therefore, by induction, $\text{Gal}(L:M(\alpha_{1}))$ is solvable and $\text{Gal}(M(\alpha_{1}):M)$ is solvable as it is abelian. It follows that $\text{Gal}(L:M)$ is solvable.
>     
>     Finally, $\text{Gal}(M:K)\cong \text{Gal}(L:K) / \text{Gal}(L:M)$ where $\text{Gal}(M:K)$ is solvable from being abelian. Therefore, $\text{Gal}(L:K)$ is solvable.
---
> [!lemma] Theorem 5
> Let $f\in K[X]$ where $K$ is a field with $\text{char }K=0$. If $f$ is solvable by radicals, then $\text{Gal}(L_{f}:K)$ is solvable.

> [!proof]-
> By definition, $K\subseteq L_{f}\subseteq M$ where $M:K$ is radical. Let $N$ be the normal closure of $M:K$. Then $K\subseteq L_{f}\subseteq M\subseteq N$. By Lemma 3, $N:K$ is a normal radical extension and $\text{Gal}(N:K)$ is solvable.
> 
> Since $L_{f}:K$ is normal, $\text{Gal}(N:L_{f})\unlhd \text{Gal}(N:K)$. Therefore, $$\text{Gal}(L_{f}:K)\cong \text{Gal}(N:K) / \text{Gal}(N:L_{f})$$and as $\text{Gal}(N:K)$ is solvable, $\text{Gal}(L_{f}:K)$ is solvable as a quotient of a normal subgroup.
---
> [!lemma] Theorem 4 (Abel-Ruffini)
> Let $L=K(\alpha_{1},\dots,\alpha_{n})$ be a splitting field of a general polynomial $f_{n}(x)\in K(s_{1},\dots,s_{n})$. Then, $$\text{Gal}(L:K(s_{1},\dots,s_{n}))\cong S_{n}$$
---
> [!lemma] Theorem 5
> Let $L:K$ be finite, $n\in \mathbb{N}$ s.t. $n$ does not divide $\text{char}(K)$. If $\mu_{n}\subseteq K$, the following are equivalent:
> 1. $L:K$ is simple residual, i.e. $L=K(\alpha)$ with $\alpha^n\in K$.
> 2. $L:K$ is Galois and the Galois group is cyclic of order dividing $n$.

> [!proof]-
> Let $\beta:=\alpha^n\in K$. Then, $x^n-\beta=\prod_{\xi\in \mu_{n}}^{}(x-\xi \alpha)$. Since $\mu_{n}\subseteq K$, $\xi a\in L$ for all $\xi\in \mu_{n}$. Therefore, $L$ is the splitting field of $x^n-b$. 
> 
> Notice that $(x^n-b)'=nx^{n-1}\neq 0$. Therefore, $(nx^{n-1},x^n-b)=1$ and $x^n-b$ is separable. This shows that $L:K$ is Galois.
> 
> Consider: $$\chi:\text{Gal}(L:K)\to \mu_{n},\gamma\mapsto \frac{\gamma(a)}{a}$$Then, for $\gamma,\sigma\in \text{Gal}(L:K)$, we have: $$\chi(\theta\gamma)=\frac{\theta\gamma(a)}{a}=\frac{\theta(a)}{a} \frac{\gamma(a)}{a}=\chi(\theta)\chi(\gamma)$$Therefore $\chi$ is a homomorphism and it is injective as $\chi:\text{Gal}(L:K)\hookrightarrow \mu_{n}\cong \mathbb{Z} / n\mathbb{Z}$.
---
