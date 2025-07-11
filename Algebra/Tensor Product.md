#Definition #Algebra 

> [!definition]
> Let $M,N,P$ be $R$-[[Module|modules]]. 
> 1. A map $\alpha:M\times N\to P$ is called ***bilinear*** if $\alpha(m,\cdot):N\to P$ and $\alpha(\cdot,n):M\to P$ are $R$-linear for all $m\in M,n\in N$.
> 2. A ***tensor product of $M$ and $N$ over $R$*** is an $R$-module $M\otimes_{R} N$ together with a bilinear map $\tau:M\times N\to M\otimes N$ s.t. 
> 	1. **universal property**: for every bilinear map $\alpha:M\times N\to P$, there exists a unique linear map $\varphi:M\otimes N\to P$ s.t. $\alpha=\varphi \circ \tau$.
> 
> The elements in $M\otimes N$ are called ***tensors*** and for $(m,n)\in M\times N$, $m\otimes n:= \tau(m,n)$. 

^c31781

- **Remark**: By the definition, we have that $\text{Bilinear}(M\times N, P)\cong \text{Hom}(M\otimes N,P)$, i.e. they are bijective. ^267a80
- **Related definition**: Tensors in $M\otimes N$ of the form $m\otimes n$ are called ***pure/monomial***. Any tensor can be written as a linear combination of pure tensors.  ^3e23bf

---
##### Properties
> [!lemma] Theorem 1 (Uniqueness and Existence of Tensor Products)
> Let $M,N$ be $R$-modules. Then,
> 1. **Uniqueness**: the tensor product is unique up to isomorphism, i.e. if $(M\otimes N, \tau)$ and $(M\otimes' N,\tau')$ are two tensor products of $M,N$, then there is a unique $R$-isomorphism $\varphi:M\otimes N\to M\otimes'N$ s.t. $\tau'=\varphi\circ \tau$.
> 2.  **Existence**: there exists a tensor product $M\otimes N$.

^5fb0e9

> [!proof]-
> We have that:
> 1. As $\tau':M\times N\to M\otimes'N$ is a bilinear map, by the universal property, there exists a unique linear map $\varphi:M\otimes N\to M\otimes'N$ s.t. $\tau'=\varphi \circ \tau$. The same way we get a unique linear map $\psi:M\otimes' N\to M\otimes N$ with $\tau=\psi \circ \tau'$.
>    
>    By applying the universal property again on $\tau$, we have a unique linear map $\alpha:M\otimes N\to M\otimes N$ s.t. $\tau= \alpha \circ \tau$. As we have that: $$\tau = \psi \circ  \varphi \circ  \tau, \quad \tau=\text{id} \circ  \tau$$By uniqueness, $\alpha=\text{id}=\psi \circ \varphi$ and similarly $\varphi \circ \psi=\text{id}$. Hence, $\varphi$ is an isomorphism. 
> 2. Let $F$ be the $R$-module of all finite formal linear combinations of $M\times N$, i.e. $$F:=\left\{  \sum_{i=1}^{n}a_{i}(m_{i},n_{i}) :n\in \mathbb{N}, a_{i}\in R, (m_{i},n_{i})\in M\times N  \right\}$$Now, let $G$ be a submodule generated by: 
> 	1. $(m_{1}+m_{2},n)-(m_{1},n)-(m_{2},n)$
> 	2. $(m,n_{1}+n_{2})-(m,n_{1})-(m,n_{2})$
> 	3. $(am,n)-a(m,n)$
> 	4. $(m,an)-a(m,n)$
> 	
> 	for all $m,m_{1},m_{2}\in M,n,n_{1},n_{2}\in N,a\in R$. Now, set $M\otimes N:= F /G$. Then, the map: $$\tau:M\times N\to M\otimes N,\quad (m,n)\mapsto \overline{(m,n)}$$ is a bilinear map. We claim that $M\otimes N$ with $\tau$ is a tensor product of $M,N$ over $R$. Let $\alpha:M\times N\to P$ be a $R$-bilinear map. Then, define $\varphi:M\otimes N\to P$ by setting $\varphi(\overline{(m,n)}):=\alpha(m,n)$ and extending it by linearity. 
> 	
> 	Since $\alpha$ is bilinear, $\varphi$ is well-defined and $\alpha=\varphi \circ \tau$. It is also clear that this is the unique choice that makes this possible. This proves the claim.

