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
##### Examples
> [!h] Example 1
> Let $\alpha$ be the real root of $x^3-2\in \mathbb{Q}[X]$. Then, $$\text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})=\{ \text{id} \}=\gamma(\mathbb{Q})$$Hence, $\phi(\gamma(\mathbb{Q}))=\phi(\text{id})=\mathbb{Q}(\alpha)$ and $\mathbb{Q}\subsetneq \mathbb{Q}(\alpha)$. We have: $\left| \text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q}) \right|<[\mathbb{Q}(\alpha):\mathbb{Q}]$
---
> [!h] Example 2
> Let $f(x):=x^p-t\in\mathbb{F}_{p}(t)[X]$ which is irreducible with $\alpha$ as root with multiplicity $p$. Then, $$\text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t))=\{ \text{id} \}$$We then have: $\left| \text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)) \right|<[\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)]$
---
