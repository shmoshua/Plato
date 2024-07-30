#Definition #Algebra 

> [!definition]
> Given a [[field extension]] $L:K$, let:
> 1. $\mathcal{F}$ be the set of subfields $M\subseteq L$ with $K\subseteq M$.
> 2. $\mathcal{G}$ be the set of subgroups of the [[Galois group]] $\text{Gal}(L:K)$
>    
>  Then, the ***Galois correspondence*** are the following two maps: $$\begin{array}{cccc} {\gamma:}&{\mathcal{F}}&\to&{\mathcal{G}}\\&{M} &\mapsto & {\text{Gal}(L:M)} \end{array}{}\quad \quad \begin{array}{cccc} {\phi:}&{\mathcal{G}}&\to&{\mathcal{F}}\\&{H} &\mapsto & {L^H} \end{array}{}$$where $L^H$ denotes the [[fixed field]] $L^H=\{ \ell\in L:\sigma(\ell)=\ell, \forall\sigma\in H \}$.
---
##### Properties
> [!lemma] Lemma 1
For a field extension $L:K$, we have:
> 1. $\gamma(K)=\text{Gal}(L:K)$
> 2. $\gamma(L)=\text{Gal}(L:L)=\{ \text{id} \}$
> 3. if $M\subseteq N$, then $\text{Gal}(L:N)=\gamma(N)\leq\gamma(M)=\text{Gal}(L:M)$ 
> 4. if $H\leq G$, then $\phi(G)\subseteq \phi(H)$


> [!proof]-
> We have:
> 1. Obvious.
> 2. $\text{Gal}(L:L)=\text{Aut}_{L}(L)=\{ \text{id} \}$.
> 3. For $\sigma\in \text{Gal}(L:N)$, $\sigma(m)=m$ for all $m\in M$ and $\sigma\in \text{Gal}(L:M)$.
> 4. For $\ell\in L^G$ and $\sigma\in H\subseteq G$, $\sigma(\ell)=\ell$.

---
> [!lemma] Theorem 2
> For a field extension $L:M:K$ and $H\leq\text{Gal}(L:K)$,
> 1. $(\gamma \circ\phi)(H) \geq H$
> 2. $(\phi \circ\gamma)(M)\supseteq M$
> 3. $(\phi \circ\gamma \circ\phi)(H)=\phi(H)$
> 4. $(\gamma \circ\phi \circ\gamma)(M)=\gamma(M)$


> [!proof]-
> We have: 
> 1. let $\sigma\in H\leq \text{Gal}(L:K)$. For $\ell\in \phi(H)$, we have that $\sigma(\ell)=\ell$. Therefore, $$\sigma\in \text{Gal}(L:\phi(H))=\gamma(\phi(H))$$
> 2. let $m\in M$ and $\sigma\in \gamma(M)$. Then, $\sigma(m)=m$ and $m\in \phi(\gamma(M))$.
> 3. As $\gamma(\phi(H))\supseteq H$ from 1, we have from Lemma 1, $\phi(\gamma(\phi(H)))\subseteq \phi(H)$. However, by 2, we have the equality.
> 4. Similarly, $\gamma(\phi(\gamma(M)))\supseteq\gamma(M)$ and from Lemma 1, $\gamma(\phi(\gamma(M)))\subseteq\gamma(M)$.

---
> [!lemma] Lemma 3
> Let $L:K$ be an extension and $K\subseteq M\subseteq L$. For $\tau\in \text{Aut}_{K}(L)$, $$\gamma(\tau(M))=\tau \gamma(M)\tau ^{-1}$$

