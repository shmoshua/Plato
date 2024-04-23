#Definition #Algebra 

> [!definition]
> Let $L$ be a [[field]] and $H\leq \text{Aut}(L)$. The ***fixed field***, denoted as $\text{Fix}(H)$ or $L^H$, is defined as: $$L^H:=\{ \ell\in L:\sigma(\ell)=\ell, \forall\sigma\in H \}$$
- **Remark**: One can check that $L^H$ is a subfield of $L$. 
- **Related definition**: Given a field extension $L:K$, let:
   1. $\mathcal{F}$ be the set of subfields $M\subseteq L$ with $K\subseteq M$.
   2. $\mathcal{G}$ be the set of subgroups of the [[Galois group]] $\text{Gal}(L:K)$
      
  Then, the ***Galois correspondence*** are the following two maps: $$\begin{array}{cccc} {\gamma:}&{\mathcal{F}}&\to&{\mathcal{G}}\\&{M} &\mapsto & {\text{Gal}(L:M)} \end{array}{}\quad \quad \begin{array}{cccc} {\phi:}&{\mathcal{G}}&\to&{\mathcal{F}}\\&{H} &\mapsto & {L^H} \end{array}{}$$
---
##### Properties
> [!lemma] Lemma 1
It holds that: 
> 1. $\gamma(K)=\text{Gal}(L:K)$
> 2. $\gamma(L)=\text{Gal}(L:L)=\{ \text{id} \}$
> 3. if $M\subseteq N$, then $\text{Gal}(L:M)=\gamma(M)\supseteq \gamma(N)= \text{Gal}(L:N)$
> 4. if $H\leq G$, then $\phi(G)\subseteq \phi(H)$

> [!proof]-
> 1 and 2 follow from the definition. For 3, for $\sigma\in \text{Gal}(L:N)$, $\sigma|_{N}=\text{id}_{N}$ and $\sigma|_{M}=\text{id}_{M}$. Lastly, if $\ell\in L^G$ then for every $\sigma\in H\subseteq G$, $\sigma(\ell)=\ell$. 
---
> [!lemma] Theorem 2
> Suppose $L:K$ is an extension, $G:=\text{Gal}(L:K)$, $H\subseteq G$ and $K\subseteq M\subseteq L$. Then, 
> 1. $(\gamma \circ\phi)(H) \supseteq H$
> 2. $(\phi \circ\gamma)(M)\supseteq M$
> 3. $(\phi \circ\gamma \circ\phi)(H)=\phi(H)$
> 4. $(\gamma \circ\phi \circ\gamma)(M)=\gamma(M)$

> [!proof]-
> We have: 
> 1. let $\sigma\in H\subseteq \text{Gal}(L:K)$. Let $\ell\in \phi(H)$. Then, by definition, $\sigma(\ell)=\ell$. Therefore, $$\sigma\in \text{Gal}(L:\phi(H))=\gamma(\phi(H))$$
> 2. let $m\in M$. Then, $\sigma(m)=m$ for all $\sigma\in \text{Gal}(L:M)=\gamma(M)$. Therefore, $m\in \phi(\gamma(M))$.
> 3. As $\gamma(\phi(H))\supseteq H$ from 1, we have from Lemma 1, $\phi(\gamma(\phi(H)))\subseteq \phi(H)$. However, by 2, we have the equality.
> 4. Similarly, $\gamma(\phi(\gamma(M)))\supseteq\gamma(M)$ and from Lemma 1, $\gamma(\phi(\gamma(M)))\subseteq\gamma(M)$.
---
##### Examples
> [!h] Example 1
> Let $\alpha$ be the real root of $x^3-2\in \mathbb{Q}[X]$. Then, $$\text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})=\{ \text{id} \}=\gamma(\mathbb{Q})$$Hence, $\phi(\gamma(\mathbb{Q}))=\phi(\text{id})=\mathbb{Q}(\alpha)$ and $\mathbb{Q}\subsetneq \mathbb{Q}(\alpha)$. We have: $\left| \text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q}) \right|<[\mathbb{Q}(\alpha):\mathbb{Q}]$
---
> [!h] Example 2
> Let $f(x):=x^p-t\in\mathbb{F}_{p}(t)[X]$ which is irreducible with $\alpha$ as root with multiplicity $p$. Then, $$\text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t))=\{ \text{id} \}$$We then have: $\left| \text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)) \right|<[\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)]$
---
