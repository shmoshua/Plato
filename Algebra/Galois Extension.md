#Definition #Algebra 

> [!definition]
> A [[field extension]] $L:K$ is ***Galois***, if $L:K$ is [[Separable Extension|separable]] and [[Normal Extension|normal]].
---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be finite. Then, the following are equivalent:
> 1. $\left| \text{Gal}(L:K) \right|=[L:K]$
> 1. $L:K$ is Galois, in which case $L$ is a splitting field of a separable polynomial $f\in K[X]$.

> [!proof]-
> Let $n:=\left| \text{Gal}(L:K) \right|=[L:K]$ and $\text{Gal}(L:K)=\{ \sigma_{1},\dots,\sigma_{n} \}$. Let $f\in K[X]$ be a irreducible polynomial with a root $\alpha\in L$. 
> 1. **Showing $L:K$ is normal**:
>    Assume $\sigma_{1}=\text{id}$ and we have $$(\alpha_{1},\alpha_{2},\dots,\alpha_{r}):=(\alpha,\sigma_{2}(\alpha),\dots,\sigma_{r}(\alpha))$$ as the distinct images of $\sigma_{i}$ of $\alpha$. Since $\sigma\in G$ is injective on $\{ \alpha_{1},\dots,\alpha_{r} \}$, it is also surjective and $\sigma$ permutes the roots. Therefore, we define the following functions: 
>      - $s_{1}:=\sum_{i=1}^{r}\alpha_{i}$
>       - $s_{2}:=\sum_{i<j}^{}\alpha_{i}\alpha_{j}$
>       - $s_{r}:=\prod_{i=1}^{}\alpha_{i}$
> 
>    Then, $\sigma(s_{i})=s_{i}$ for all $\sigma\in G$ and $s_{i}\in K$, by Corollary 3. Let $$g(x):=(x-\alpha_{1})\dots(x-\alpha_{r})=x^r-s_{1}x^{r-1}+s_{2}x^{r-2}+\dots+(-1)^rs_{r}\in K[X]$$Since each $\alpha_{i}\in L$, $g$ splits over $L$. 
>    
>    We claim that $g=m_{\alpha,K}$. Let $h(x):=b_{0}+b_{1}x+\dots+b_{m}x^m\in K[X]$ with $\alpha$ as root. By applying $\sigma_{i}$, we know that: $$h(\sigma_{i}(\alpha))=\sigma_{i}(b_{0}+b_{1}\alpha+\dots+b_{m}\alpha^m)=\sigma_{i}(0)=0$$Therefore, $\alpha_{i}$ is a root of $h$ as well, and $g|h$, therefore, $g=m_{\alpha,K}$.
>    
>    However, $f$ is irreducible with $\alpha$ as root. Therefore, $f$ is a constant multiple of $g$ and $f$ splits over $L$, i.e. $L:K$ is normal.
>  2. **Showing $L:K$ is separable**:
>     Further $L:K$ is separable, because $\alpha_{1},\dots,\alpha_{r}$ are distinct and $\alpha$ is separable.
>  3. **Showing $L$ is a splitting field**:
>     Since $L:K$ is normal, separable and finite, let $L=K(\alpha_{1},\dots,\alpha_{n})$ and let $p_{i}(x)$ be the minimal polynomial of $\alpha_{i}$ over $K$. Since $L:K$ is normal, $L$ has all the roots of $p_{i}$.  As $L:K$ is separable, $p_{i}$ is separable and $L$ is the splitting field of the product of $p_{i}$ where this polynomial is also separable.
>   4. **Other implication**:
>      [[Galois Group|Theorem 4]]
---
> [!lemma] Theorem 2
> Let $L$ be a field and $G\leq \text{Aut}(L)$ a finite subfield of $\text{Aut}(L)$. Let $L_{0}:=\text{Fix}(G)=L^G=\phi(G)$. Then, $$[L:L_{0}]=[L:L^G]=\left| G \right| $$