> [!proof]-
> Let $\tilde{M}:=\tau(M)$. Take $\sigma\in \gamma(M)$ and $\tilde{x}\in \tilde{M}$. Then, there exists $x\in M$ s.t. $\tau(x)=\tilde{x}$. Therefore, $$(\tau\sigma \tau ^{-1})(\tilde{x})=\tau\sigma(x)=\tau(x)=\tilde{x}$$Therefore, $\tau\sigma \tau ^{-1}\in \gamma(\tilde{M})$ and $\tau\gamma(M)\tau ^{-1}\subseteq \gamma(\tau(M))$.  
> 
> Conversely, take $\sigma\in \gamma(\tilde{M})$ and $x\in M$. Then, $$(\tau ^{-1}\sigma \tau)(x)=\tau ^{-1}(\tau(x))=x$$Therefore, $\tau ^{-1}\gamma(\tau(M))\tau \subseteq \gamma(M)$, which proves the statement.
---
> [!lemma] Theorem 4 (The Fundamental Theorem of Galois Correspondence)
> Let $L:K$ be finite [[Galois Extension|Galois]]. Then, 
> 1. $\left| \text{Gal}(L:K) \right|=[L:K]$.
> 2. the maps $\phi,\gamma$ are mutual inverses.
> 3. if $M\in \mathcal{F}$, then $[L:M]=\left| \gamma(M) \right|$ and $[M:K]=\left| \text{Gal}(L:K) \right| / \left| \gamma(M) \right|$.
> 4. an intermediate field $M:K$ is normal if and only if $\gamma(M)\unlhd \text{Gal}(L:K)$
> 5. if $M:K$ is normal, $\text{Gal}(M:K)\cong \text{Gal}(L:K) / \gamma(M)$.  

> [!proof]-
> We have:
> 1. [[Galois Extension|Theorem 1]].
> 2. Let $M\in \mathcal{F}$. Then, $L:M$ is Galois from [[Galois Extension|Corollary of Theorem 1]]. Therefore, by [[Galois Extension|Theorem 1]], $$\phi\gamma(M)=L^{\text{Gal}(L:M)}=M$$
>    
>    Conversely, let $H\in \mathcal{G}$, i.e. $H\leq \text{Gal}(L:K)$. Then, $H\subseteq\gamma(\phi(H))$ and $\phi(H)=\phi(\gamma(\phi(H)))$. Then, from [[Galois Group|Corollary 4]] $\left| H \right| =\left| \text{Gal}(L,L^H) \right|=\left| \gamma(\phi(H)) \right|$ and $H=\gamma(\phi(H))$.
> 3. As $L:M$ is Galois, $[L:M]=\left|\text{Gal}(L:M) \right|=\left| \gamma(M) \right|$ and $$[M:K]=\frac{[L:K]}{[L:M]}=\frac{\left| \text{Gal}(L:K) \right| }{\left| \gamma(M) \right| }$$
> 4. Suppose $M:K$ is normal. Then, by [[Normal Extension|Theorem 2]], $\text{Mono}_{K}(M,L)=\text{Aut}_{K}(M)$. Hence, for any $\tau\in \text{Gal}(L:K)$. Then, by [[K-Homomorphism|Theorem 1]] $\tau|_{M}\in \text{Aut}_{K}(M)$ and $\tau(M)=M$. By Lemma 3, $$\gamma(M)=\tau\gamma(M)\tau ^{-1}$$
>   
>    Conversely, let $\gamma(M)\unlhd \text{Gal}(L:K)$. Let $\sigma\in \text{Mono}_{K}(M,L)$. As $L:K$ is normal, by [[K-Homomorphism|Theorem 1]], there exists $\tau\in \text{Gal}(L:K)$ s.t. $\tau|_{M}=\sigma$.  From the normality, $$\tau\gamma(M)\tau ^{-1}=\gamma(M)$$Then, by Lemma 3, $\gamma(M)=\gamma(\tau(M))$ and by 2, $M=\tau(M)$. Therefore, $$\sigma(M)=\tau(M)=M$$and $\sigma\in \text{Aut}_{K}(M)$. By [[Normal Extension|Theorem 2]], $M:K$ is normal.
> 5. Let $M:K$ be normal. We define: $$\begin{array}{cccc} {\theta:}&{\text{Gal}(L:K)}&\to&{\text{Gal}(M:K)}\\&{\sigma} &\mapsto & {\sigma|_{M}} \end{array}{}$$As $M:K$ is normal, $\sigma|_{M}\in \text{Aut}_{K}(M)=\text{Gal}(M:K)$. Further, by [[K-Homomorphism|Theorem 1]] we have the surjectivity of $\theta$.
>   
>    Lastly, let $\sigma\in \text{ker }\theta$. Then, $\sigma|_{M}=\text{id}_{M}$. Therefore, $\sigma\in \text{Gal}(L:M)=\gamma(M)$. This proves that $\text{Gal}(M:K)\cong \text{Gal}(L:K) / \gamma(M)$.
---
> [!lemma] Theorem 5 (Intermediate Composite Fields)
> Let $L:K$ be a finite Galois extension with intermediate fields $K_{1},K_{2}$. Then, 
> 1. $K_{1}K_{2}=L^{\text{Gal}(L:K_{1})\cap \text{Gal}(L:K_{2})}$
> 2. $K_{1}\cap K_{2}=L^{\braket{ \text{Gal}(L:K_{1}) ,\text{Gal} (L:K_{2}) }}$ where $\braket{ G_{1} , G_{2} }$ is the subgroup generated by $G_{1},G_{2}$.
> 3. if $K_{1}K_{2}=L$ and $K_{1}\cap K_{2}=K$ and $K_{1}:K$ and $K_{2}:K$ are both Galois, then:$$\text{Gal}(L:K)\cong G_{1}\times G_{2}$$

