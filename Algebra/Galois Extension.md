#Definition #Algebra 

> [!definition]
> A [[field extension]] $L:K$ is ***Galois***, if $L:K$ is [[Separable Extension|separable]] and [[Normal Extension|normal]].
---
##### Properties
> [!lemma] Theorem 1
> Let $L:K$ be finite. Then, TFAE:
> 1. $\left| \text{Gal}(L:K) \right|=[L:K]$
> 1. $L:K$ is Galois, in which case $L$ is a splitting field of a separable polynomial $f\in K[X]$.

> [!proof]+
> We have:
> 1. Let $\text{Gal}(L:K)=\{ \sigma_{1},\dots,\sigma_{n} \}$. 
> 	1. **Showing $L:K$ is normal**:
> 	   Let $f\in K[X]$ be a irreducible polynomial with a root $\alpha\in L$. Assume $\sigma_{1}=\text{id}$ wlog and let there be $r\leq n$ distinct images of $\alpha$ under $\sigma_{i}$. Define them as $\alpha_{1},\dots,\alpha_{r}$ where $\alpha_{1}=\sigma_{1}(\alpha)=\alpha$. $\alpha_{1},\dots,\alpha_{r}$ are $r$ distinct roots of $f$ in $L$. 
> 	   
> 	   Now for $\sigma\in \text{Gal}(L:K)$, then it s injective on $\{ \alpha_{1},..,\alpha_{r} \}$ and therefore surjective, i.e. $\sigma$ permutes the roots. We then define: 
> 	   1. $s_{1}:=\sum_{i=1}^{r}\alpha_{i}$
> 	   2. $s_{2}:=\sum_{i<j}^{}\alpha_{i}\alpha_{j}$
> 	   3. $s_{r}:=\prod_{i=1}^{}\alpha_{j}$
> 	   
> 	   Then, $\sigma(s_{i})=s_{i}$ and $s_{i}\in L^{\text{Gal}(L:K)}$ for all $i\in[r]$. As [[Galois Group|Theorem 3]] states that $\left| \text{Gal}(L:K) \right|=[L:K]$ if and only if $K=L^{\text{Gal}(L:K)}$, $s_{i}\in K$ for all $i\in [r]$.  Now, let: $$g(x):=(x-\alpha_{1})\dots(x-\alpha_{r})=x^r-s_{1}x^{r-1}+s_{2}x^{r-2}+\dots+(-1)^rs_{r}\in K[X]$$Since each $\alpha_{i}\in L$, $g$ splits over $L$. 
> 	   
> 	   We claim that $g=m_{\alpha,K}$. Let $h(x):=b_{0}+b_{1}x+\dots+b_{m}x^m\in K[X]$ with $\alpha$ as root. By applying $\sigma_{i}$, we know that: $$h(\sigma_{i}(\alpha))=\sigma_{i}(b_{0}+b_{1}\alpha+\dots+b_{m}\alpha^m)=\sigma_{i}(0)=0$$Therefore, $\alpha_{i}$ is a root of $h$ as well, and $g|h$, therefore, $g=m_{\alpha,K}$.
> 	   
> 	   However, $f$ is irreducible with $\alpha$ as root. Therefore, $f$ is a constant multiple of $g$ and $f$ splits over $L$, i.e. $L:K$ is normal.

> [!proof]+
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
>   
>  2. **Showing $L:K$ is separable**:
>     Further $L:K$ is separable, because $\alpha_{1},\dots,\alpha_{r}$ are distinct and $\alpha$ is separable.
>  3. **Showing $L$ is a splitting field**:
>     Since $L:K$ is normal, separable and finite, let $L=K(\alpha_{1},\dots,\alpha_{n})$ and let $p_{i}(x)$ be the minimal polynomial of $\alpha_{i}$ over $K$. Since $L:K$ is normal, $L$ has all the roots of $p_{i}$.  As $L:K$ is separable, $p_{i}$ is separable and $L$ is the splitting field of the product of $p_{i}$ where this polynomial is also separable.
>   4. **Other implication**:
>      [[Galois Group|Theorem 4]]

- **Corollary**: If $L:K$ is a Galois extension and $K\subseteq M\subseteq L$, then $L:M$ is also Galois (cf. [[Separable Extension|Lemma 1]] and [[Normal Extension|Corollary 3]])
- **Remark**: In the scenario above, $M:K$ is not necessarily Galois, e.g. $\mathbb{Q}(\sqrt[4]{2  }, i):\mathbb{Q}(\sqrt[4]{2  }):\mathbb{Q}$

---

##### Examples
> [!h] Example 1 (Finite Fields)
> Every extension $L:K$ of finite fields is Galois. Then, $$\text{Gal}(L:K)\cong \mathbb{Z} / {[L:K]\mathbb{Z}}$$
---