^96a6da

---
> [!lemma] Lemma 2 (Properties of Tensors)
> For any $R$-modules $M,N,P$, 
> 1. $M\otimes N\cong N\otimes M$.
> 2. $M\otimes R\cong M$.
> 3. $(\bigoplus_{\alpha\in \mathcal{A}}M_{\alpha})\otimes N\cong \bigoplus_{\alpha\in \mathcal{A}}(M_{\alpha}\otimes N)$.
> 4. $M\otimes N\otimes P\cong (M\otimes N)\otimes P\cong M\otimes(N\otimes P)$.
> 5. if $M,N$ are [[Basis|free]] with basis $\{ m_{i} \}_{i}$ and $\{ n_{j} \}_{j}$ respectively, then $M\otimes N$ is free with basis $\{ m_{i}\otimes n_{j} \}_{i,j}$.

^bd93e0

> [!proof]-
> We have that:
> 1. $(m,n)\mapsto n\otimes m$ is bilinear and by the universal property, there exists a unique linear map: $$\varphi:M\otimes N\to N\otimes M,\quad \varphi(m\otimes n)=n\otimes m,\quad \forall m\in M,n\in N$$Similarly, we get $\psi:N\otimes M\to M\otimes N$ with $\psi(n\otimes m)=m\otimes n$. Then, $(\psi \circ\varphi)(m\otimes n)=m\otimes n$ for all $m\in M$ and $n\in N$. As $\{ m\otimes n \}_{m,n}$ generate $M\otimes N$, we have that $\psi \circ \varphi=\text{id}$. Similar for the converse. Hence, $\varphi$ is an isomorphism.
> 2. $(m,a)\mapsto am$ is bilinear and by the universal property, there exists a unique linear map: $$\varphi:M\otimes R\to M,\quad \varphi(m\otimes a)=am,\quad \forall m\in M,a\in R$$Further, there is a linear map $\psi:M\to M\otimes R,m\mapsto m\otimes 1$. Then, $$(\psi \circ  \varphi)(m\otimes  a)=\psi(am)=am\otimes 1=a(m\otimes 1)=m\otimes a$$and $(\varphi \circ \psi)(m)=\varphi(m\otimes 1)=m$. Hence, $\varphi$ is an isomorphism.
> 3. $((m_{\alpha})_{\alpha},n)\to(m_{\alpha}\otimes n)_{\alpha}$ induces a bilinear map. Hence, there exists a unique linear: $$\varphi:(\bigoplus_{\alpha\in \mathcal{A}}M_{\alpha})\otimes N\to\bigoplus_{\alpha\in \mathcal{A}}(M_{\alpha}\otimes N), \quad\varphi((m_{\alpha})_{\alpha}\otimes n)=(m_{\alpha}\otimes n)_{\alpha}$$Similarly, we get $M_{\alpha}\otimes N\to(\bigoplus_{\alpha}M_{\alpha})\otimes N,m_{\alpha}\otimes n\mapsto (\dots,m_{\alpha},\dots)\otimes n$.  Hence, $$\psi:\bigoplus _{\alpha}(M_{\alpha}\otimes N)\to( \bigoplus _{\alpha}M_{\alpha})\otimes N,\quad \psi((m_{\alpha}\otimes  n_{\alpha})_{\alpha})=\sum_{\alpha}^{}(\dots,m_{\alpha},\dots)\otimes n_{\alpha}$$One easily sees that $\psi$ and $\varphi$ are inverses on the pure tensors and hence on the whole space.
> 4. Let the LHS be a tensor product defined from the trilinear map, i.e. for any trilinear $\alpha:M\times N\times P\to Q$, there exists a unique linear map $\varphi:M\otimes N\otimes P \to Q$ s.t. $\alpha(m,n,p)=\varphi (m\otimes n\otimes p)$. 
>    
>    Then, notice that $(m,n,p)\mapsto (m\otimes n) \otimes p$ is trilinear and by the universal property, we have: $$\varphi:M\otimes N\otimes P\to(M\otimes N)\otimes P,\quad \varphi(m\otimes n\otimes p)=(m\otimes  n)\otimes  p$$Conversely, let $\alpha:(M\otimes N)\times P\to M\otimes N\otimes P$ defined on $\alpha(m\otimes n, p):=m\otimes n\otimes p$ then extended on the whole space. Then, $\alpha$ remains bilinear and there exists: $$\psi:(M\otimes N)\otimes P\to M\otimes N\otimes P,\quad \psi((m\otimes n)\otimes  p)=m\otimes n\otimes p$$Hence, $\varphi,\psi$ are inverses on pure tensors and hence on the whole space.
>    
>    The proof for $M\otimes(N\otimes P)$ is analogous and this proves the associativity.
> 5. We show that $\{ m_{i}\otimes n_{j} \}_{i,j}$ is linearly independent. Let $\beta_{kl}:M\times N\to R$ be a bilinear map given by: $$\beta_{kl}(m_{i},n_{j}):=\begin{cases}1&i=k,j=l\\0&\text{otherwise}\end{cases}$$Then, there exists $\varphi_{kl}:M\otimes N\to R$ with $\varphi_{kl}(m_{i}\otimes n_{j})=\mathbb{1}_{i=k,j=l}$. Now, let $\sum_{i,j}^{}a_{ij}(m_{i}\otimes n_{j}) =0$. We get that:$$0=\varphi_{kl}\left( \sum_{i,j}^{}a_{ij}(m_{i}\otimes n_{j}) \right)=a_{kl}$$and it is linearly independent.
>    
>    Now, we get that: $$m\otimes n=\left( \sum_{i}^{}a_{i}m_{i} \right)\otimes \left( \sum_{j}^{}b_{j}n_{j} \right)=\sum_{i}\sum_{j}^{}a_{i}b_{j}(m_{i}\otimes n_{j})$$

	
^6fa18d