> [!proof]+
> We have:
> 1. As $\sigma\in \text{Gal}(L:K_{1})\cap \text{Gal}(L:K_{2})$ fix both $K_{1}$ and $K_{2}$, $\sigma|_{K_{1}K_{2}}=\text{id}_{K_{1}K_{2}}$. Hence, $K_{1}K_{2}\subseteq L^{\text{Gal}(L:K_{1})\cap \text{Gal}(L:K_{2})}$.
>    
>    Conversely, we have $\text{Gal}(L:K_{1}K_{2})\leq \text{Gal}(L:K_{i})$ and therefore,$$\text{Gal}(L:K_{1}K_{2})\leq \text{Gal}(L:K_{1})\cap\text{Gal}(L:K_{2})$$From Galois correspondence, $L^{\text{Gal}(L:K_{1})\cap \text{Gal}(L:K_{2})}\subseteq K_{1}K_{2}$.
> 2. As $k\in K_{1}\cap K_{2}$ is stays trivial by both $\text{Gal}(L:K_{1})$ and $\text{Gal}(L:K_{2})$, it still does so in th
---
##### Examples
> [!h] Example 1
> Let $f(x):=(x^2+1)(x^{2}-5)\in \mathbb{Q}[X]$. Then, 
> 1. $L:=\mathbb{Q}(i,\sqrt{ 5 })$ is the splitting field and $f$ is separable, i.e. $L:\mathbb{Q}$ is Galois with degree 4.
> 2. $\text{Gal}(L:\mathbb{Q})\cong \mathbb{Z}_{2}\times \mathbb{Z}_{2}$
---
> [!h] Example 2
> Let $f(x):=x^3-2\in \mathbb{Q}[X]$. Then, 
> 1. $L:=\mathbb{Q}(\sqrt[3]{2  },\rho)$ for $\rho=\exp(2\pi i /3)$ is the splitting field of $f$. Then, $L:\mathbb{Q}$ is Galois.
> 2. $[L:\mathbb{Q}]=6$ as $[\mathbb{Q}(\sqrt[3]{2  }):\mathbb{Q}]=3$ and $[\mathbb{Q}(\rho):\mathbb{Q}]=2$.
> 3. Therefore, $\text{Gal}(L:\mathbb{Q})\cong S_{3}$.
---