> [!proof]-
> First, suppose that $[L:L^G]=:m<n=:\left| G \right|$. Let $\{ w_{1},\dots,w_{m} \}$ be the basis of $L$ over $L_{0}$. Let $G=\{ \sigma_{1},\dots,\sigma_{n} \}$ and consider the system: $$\sigma_{1}(w_{j})y_{1}+\dots+\sigma_{n}(w_{j})y_{m}=0$$for all $j\in [m]$. Then, as there are more unknowns than the number of equations, there exists a non-trivial solution $y_{i}\in L$. Therefore, we have that: $$(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(w_{j})=0$$for all $j\in[m]$ on a basis of $L$ over $L_{0}$. Let now $a=\sum_{i=1}^{m}a_{i}w_{i}\in L$ with $a_{i}\in L_{0}$. Then, $$(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(a)=\sum_{i=1}^{m}a_{i}(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(w_{i})=0$$Therefore, $\sigma_{1},\dots,\sigma_{n}$ are linearly dependent, which contradicts [[Character|Theorem 2]].
> 
> Suppose now that $[L:L^G]=m>n=\left| G \right|$. Let $\{ w_{1},\dots,w_{n+1} \}\subseteq L$ be linearly independent. Then, the equations: $$\sigma_{j}(w_{1})y_{1}+\dots+\sigma_{j}(w_{n+1})y_{n+1}=0$$for all $j\in[n]$. As there are more unknowns than equations, there exists a non-trivial solution $y_{1},\dots,y_{n+1}\in L$. Choose one s.t. as few of them as possible are non-zero. Modulo renumbering we can assume that $y_{1},\dots,y_{r}\neq 0$ and $y_{r+1},\dots,y_{n+1}=0$. Therefore, we have: $$\sigma_{j}(w_{1})y_{1}+\dots+\sigma_{j}(w_{r})y_{r}=0$$for $j\in[n]$. For $\sigma\in G$, we now have: $$\sigma\sigma_{j}(w_{1})\sigma(y_{1})+\dots+\sigma\sigma_{j}(w_{r})\sigma(y_{r})=0$$As $\{ \sigma\sigma_{j} \}_{j\in[n]}=G$, for all $\ell\in[n]$,$$\sigma_{\ell}(w_{1})\sigma(y_{1})+\dots+\sigma_{\ell}(w_{r})\sigma(y_{r})=0$$Therefore, we get that: $$\sigma_{\ell}(w_{2})(\sigma(y_{2})y_{1}-\sigma(y_{1})y_{2})+\dots+\sigma_{\ell}(w_{r})(\sigma(y_{r})y_{1}-\sigma(y_{1})y_{r})=0$$From the minimality of $r$, we have that $\sigma(y_{1})y_{\ell}=\sigma(y_{\ell})y_{1}$ for all $\ell=2,\dots,r$. This happens if $y_{\ell}y_{1}^{-1}=\sigma(y_{\ell}y_{1}^{-1})$ for all $\sigma\in G$, i.e. $y_{\ell}y_{1}^{-1}\in L_{0}$ for all $\ell=1,\dots,r$. Therefore, there exists $z_{1},\dots,z_{r}\in L_{0}$ and $0\neq k\in L$ s.t. $$y_{\ell}=kz_{\ell}, \quad \ell=1,\dots,r$$Plugging this in with $\sigma=\text{id}_{L}$, $$w_{1}(kz_{1})+\dots+w_{r}(kz_{r})=0$$As $k\neq 0$, $w_{1}z_{1}+\dots+w_{r}z_{r}=0$. This shows that $\{ w_{1},\dots,w_{r} \}$ are linearly dependent, which is a contradiction.
---
> [!lemma] Corollary 3
> Let $L:K$ be a finite extension and $G:=\text{Gal}(L:K)=\gamma(K)$. Then, $$\left| \text{Gal}(L:K) \right|\leq[L:K] $$with equality if and only if $K=\phi(G)=L^{\text{Gal}(L:K)}$, i.e. $K=(\phi \circ\gamma)(K)$

> [!proof]-
> Let $L_{0}:=\text{Fix}(G)$. Then, $K\subseteq L_{0}\subseteq L$. By Theorem 2, we have $[L:L_{0}]=\left| \text{Gal}(L:K) \right|$. Hence, $$[L:K]=[L:L_{0}][L_{0}:K]=\left| \text{Gal}(L:K) \right| [L_{0}:K]$$We have $\left| \text{Gal}(L:K) \right|=[L:K]$ if and only if $[L_{0}:K]=1$ if and only if $L_{0}=K$ if and only if $K=\text{Fix}(G)$. 
---
> [!lemma] Corollary 4
> Let $G$ be a finite subgroup of $\text{Aut}(L)$ and $K=\text{Fix}(G)$. Then, every automorphism of $L$ fixing $K$ is contained in $G$, i.e. $\text{Gal}(L:K)=G$.

> [!proof]-
> By definition $K$ is fixed by all elements of $G$. So $G\subseteq \text{Gal}(L:K)$. By Theorem 2, we have: $$\left| G \right| =[L:L^G]=[L:K]$$By Corollary 3, $[L:K]= \left| G \right|\leq \left| \text{Gal}(L:K) \right|\leq[L:K]$ and $[L:K]=\left| G \right|$.
---
> [!lemma] Corollary 5
> If $G_{1}\neq G_{2}$ be distinct finite subgroups of $\text{Aut}(L)$. Then, their fixed fields are also distinct. 
---
> [!lemma] Corollary 6
> Let $G:=\text{Gal}(L:K)$ with $[L:K]<+\infty$ and $H\leq G$. Then, $$[L^H:K]=[L:K] / \left| H \right| $$

> [!proof]-
> Apply Theorem 2 to $H\leq \text{Aut}(L)$ and $[L:L^H]=\left| H \right|$. Therefore, $$[L:K]=[L:L^H][L^H:K]$$
---
##### Examples
> [!h] Example 1 (Finite Fields)
> Every extension $L:K$ of finite fields is Galois. Then, $$\text{Gal}(L:K)\cong \mathbb{Z} / {[L:K]\mathbb{Z}}$$
---
