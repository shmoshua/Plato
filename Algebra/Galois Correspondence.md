#Definition #Algebra 

> [!definition]
> Given a field extension $L:K$, let:
> 1. $\mathcal{F}$ be the set of subfields $M\subseteq L$ with $K\subseteq M$.
> 2. $\mathcal{G}$ be the set of subgroups of the [[Galois group]] $\text{Gal}(L:K)$
>    
>  Then, the ***Galois correspondence*** are the following two maps: $$\begin{array}{cccc} {\gamma:}&{\mathcal{F}}&\to&{\mathcal{G}}\\&{M} &\mapsto & {\text{Gal}(L:M)} \end{array}{}\quad \quad \begin{array}{cccc} {\phi:}&{\mathcal{G}}&\to&{\mathcal{F}}\\&{H} &\mapsto & {L^H} \end{array}{}$$where $L^H$ denotes the [[fixed field]] $L^H=\{ \ell\in L:\sigma(\ell)=\ell, \forall\sigma\in H \}$.
---
##### Properties
> [!lemma] Lemma 1
It holds that: 
> 1. $\gamma(K)=\text{Gal}(L:K)$
> 2. $\gamma(L)=\text{Gal}(L:L)=\{ \text{id} \}$
> 3. if $M\subseteq N$, then $\text{Gal}(L:M)=\gamma(M)\supseteq \gamma(N)= \text{Gal}(L:N)$
> 4. if $H\leq G$, then $\phi(G)\subseteq \phi(H)$

^f02def

> [!proof]-
> 1 and 2 follow from the definition. For 3, for $\sigma\in \text{Gal}(L:N)$, $\sigma|_{N}=\text{id}_{N}$ and $\sigma|_{M}=\text{id}_{M}$. Lastly, if $\ell\in L^G$ then for every $\sigma\in H\subseteq G$, $\sigma(\ell)=\ell$. 

^26a836

---
> [!lemma] Theorem 2
> Suppose $L:K$ is an extension, $G:=\text{Gal}(L:K)$, $H\subseteq G$ and $K\subseteq M\subseteq L$. Then, 
> 1. $(\gamma \circ\phi)(H) \supseteq H$
> 2. $(\phi \circ\gamma)(M)\supseteq M$
> 3. $(\phi \circ\gamma \circ\phi)(H)=\phi(H)$
> 4. $(\gamma \circ\phi \circ\gamma)(M)=\gamma(M)$

^ffd98d

> [!proof]-
> We have: 
> 1. let $\sigma\in H\subseteq \text{Gal}(L:K)$. Let $\ell\in \phi(H)$. Then, by definition, $\sigma(\ell)=\ell$. Therefore, $$\sigma\in \text{Gal}(L:\phi(H))=\gamma(\phi(H))$$
> 2. let $m\in M$. Then, $\sigma(m)=m$ for all $\sigma\in \text{Gal}(L:M)=\gamma(M)$. Therefore, $m\in \phi(\gamma(M))$.
> 3. As $\gamma(\phi(H))\supseteq H$ from 1, we have from Lemma 1, $\phi(\gamma(\phi(H)))\subseteq \phi(H)$. However, by 2, we have the equality.
> 4. Similarly, $\gamma(\phi(\gamma(M)))\supseteq\gamma(M)$ and from Lemma 1, $\gamma(\phi(\gamma(M)))\subseteq\gamma(M)$.

^9c8ee6

---
> [!lemma] Lemma 3
> Let $L:K$ be an extension and $K\subseteq M\subseteq L$. For $\tau\in \text{Aut}_{K}(L)$, $$\gamma(\tau(M))=\tau \gamma(M)\tau ^{-1}$$