- **Remark**: If $M,N$ are free of rank $m,n$ respectively, $$M\otimes N\cong R^m\otimes (R\oplus \dots \oplus R)\cong (R^m \otimes R)\oplus \dots \oplus (R^m \otimes R)\cong R^m\oplus \dots \oplus R^m\cong R^{mn}$$ ^552c4a
---
> [!lemma] Proposition 3 (Tensor Products are Right Exact)
> Let $R$ be a ring and $M,N,P$ be $R$-modules. 
> 1.  $\text{Hom}(M,\text{Hom}(N,P))\cong \text{Hom}(M\otimes N,P)$
> 2. If $M\xrightarrow{\varphi}N\xrightarrow{\psi}P\to 0$ is an [[exact sequence]], then for any $R$-module $A$:$$M\otimes A\xrightarrow{\varphi \otimes  \text{id}}N\otimes A\xrightarrow{\psi \otimes  \text{id}}P\otimes A\to 0$$is an exact sequence as well.
> 3. If $0\to M \to N\to P \to 0$ is exact, then for any $R$-module $A$:$$0\to M\otimes A \to N\otimes A \to P \otimes A \to 0$$is exact if:
> 	1. $0\to M\to N\to P \to 0$ is [[Split Exact Sequence|split]].
> 	2. $A$ is a free $R$-module.

^47b82c

