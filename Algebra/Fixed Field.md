#Definition #Algebra 

> [!definition]
> Let $L$ be a [[field]] and $H\leq \text{Aut}(L)$. 
> 1. The ***fixed field***, denoted as $\text{Fix}(H)$ or $L^H$, is defined as: $$L^H:=\{ \ell\in L:\sigma(\ell)=\ell, \forall\sigma\in H \}$$

---
##### Properties
> [!lemma] Lemma 1 (Fixed Field Properties)
> For $L$ and $H\leq \text{Aut}(L)$, 
> 1. $L^H$ is a subfield of $L$. 

> [!proof]-
> We have that:
> 1. for $a,b\in L^H$ and $\sigma\in H$, 
> 	1. $\sigma(a+ b)=\sigma(a)+\sigma(b)=a+b$ and $a+b\in L^H$. 
> 	2. $\sigma(ab)=\sigma(a)\sigma(b)=ab$ and $ab\in L^H$.
> 	3. $\sigma(a^{-1})=\sigma(a)^{-1}=a^{-1}$ and $a^{-1}\in L^H$.

---
> [!lemma] Theorem 2
> Let $L$ be a field and $G\leq \text{Aut}(L)$ a finite subgroup. Then, $$[L:L^G]=\left| G \right| $$

> [!proof]-
> We prove it by contradiction. Assume $[L:L^G]\neq \left| G \right|$. Then, 
> 1. Suppose that $[L:L^G]=:m<n=:\left| G \right|$. Let $\{ w_{1},\dots,w_{m} \}$ be the basis of $L$ over $L^G$. Let $G=\{ \sigma_{1},\dots,\sigma_{n} \}$ and consider the system: $$\sigma_{1}(w_{j})y_{1}+\dots+\sigma_{n}(w_{j})y_{n}=0$$for all $j\in [m]$. Then, as there are more unknowns than the number of equations, there exists a non-trivial solution $y_{i}\in L$. Therefore, we have that: $$(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(w_{j})=0$$for all $j\in[m]$ on a basis of $L$ over $L^G$. Let now $a=\sum_{i=1}^{m}a_{i}w_{i}\in L$ with $a_{i}\in L^G$. Then, $$(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(a)=\sum_{i=1}^{m}a_{i}(y_{1}\sigma_{1}+\dots+y_{n}\sigma_{n})(w_{i})=0$$Therefore, $\sigma_{1},\dots,\sigma_{n}$ are linearly dependent, which contradicts [[Character|Theorem 2]].
> 
> 2. Suppose now that $[L:L^G]=m>n=\left| G \right|$. Let $\{ w_{1},\dots,w_{n+1} \}\subseteq L$ be linearly independent. Then, the equations: $$\sigma_{j}(w_{1})y_{1}+\dots+\sigma_{j}(w_{n+1})y_{n+1}=0$$for all $j\in[n]$. As there are more unknowns than equations, there exists a non-trivial solution $y_{1},\dots,y_{n+1}\in L$. Choose one s.t. as few of them as possible are non-zero. Modulo renumbering we can assume that $y_{1},\dots,y_{r}\neq 0$ and $y_{r+1},\dots,y_{n+1}=0$. Therefore, we have: $$\sigma_{j}(w_{1})y_{1}+\dots+\sigma_{j}(w_{r})y_{r}=0$$for $j\in[n]$. For $\sigma\in G$, we now have: $$\sigma\sigma_{j}(w_{1})\sigma(y_{1})+\dots+\sigma\sigma_{j}(w_{r})\sigma(y_{r})=0$$As $\{ \sigma\sigma_{j} \}_{j\in[n]}=G$, for all $\ell\in[n]$,$$\sigma_{\ell}(w_{1})\sigma(y_{1})+\dots+\sigma_{\ell}(w_{r})\sigma(y_{r})=0$$Therefore, we get that: $$\sigma_{\ell}(w_{2})(\sigma(y_{2})y_{1}-\sigma(y_{1})y_{2})+\dots+\sigma_{\ell}(w_{r})(\sigma(y_{r})y_{1}-\sigma(y_{1})y_{r})=0$$From the minimality of $r$, we have that $\sigma(y_{1})y_{\ell}=\sigma(y_{\ell})y_{1}$ for all $\ell=2,\dots,r$. This happens if $y_{\ell}y_{1}^{-1}=\sigma(y_{\ell}y_{1}^{-1})$ for all $\sigma\in G$, i.e. $y_{\ell}y_{1}^{-1}\in L_{0}$ for all $\ell=1,\dots,r$. Therefore, there exists $z_{1},\dots,z_{r}\in L_{0}$ and $0\neq k\in L$ s.t. $$y_{\ell}=kz_{\ell}, \quad \ell=1,\dots,r$$Plugging this in with $\sigma=\text{id}_{L}$, $$w_{1}(kz_{1})+\dots+w_{r}(kz_{r})=0$$As $k\neq 0$, $w_{1}z_{1}+\dots+w_{r}z_{r}=0$. This shows that $\{ w_{1},\dots,w_{r} \}$ are linearly dependent, which is a contradiction.
---
##### Examples
> [!h] Example 1
> Let $\alpha$ be the real root of $x^3-2\in \mathbb{Q}[X]$. Then, $$\text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})=\{ \text{id} \}=\gamma(\mathbb{Q})$$Hence, $\phi(\gamma(\mathbb{Q}))=\phi(\text{id})=\mathbb{Q}(\alpha)$ and $\mathbb{Q}\subsetneq \mathbb{Q}(\alpha)$. We have: $\left| \text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q}) \right|<[\mathbb{Q}(\alpha):\mathbb{Q}]$
---
> [!h] Example 2
> Let $f(x):=x^p-t\in\mathbb{F}_{p}(t)[X]$ which is irreducible with $\alpha$ as root with multiplicity $p$. Then, $$\text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t))=\{ \text{id} \}$$We then have: $\left| \text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)) \right|<[\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)]$
---