> [!proof]-
> Let $\tilde{M}:=\tau(M)$. Take $\sigma\in \gamma(M)$ and $\tilde{x}\in \tilde{M}$. Then, there exists $x\in M$ s.t. $\tau(x)=\tilde{x}$. Therefore, $$(\tau\sigma \tau ^{-1})(\tilde{x})=\tau\sigma(x)=\tau(x)=\tilde{x}$$Therefore, $\tau\sigma \tau ^{-1}\in \gamma(\tilde{M})$ and $\tau\gamma(M)\tau ^{-1}\subseteq \gamma(\tau(M))$.  
> 
> Conversely, take $\sigma\in \gamma(\tilde{M})$ and $x\in M$. Then, $$(\tau ^{-1}\sigma \tau)(x)=\tau ^{-1}(\tau(x))=x$$Therefore, $\tau ^{-1}\gamma(\tau(M))\tau \subseteq \gamma(M)$, which proves the statement.
---
> [!lemma] Theorem 4 (The Fundamental Theorem of Galois Correspondence)
> Let $L:K$ be finite [[Galois Extension|Galois]] of degree $n$. Then, 
> 1. $\left| \text{Gal}(L:K) \right|=[L:K]=n$.
> 2. the maps $\phi,\gamma$ are mutual inverses.
> 3. if $M\in \mathcal{F}$, then $[L:M]=\left| \gamma(M) \right|$ and $[M:K]=\left| \text{Gal}(L:K) \right| / \left| \gamma(M) \right|$.
> 4. an intermediate field $M:K$ is normal if and only if $\gamma(M)\unlhd \text{Gal}(L:K)$
> 5. if $M:K$ is normal, $\text{Gal}(M:K)\cong \text{Gal}(L:K) / \gamma(M)$.  

> [!proof]+
> We have:
> 1. [[Galois Extension|Theorem 1]]
> 2. Let $M\in \mathcal{F}$. Then, $L:M$ is Galois from [[Galois Extension|Corollary of Theorem 1]]. Therefore, by [[Galois Extension|Corollary 3]], $\phi\gamma(M)=M$.
>    
>    Conversely, let $H\in \mathcal{G}$, i.e. $H\leq \text{Gal}(L:K)$. Then, $H\subseteq\gamma(\phi(H))$ and $\phi(H)=\phi(\gamma(\phi(H)))$. By [[Galois Extension|Theorem 2]], $\left| L:\phi(H) \right|=\left| H \right|$. Therefore, $$\left| H \right| =[L:\phi(H)]=[L:\phi(\gamma(\phi(H)))]=\left| \gamma(\phi(H)) \right| $$ and $H=\gamma(\phi(H))$.
>3. As $L:M$ is normal, $[L:M]=\left| \gamma(M) \right|$ and $$[M:K]=\frac{[L:K]}{[L:M]}=\frac{\left| \text{Gal}(L:K) \right| }{\left| \text{Gal}(L:M) \right| }$$
>4. Suppose $M:K$ is normal. Let $\tau\in \text{Gal}(L:K)$. Then, by [[K-Homomorphism|Theorem 1]] $\tau|_{M}\in \text{Mono}_{K}(M,L)$. By [[Normal Extension|Theorem 2]], $\tau|_{M}\in \text{Aut}_{K}(M)$ and $\tau(M)=M$. By Lemma 3, $$\gamma(M)=\tau\gamma(M)\tau ^{-1}$$
>   Conversely, let $\gamma(M)\unlhd \text{Gal}(L:K)$. Let $\sigma\in \text{Mono}_{K}(M:L)$. As $L:K$ is normal, by [[K-Homomorphism|Theorem 1]], there exists $\tau\in \text{Gal}(L:K)$ s.t. $\tau|_{M}=\sigma$.  From the normality, $$\tau\gamma(M)\tau ^{-1}=\gamma(M)$$Then, by Lemma 3, $\gamma(M)=\gamma(\tau(M))$ and by 2, $$
---
##### Examples
> [!h] Example 1
> Let $f(x):=(x^2+1)(x^{2}-5)\in \mathbb{Q}[X]$. Then, 
> 1. $L:=\mathbb{Q}(i,\sqrt{ 5 })$ is the splitting field and $f$ is separable, i.e. $L:\mathbb{Q}$ is Galois with degree 4.
> 2. $\text{Gal}(L:\mathbb{Q})\cong \mathbb{Z}_{2}\times \mathbb{Z}_{2}$