> [!proof]-
> We have that:
> 1. We define a homomorphism: $$\Psi:\text{Hom}(M,\text{Hom}(N,P))\to \text{Hom}(M\otimes N,P), \quad \alpha\mapsto (m\otimes n\mapsto \alpha(m)(n))$$More precisely, for $M\times N\to P,(m,n)\mapsto \alpha(m)n$ is a bilinear map and by the universal property, $\Psi(\alpha)$ is well-defined. Hence, this is an isomorphism. 
> 2. As [[Module|Hom(.,N) is left exact]], $$0\to \text{Hom}(P,\text{Hom}(A,B))\xrightarrow{\psi ^{*}}\text{Hom}(N,\text{Hom}(A,B))\to\text{Hom}(M,\text{Hom}(A,B))$$ is left exact for all $R$-modules $A,B$ with: $\psi ^{*}(f)=f \circ  \psi$. From 1, this is the same as: $$0\to \text{Hom}(P\otimes A,B)\xrightarrow{\tilde{\psi}}\text{Hom}(N\otimes A,B)\to\text{Hom}(M\otimes A,B)$$where for $g:P\otimes A\to B$:$$\tilde{\psi}(g)(n\otimes a)=g(\psi(n)\otimes a)=g(\psi \otimes  \text{id}(n\otimes  a))$$
>    
>    We send it back so we get: $$M\otimes A\xrightarrow{\varphi \otimes \text{id}} N\otimes A \xrightarrow{\psi \otimes \text{id}} P\otimes A\to 0$$as an exact sequence.
> 3. We just have to show that if $\varphi:M\to N$ is injective, $\varphi \otimes \text{id}$ is injective. Assume that the sequence is split. Then, there exists $j:N\to M$ s.t. $j \circ\varphi= \text{id}_{M}$. 
>    
>    Let: $\varphi \otimes \text{id}\left( \sum_{i}^{}m_{i}\otimes a_{i} \right)=0$. Then, $\sum_{i}^{}\varphi(m_{i})\otimes a_{i} = 0$ and $$\sum_{i}^{}m_{i}\otimes  a_{i}=(j\otimes \text{id})\left( \sum_{i}^{}\varphi(m_{i})\otimes  a_{i} \right)=0$$Hence, $\varphi \otimes \text{id}$ is injective.
>    
>    If $A$ is finitely generated free with basis $(b_{i})_{i\in I}$. Then, if we have that: $$0=\varphi \otimes  \text{id}\left( \sum_{i}^{}m_{i}\otimes a_{i} \right)=\sum_{i}^{}\varphi(m_{i})\otimes  a_{i}$$However, note that the following map is a bijection.$$M\otimes  A\to M^I,\quad \sum_{i\in I}^{}m_{i}\otimes  a_{i}\mapsto (m_{i})_{i\in I} $$Hence, $\varphi(m_{i})=0$ for all $i\in I$ and by injectivity of $\varphi$, we have that $m_{i}=0$ for all $i\in I$.

^2db9e9

---
> [!lemma] Proposition 4 (Cokernel of Tensor Product)
> Let $R$ be a ring and $U,V,M$ be $R$-modules. 
> 1. for a homomorphism $f:U\to V$, we have that: $$\text{coker}(f\otimes  \text{id}_{M})\cong \text{coker}(f)\otimes  M$$

^df073f

> [!proof]-
> Notice that:
> 1. We have that: $$U\overset{ f }{ \to } V \overset{ q }{ \to } \text{coker}(f)\to 0$$is an exact sequence where $q$ is standard projection. Therefore, by right exactness, $$U\otimes  M \overset{ f\otimes  \text{id} }{ \to } V\otimes  M \overset{ q\otimes  \text{id} }{ \to } \text{coker}(f)\otimes M\to 0$$is also an exact sequence. Then, $$\begin{CD}U\otimes M @> f\otimes  \text{id}>> V \otimes M @>q\otimes  \text{id}>> \text{coker}(f)\otimes  M @>>> 0@>>> 0\\@V\text{id}VV@V\text{id}VV@V\varphi VV @VVV@VVV\\U\otimes M @>>f\otimes  \text{id}> V \otimes M @>>q'> \text{coker}(f\otimes  \text{id})@>>> 0@>>> 0\end{CD}$$commutes if we define $\varphi([v]\otimes m)=[v\otimes m]$. Therefore, by 5-lemma it is isomorphic.

^3c1324

