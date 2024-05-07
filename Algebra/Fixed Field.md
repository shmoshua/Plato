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
![[Galois Correspondence#^f02def]]
![[Galois Correspondence#^26a836|p]]

---
![[Galois Correspondence#^ffd98d]]
![[Galois Correspondence#^9c8ee6|p]]

---
##### Examples
> [!h] Example 1
> Let $\alpha$ be the real root of $x^3-2\in \mathbb{Q}[X]$. Then, $$\text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q})=\{ \text{id} \}=\gamma(\mathbb{Q})$$Hence, $\phi(\gamma(\mathbb{Q}))=\phi(\text{id})=\mathbb{Q}(\alpha)$ and $\mathbb{Q}\subsetneq \mathbb{Q}(\alpha)$. We have: $\left| \text{Gal}(\mathbb{Q}(\alpha):\mathbb{Q}) \right|<[\mathbb{Q}(\alpha):\mathbb{Q}]$
---
> [!h] Example 2
> Let $f(x):=x^p-t\in\mathbb{F}_{p}(t)[X]$ which is irreducible with $\alpha$ as root with multiplicity $p$. Then, $$\text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t))=\{ \text{id} \}$$We then have: $\left| \text{Gal}(\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)) \right|<[\mathbb{F}_{p}(t)(\alpha):\mathbb{F}_{p}(t)]$
---
