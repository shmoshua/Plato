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
> [!lemma] Theorem 3
> For a polynomial $f\in K[X]$, if $f$ is solvable by radicals, then $\text{Gal}(L_{f}:K)$ is solvable.

> [!proof]+
> 
---
> [!lemma] Theorem 4 (Abel-Ruffini)
> Let $L=K(\alpha_{1},\dots,\alpha_{n})$ be a splitting field of a general polynomial $f_{n}(x)\in K(s_{1},\dots,s_{n})$. Then, $$\text{Gal}(L:K(s_{1},\dots,s_{n}))\cong S_{n}$$
---