---
##### Examples
> [!h] Example 1
> Let $I,J\unlhd R$ be [[Coprime Ideal|coprime]]. Then,
> 1. $R / I\otimes R / J=0$

^c4c085

> [!proof]-
> We have: 
> 1. Let $a\in I,b\in J$ s.t. $a+b=1$. Let $r,s\in R$. For $\overline{r}\otimes \overline{s}\in R / I\otimes R / J$, $$\overline{r} \otimes \overline{s}=(a+b)(\overline{r} \otimes \overline{s})=\overline{ar}\otimes  \overline{s}+\overline{r} \otimes  \overline{bs}=0$$hence, $R / I\otimes R / J=0$.

^ffbf53

---
> [!h] Example 2
> We have that:
> 1. $\mathbb{Q} / \mathbb{Z} \otimes_{\mathbb{Z}}\mathbb{Q} / \mathbb{Z}=0$.
> 2. $\mathbb{Q} \otimes_{\mathbb{Z}}\mathbb{Q} \cong \mathbb{Q}$
> 3. $\mathbb{C} \otimes_{\mathbb{R}}\mathbb{C}\cong \mathbb{C}\oplus \mathbb{C}$
> 4. $\mathbb{Q}[x]\otimes_{\mathbb{Q}}\mathbb{C}\cong \mathbb{C}[x]$

^3e32bf

> [!proof]-
> We have:
> 1. Consider $\frac{p}{q}\otimes \frac{m}{n}$. We have: $$\frac{p}{q}\otimes \frac{m}{n}=\frac{np}{nq}\otimes \frac{m}{n}=n\frac{p}{nq}\otimes \frac{m}{n}=\frac{p}{q}\otimes m=\frac{p}{q}\otimes 0=0$$
> 2. We claim that: $$\psi:\mathbb{Q}\otimes _{\mathbb{Z}} \mathbb{Q}\to \mathbb{Q},\quad \alpha \otimes  \beta\mapsto \alpha\beta$$is an isomorphism. We have that: $$\frac{a}{b}\otimes  \frac{c}{d}=\frac{ac}{bd}\otimes 1$$Similarly as above. This proves the statement.
> 3. We have that: $$\mathbb{C}\otimes _{\mathbb{R}}\mathbb{C}\cong \mathbb{C}\otimes _{\mathbb{R}} (\mathbb{R}\oplus \mathbb{R})=(\mathbb{C}\otimes _{\mathbb{R}}\mathbb{R})\oplus (\mathbb{C}\otimes _{\mathbb{R}}\mathbb{R})=\mathbb{C}\oplus \mathbb{C}$$
> 4. We have that: $$\varphi:\mathbb{Q}[x]\otimes _{\mathbb{Q}} \mathbb{C}\to \mathbb{C}[x],\quad f\otimes  \alpha\to \alpha f$$is isomorphic with its inverse given by: $\psi(\alpha x^i)\mapsto x^i\otimes \alpha$.

^79a8a1

---
> [!h] Example 3 (Vector Spaces and Duals)
> Let $V,W$ be $K$-vector spaces. Let $V^{*}:=\text{Hom}_{K}(V,K)$ be the dual space of $V$. Then, 
> 1. there exist following linear maps 
> 	1. $\Phi:V^{*}\otimes W\to \text{Hom}(V,W)$ s.t. $\Phi(\varphi \otimes w)(v)=\varphi(v)w$
> 	2. $\Psi:V^{*}\otimes V^{*}\to \text{Bilinear}(V,V)$ s.t. $\Psi(\varphi \otimes \psi)(v,v')=\varphi(v)\psi(v')$.
> 	3. $T:V^{*}\otimes V\to K$ s.t. $T(\varphi\otimes v)=\varphi(v)$.
> 	
>2. $\Phi,\Psi$ are injective.
>3. $\Phi,\Psi$ are isomorphisms if $V,W$ are finite dimensional.

^45d1be

