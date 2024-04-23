#Definition #Algebra 

> [!definition]
> Let $L$ be a [[field]] and $H\leq \text{Aut}(L)$. The ***fixed field***, denoted as $\text{Fix}(H)$ or $L^H$, is defined as: $$L^H:=\{ \ell\in L:\sigma(\ell)=\ell, \forall\sigma\in H \}$$
- **Remark**: One can check that $L^H$ is a subfield of $L$. 
- **Related definition**: Given a field extension $L:K$, let:
   1. $\mathcal{F}$ be the set of subfields $M\subseteq L$ with $K\subseteq M$.
   2. $\mathcal{G}$ be the set of subgroups of the [[Galois group]] $\text{Gal}(L:K)$
      
  Then, there exists the following two maps: $$\begin{array}{cccc} {\gamma:}&{\mathcal{F}}&\to&{\mathcal{G}}\\&{M} &\mapsto & {\text{Gal}(L:M)} \end{array}{}\quad \quad \begin{array}{cccc} {\phi:}&{\mathcal{G}}&\to&{\mathcal{F}}\\&{H} &\mapsto & {L^H} \end{array}{}$$
---
##### Properties
> [!lemma] Lemma 1
It holds that: 
> 1. $\gamma(K)=\text{Gal}(L:K)$
> 2. $\gamma(L)=\text{Gal}(L:L)=\{ \text{id} \}$
> 3. if $M\subseteq N$, then $\text{Gal}(L:M)=\gamma(M)\supseteq \gamma(N)= \text{Gal}(L:N)$
> 4. if $H\leq G$, then $\phi(G)\subseteq \phi(H)$
---
> [!lemma] Theorem 2
> Suppose $L:K$ is an extension, $G:=\text{Gal}(L:K)$, $H\subseteq G$ and $K\subseteq M\subseteq L$. Then, 
> 1. $(\gamma \circ\phi)(H) \supseteq H$
> 2. $(\phi \circ\gamma)(M)\supseteq M$
> 3. $(\phi \circ\gamma \circ\phi)(H)=\phi(H)$
> 4. $(\gamma \circ\phi \circ\gamma)(M)=\gamma(M)$