> [!proof]-
> We have that:
> 1. Consider: $$V^{*}\times W\to \text{Hom}(V,W),\quad (\varphi,w)\mapsto (v\mapsto \varphi(v)w)$$ is bilinear and by universal property the statement holds. Similarly, $$V^{*}\times V^{*}\to \text{Bilinear}(V,V),\quad (\varphi,\psi)\mapsto ((v,v')\mapsto \varphi(v)\psi(v'))$$$$V^{*}\times V \to K,\quad (\varphi,v)\mapsto \varphi(v)$$are bilinear and by universal property the statement holds. 
> 2. Let $\Phi(\varphi \otimes w)=0$. Then, $\varphi(v)w=0$ for all $v$, which holds if either $\varphi=0$ or $w=0$, i.e. $\varphi \otimes w= 0$. As $V^{*}\otimes W$ is generated by the pure tensors of the basis of $V^{*}$ and $W$, $\Phi$ is injective.
>    
>    Let $\Psi(\varphi \otimes \psi) = 0$. Then, $\varphi(v)\psi(v')=0$ for all $v,v'\in V$, which holds if either $\varphi=0$ or $\psi=0$, i.e. $\varphi \otimes \psi=0$. Similarly, $\Psi$ is injective.
> 3. $V,W$ are finite dimensional, hence injective implies bijective.

^bba294

---
> [!h] Example 4 (Tensor Product of Homomorphisms)
> Let $\varphi:M\to N$ and $\varphi':M'\to N'$ be homomorphisms of $R$-modules. Then, 
> 1. $M\times M'\to N\otimes N', (m,m')\mapsto \varphi(m)\otimes\varphi'(m')$ is a bilinear map and:
> 2. $\varphi \otimes\varphi':M\otimes M'\to N\otimes N'$ is well-defined s.t. $\varphi \otimes\varphi'(m\otimes m')=\varphi(m)\otimes\varphi'(m')$. 

^88632b

---
> [!h] Example 1
> Let $V$ be a finite-dimensional vector space. Then, $$\begin{array}{cccc} {J:}&{V^{*}\otimes W}&\to&{\text{Hom}(V,W)}\\&{f\otimes w} &\mapsto & {v\mapsto f(v)w} \end{array}{}$$is an isomorphism.

> [!proof]-
> First we show that $J(f\otimes w)$ is well-defined. $$J(f\otimes w)(v_{1}+v_{2})=f(v_{1})w+f(v_{2})w=J(f\otimes w)v_{1}+J(f\otimes w)v_{2}$$$$J(f\otimes w)(av)=af(v)w=aJ(f\otimes w)v$$
> If $J(f\otimes w)=0$, then either $f=0$ or $w=0$. Therefore, $\text{ker }J=(0)$. Further, for $A\in \text{Hom}(V,W)$, let $f_{i}$ be the basis of $V^{*}$. Then, consider $\sum_{i}^{}f_{i}\otimes A(v_{i})$. $$J\left( \sum_{i}^{}f_{i}\otimes A(v_{i}) \right)(v)=\sum_{i}^{}f_{i}(v)A(v_{i})=A\left( \sum_{i}^{}f_{i}(v)v_{i} \right)=A(v) $$
---
> [!h] Example 2 (Symmetric and Exterior Power)
> Let $V$ be a $K$-vector space. We define: $$S^nV:=V^{\otimes n} / \braket{ T-s(T) :T\in V^{\otimes }n ,s\in \text{Trans}} $$i.e. where $s$ is a transposition. If $\{ v_{i} \}_{i}$ is a basis of $V$, then $\{ v_{i_{1}}\otimes\dots \otimes v_{i_{n}}:i_{1}\leq\dots\leq i_{n} \}$ is the basis of $S^nV$ with dimension ${m+n-1\choose n}$ for $\text{dim} V=m$.
> 
> Similarly, for: $$\land^nV:=V^{\otimes n} / \braket{ s(T)=T  } $$we have $\{ v_{i_{1}}\otimes\dots \otimes v_{i_{n}}:i_{1}<\dots<i_{n} \}$ as a basis with dimension $m \choose n$.
---
