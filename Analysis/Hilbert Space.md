#Definition #FunctionalAnalysis 
> [!definition]
> An [[Inner Product Space|inner product space]] $\mathcal{H}$ is a ***Hilbert space***, if the induced [[Analysis/Normed Space|normed space]] is [[Banach Space|Banach]].
- **Related definition**: an ***orthonormal system*** is $\{ e_{n} \}_{n}\subseteq \mathcal{H}$ s.t. $\braket{ e_{i} , e_{j} } =\delta_{ij}$ for all $i,j\in \mathbb{N}$.
---
##### Properties
> [!lemma] Theorem 1 (Bessel's Inequality)
> Let $\mathcal{H}$ be a [[Separable Space|separable]] Hilbert space with $\{ e_{k} \}$ as an orthonormal system. Then, for any $x\in \mathcal{H}$: 
$$\sum_{k=0}^{\infty}\left| \braket{ x , e_{k} }  \right| ^{2}\leq\|x\|^2$$

> [!proof]-
> Let $x\in \mathcal{H}$ and $n\geq 1$ and define $S_{n}(x):=\sum_{k=0}^{n}\braket{ x , e_{k} }e_{k}$. Then, from Pythagoras, $$\left\| S_{n}(x) \right\|^{2}=\sum_{k=0}^{n} \left| \braket{ x , e_{k} }  \right| ^{2}$$and $$\braket{ S_{n}(x) , x } =\left\langle \sum_{k=0}^{n}\braket{ x , e_{k} } e_{k},x\right\rangle=\sum_{k=0}^{n}\braket{ x , e_{k} } \braket{ e_{k} , x } =\sum_{k=0}^{n}\left| \braket{ x , e_{k} }  \right| ^{2}$$Therefore, $$0\leq \left\| S_{n}(x)-x \right\| ^{2}=\left\| S_{n}(x) \right\|^{2}+\|x\|^{2}-2\text{Re}\braket{ S_{n}(x) , x }  =\|x\|^{2}-\sum_{k=0}^{n}\left| \braket{ x , e_{k} }  \right| ^{2}$$This proves the statement.
---
> [!lemma] Theorem 2 (Parseval's Identity)
> Let $\mathcal{H}$ be a [[Separable Space|separable]] Hilbert space with $\{ e_{k} \}$ as an orthonormal system. Then, for any $x\in \mathcal{H}$:
> 1. $\sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k}$ converges in $\mathcal{H}$.
> 2. $\left\| \sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k} \right\|^{2}=\sum_{k=0}^{\infty}\left| \braket{ x , e_{k} } \right|^{2}\leq \|x\|^{2}$
> 3. $x-\sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k} \ {\bot}\ \overline{\text{Span} \{ e_{k} \}_{k}  }$
> 4. $x=\sum_{k=0}^{\infty}\braket{ x , e_{k} }e_{k}$ if and only if $$\sum_{k=0}^{\infty}\left| \braket{ x , e_{k} }  \right|^{2}=\|x\|^{2} $$

> [!proof]-
> For $S_{n}(x):=\sum_{k=0}^{n}\braket{ x , e_{k} }e_{k}$, we show that $(S_{n}(x))_{n}$ is Cauchy. We have; $$\left\| S_{m}(x)-S_{n}(x) \right\|^{2}=\sum_{k=n+1}^{m}\left| \braket{ x , e_{k} }  \right| ^{2} $$which is part of a convergent series by Bessel's inequality. Therefore, $(S_{n}(x))_{n}$ is Cauchy and this shows 1 and 2.
> 
> For $n,k$ s.t. $n\geq k$: $$\braket{ S_{n}(x) , e_{k} } =\sum_{j=0}^{n}\braket{ x , e_{j} } \delta_{jk}=\braket{ x , e_{k} } $$Therefore, $\braket{ x-S_{n}(x) , e_{k} } =\braket{ x , e_{k} } -\braket{ x , e_{k} } =0$ and we have the result by $n\to \infty$.
> 
> Lastly, we have: $$\left\| x-S_{n}(x) \right\| =\|x\|^{2}-\sum_{k=0}^{n}\left| \braket{ x , e_{k} }  \right| ^{2}$$This proves the statement.
---
> [!lemma] Theorem 3 (Existence of Projections)
> For a Hilbert space $\mathcal{H}$ and a closed convex subset $C\subseteq \mathcal{H}$. Then, for all $v\in \mathcal{H}$, 
> 1. there exists a unique $\rho_{C}(v)\in C$ s.t.
> $$\|v-\rho_{C}(v)\|=d(v,C)$$
> 2. $\rho_{C}(v)$ is characterized by $\text{Re}\braket{ v-\rho_{C}(v), w-\rho_{C}(w) }\leq 0$ for all $w\in C$.
> 3. if $C$ is a vector subspace and $w\in \mathcal{H}$, $w=\rho_{C}(v)$ if and only if $v-w\  \bot\ C$.

> [!proof]-
> By translating the situation by $-v$, we may assume that $v=0$. Then, let:
> - $d:=d(0,C)$ and
> - $(v_{n})_{n\geq 1}\subseteq C$ s.t. $d^{2} \leq \left\| v_{n} \right\|^{2}< d^{2}+\frac{1}{n}$.
>   
> Then, we have: $$\left\| \frac{v_{n}+v_{m}}{2} \right\|^{2}+\left\| \frac{v_{n}-v_{m}}{2} \right\|^{2}=\frac{1}{2} (\| v_{n} \| ^{2}+\|  v_{m} \| ^{2})  <d^{2}+\frac{1}{2} \left( \frac{1}{n}+\frac{1}{m} \right)$$ Then, as $\frac{v_{n}+v_{m}}{2}\in C$, we have $\left\| \frac{v_{n}+v_{m}}{2} \right\|^{2}\ge d^{2}$ and $$\left\| \frac{v_{n}-v_{m}}{2} \right\|^{2}<\frac{1}{2} \left( \frac{1}{n}+\frac{1}{m} \right)$$ which implies that $(v_{n})_{n}$ is a Cauchy sequence. Since $\mathcal{H}$ is a Hilbert space, $x:=\lim_{ n \to \infty }v_{n}\in C$ exists and clearly, $d(0,C)=\|x\|$. 
> 
> Uniqueness follows directly from the strict convexity property.
> 
> Take any $w\in C$ and $\lambda\in[0,1]$. Then,$$F_{w}(\lambda):=\left\| v-((1-\lambda)\rho_{C}(v)+\lambda w) \right\|^{2}=\left\| v-\rho_{C}(v) \right\| ^{2}+\lambda^{2}\left\| w-\rho_{C}(v)\right\|^{2}-2\lambda \text{Re}\braket{ v-\rho_{C}(v) , w-\rho_{C}(v) }   $$with $F'_{w}(\lambda)=2\lambda \left\| w-\rho_{C}(v) \right\|^{2}-2\text{Re}\braket{ v-\rho_{C}(v) , w-\rho_{C}(v) }$. As $F_{w}$ takes its minimum at $\lambda=0$, we have that $\text{Re}\braket{ v-\rho_{C}(v) , w-\rho_{C}(v) }\leq 0$. 
> 
> Conversely, if it holds, we have: $$F_{w}(\lambda)\geq\|v-\rho_{C}(v)\|^{2}+\lambda^{2}\|w-\rho_{C}(v)\|^{2}\geq\|v-\rho_{C}(v)\|^{2}$$By taking $\lambda=1$, $\|v-w\|^{2}\geq\|v-\rho_{C}(v)\|^{2}$.
- **Corollary**: For a proper closed subspace $Y\subseteq \mathcal{H}$, there always exists $0\neq x_{0}\in Y^{\bot}$. (Take $x_{0}:=z_{0}-\rho_{Y}(z_{0})$ where $z_{0}\notin Y$) 
---
> [!lemma] Proposition 4 (Orthogonal Decomposition)
> Let $V \subseteq \mathcal{H}$ be a closed subspace of a Hilbert space.  Then, $\mathcal{H}$ is the orthogonal [[direct sum]] of $V$ and $V^{\bot}$, i.e.: $$\begin{array}{cccc} {T:}&{\mathcal{H}}&\to&{V\oplus V^{\bot}}\\&{v} &\mapsto & {(\rho_{V}(v),\rho_{V^{\bot}}(v))} \end{array}{}$$is an isometry of Hilbert spaces with $\|v\|^{2}=\|\rho_{V}(v)\|^{2}+\|\rho_{V^{\bot}}(v)\|^{2}$.
> 

>[!proof]-
> Firstly, $\rho_{V}(v)\in V$ exists per Theorem 3. Then, for any $z\in V^{\bot}$:$$\braket{ v-(v-\rho_{V}(v)) , z } =\braket{ \rho_{V}(v) , z } =0$$Therefore, by Theorem 3, $v-\rho_{V}(v)=\rho_{V^{\bot}}(v)$. 
>
>Then, it is clear that $T$ is surjective. Furthermore, to show the injectivity: $$\begin{align}\braket{ Tu , Tv }&=\braket{ \rho_{V}(u) , \rho_{V}(v) } +\braket{u- \rho_{V}(u) , v-\rho_{V}(v) }\\&=\braket{ \rho_{V}(u) , \rho_{V}(v) } +\braket{ u , v } -\braket{ u , \rho_{V}(v) }-\underbrace{ \braket{ \rho_{V}(u) , v-\rho_{V}(v) } }_{ =0 }\\&=\underbrace{ \braket{ \rho _{V}(u)-u ,\rho_{V}(v)   } }_{ =0 }+\braket{ u , v } \\&=\braket{ u , v }  \end{align} $$Therefore, $T$ is a bijective isometry.
>
>---
>Since $V$ is closed and convex, we have the nearest point projection: $$P_{V}:\mathcal{H} \to V$$from Theorem 1.  Then, for all $u\in V$, the polynomial $$\begin{array}{cccc} {}&{\mathbb{R}}&\to&{\mathbb{R}}\\&{t} &\mapsto & {\left\| v-(P_{V}(v)-tu) \right\| ^{2}} \end{array}{}$$attains a minimum at $t=0$. Then, then in the derivative, we should have: $$\text{Re}\braket{ v-P_{V}(v) , u } =0$$for all $u\in V$. Now, for $u\in V$, let $\alpha\in \mathbb{C}$ s.t. $$\left| \braket{ v-P_{V}(v) , u }  \right| =\alpha \cdot \braket{ v-P_{V}(v) , u }=\text{Re} \braket{ v-P_{V} (v), \overline{\alpha}u }=0  $$Therefore, $v-P_{V}(v)\in V^{\bot}$. It follows that: $$\|v\|^2=\left\| P_{V}(v)+(v-P_{V}(v)) \right\|^{2}=\left\| P_{V}(v) \right\| ^2+\left\| v-P_{V}(v) \right\| ^2$$
---
> [!lemma] Theorem 5 (Riesz Representation Theorem)
> For a Hilbert space $\mathcal{H}$, the Riesz map, defined as: $$\begin{array}{cccc} {i:}&{\mathcal{H}}&\to&{\mathcal{H}^{*}}\\&{u} &\mapsto & {\braket{ \cdot  , u } } \end{array}{}$$is an anti-linear, norm-preserving bijection. Therefore, $\mathcal{H}^{*}\cong \mathcal{H}$.

> [!proof]-
> Anti-linearity is clear. For the norm, by [[Inner Product Space|Cauchy-Schwarz]], we have: $$\left\| i(u) \right\| =\sup_{\|v\|\leq 1}\left| \braket{ v,u }  \right| \leq \|u\| $$Since, $i(u)\left( \frac{u}{\|u\|} \right)=\|u\|$, we have $\|i(u)\|=\|u\|$, i.e. $i$ is norm-preserving.
> 
> Now, let $\lambda\in \mathcal{H}^{*}$ s.t. $\lambda\neq 0$. Then, $\text{ker}\lambda$ is a closed, co-dimension 1 subspace of $\mathcal{H}$. By Proposition 4, we have: $$\text{ker}\lambda \oplus (\text{ker}\lambda)^{\bot}=\mathcal{H}$$Let $(\text{ker}\lambda)^{\bot}=\mathbb{K}\cdot e$ for some $\|e\|=1$. Further, let $u:=\overline{\lambda(e)}\cdot e$. Then, for any $v\in \mathcal{H}$, we have $v=v_{1} +r \cdot e$. for some $r\in \mathbb{K}$, $v_{1}\in \text{ker}\lambda$ and:$$i(u)(v)=\braket{ v , u } =\braket{ re ,  \overline{\lambda(e)}e}=r\lambda(e)=\lambda(re)=\lambda(v) $$which shows that $i(u)=\lambda$.
---
> [!lemma] Proposition 6
> Let $\mathcal{H}$ be a [[Separable Space|separable]] $\infty$-dimensional Hilbert space and $\{ e_{n} \}_{n\geq 1}$ an orthonormal basis. Then, $e_{n}\to 0$ weakly as $n\to \infty$.


> [!proof]-
> Recall that every $f\in \mathcal{H}^{*}$ is given by $f(v)=\braket{ v , x }$ for some $x\in \mathcal{H}$ from Riesz Representation theorem. Let $x=\sum_{n=1}^{\infty}\braket{ x , e_{n} }e_{n}$, with $\|x\|^{2}=\sum_{n=1}^{\infty}\left| \braket{ x , e_{n} } \right|^{2}$. Then, $$f(e_{n})=\braket{ e_{n} , x } $$Since $\|x\|^{2}=\sum_{n=1}^{\infty}|\braket{ e_{n} , x } |^{2}$, we have that $\lim_{ n \to \infty }\braket{ e_{n} , x } =0$. This shows that $f(e_{n})\to 0$. From [[Weak Topology|Lemma 2]], $e_{n}\to{0}$ in weak-topology.
- **Corollary**: $B_{\leq 1}^\mathcal{H}(0)$ is weakly closed, $S_{1}^\mathcal{H}(0)=\{ v\in \mathcal{H}:\|v\|=1 \}$ is not weakly closed.
---
> [!lemma] Lemma 2
> Let $\mathcal{H}$ be a Hilbert space and assume $\{ x_{n}: n\geq 1 \}$ is pairwise orthogonal. Then, the following are equivalent:
> 1. $\sum_{n=1}^{\infty}x_{n}$ converges.
> 2. $\sum_{n=1}^{\infty}\left\| x_{n} \right\|^{2}$ converges.
> 3. $\sum_{n=1}^{\infty}\braket{ x_{n} , y }$ converges for all $y\in \mathcal{H}$.

> [!proof]-
> 1 is equivalent to 2 by [[Hilbert Space|Pythagoras]]. (the partial sum is Cauchy in one iff it is in another).
> 1. (1=>3): We have; $$\left| \sum_{n=k}^{\ell}\braket{ x_{n} , y }  \right| =\left| \left\langle \sum_{n=k}^{\ell} x_{n},y  \right\rangle \right|\leq \left\| \sum_{n=k}^{\ell}x_{n} \right\| \left\| y \right\|  $$Therefore, 3 is Cauchy if 1 is Cauchy.
> 2. (3=>1): Define $\Lambda_{n}(y):=\sum_{k=1}^{n}\braket{ y ,x_{k}  }$ . Then, $\Lambda_{n}\in \mathcal{H}^{*}$. Then, for all $y\in \mathcal{H}$, $\lim_{ n \to \infty }\Lambda_{n}(y)$ exists and $$\sup_{n\geq 1}\left| \Lambda_{n}(y) \right| <+\infty,\quad \forall y\in \mathcal{H}$$Then, by [[Bounded Linear Map|Banach-Steinhaus]], $\sup_{n\geq 1}\left\| \Lambda_{n} \right\|<+\infty$. Then, $$\left\| \Lambda_{n} \right\| ^{2}=\sup_{\left\| y \right\| \leq 1}\left| \left\langle\sum_{k=1}^{n}x_{k},y\right\rangle \right| ^{2}\leq \left\| \sum_{k=1}^{n}x_{k} \right\| ^{2}=\sum_{k=1}^{n}\left\| x_{k} \right\| ^{2}$$Therefore, we get 1. 

---
##### Hilbert Space and Spectral Theorem
> [!lemma] Lemma 1
> Let $\mathcal{H}$ be a [[Separable Space|separable]] Hilbert space and $A\subseteq \mathcal{B}(\mathcal{H})$ is a commutative [[C*-Algebra|sub-$C^{*}$-algebra]] containing $\text{id}_{\mathcal{H}}$. Then, 
> 1. there exists $J\subseteq \mathbb{N}$ and $\{ v_{n}:n\in J \}\subseteq \mathcal{H} \backslash\{ 0 \}$ s.t. 
> 	1. $\overline{Av_{n}}\ \bot\  \overline{Av_{m}}$ for $n\neq m$.
> 	2. $\mathcal{H}=\widehat{\bigoplus}_{n\in J} \overline{Av_{n}}$ where $\widehat{\bigoplus}$ denotes the direct orthogonal sum.

> [!proof]-
> Consider $\mathcal{C}:=\{ F\subseteq \mathcal{H} \backslash \{ 0 \}:\forall v,w\in F,Av\ \bot\ Aw \}$. Then $\mathcal{C}\neq \varnothing$ and we will use the Zorn's lemma to find a maximal set. If $\mathcal{U}\subseteq \mathcal{C}$ is totally ordered, then $\bigcup_{F\in \mathcal{U}}^{}F\in \mathcal{C}$. Therefore, there exists a maximal element $J$. As $\mathcal{H}$ is separable, $J$ is countable. Then, one can see that the first condition holds for $J$.
> 
> Consider $\mathcal{L}:=\bigoplus_{v\in J}Av$. We want to show that $\overline{\mathcal{L}}=\mathcal{H}$. Assume otherwise. Then, $\mathcal{L}^{\bot}\neq(0)$. As $\mathcal{L}$ is $A$-invariant and $A$ is stable under $T\to T^{*}$, $\mathcal{L}^{\bot}$ is $A$-invariant.
> 
> Let $w\in \mathcal{L}^{\bot}\backslash\{ 0 \}$. Then, clearly $Aw\ {\bot}\ Av$ for all $v\in J$. This is a contradiction to the maximality of $J$.
> 
---
> [!lemma] Theorem 2
> Let $\mathcal{H}$ be a [[Separable Space|separable]] Hilbert space and $A\subseteq \mathcal{B}(\mathcal{H})$ is a commutative [[C*-Algebra|sub-$C^{*}$-algebra]] containing $\text{id}_{\mathcal{H}}$. Then, 
> 1. there exists a finite positive Borel regular measure $\mu$ on $\widehat{A}\times \mathbb{N}$ and
> 2. there exists a Hilbert space isomorphism $\Lambda:\mathcal{H}\to L^{2}(\widehat{A}\times \mathbb{N},\mu)$ s.t. for all $T\in A$ and $v\in \mathcal{H}$, $$\Lambda(Tv)(\chi,n)=\widehat{T}(\chi)\Lambda(v)(\chi,n)$$In other words, the following diagram commutes: $$\begin{CD}\mathcal{H} @>\Lambda>>L^2(\widehat{A}\times \mathbb{N},\mu)\\@VTVV&@VVM_{\widehat{T}}V\\\mathcal{H}@>\Lambda>>L^2(\widehat{A}\times \mathbb{N},\mu)\end{CD}$$where $M_{\widehat{T}}$ is a [[Multiplication Operator on Lp Space|multiplication operator]] s.t. $(M_{\widehat{T}}f)(\chi,n)=\widehat{T}(\chi)f(\chi,n)$.

> [!proof]+
> Let $E$ be the resolution of identity given by the [[Guelfand Spectrum|spectral theorem]], i.e. for all $T\in A$: $$T=\int_{\widehat{A}}^{} \widehat{T} \, dE $$Let $v\neq 0$. Then, $\braket{ Tv , v } =\int_{\widehat{A}}^{} \widehat{T} \, dE_{v,v}$ but as $E_{v,v}$ is a positive Borel regular measure on $\widehat{A}$ with $E_{v,v}(\widehat{A})=\braket{ v,v}=\|v\|^{2}$, $$\left\| Tv \right\| ^{2} =\braket{ T^{*}Tv , v } =\int_{\widehat{A}}^{} \overline{\widehat{T}}\widehat{T} \, dE_{v,v}=\int_{\widehat{A}}^{} \left| \widehat{T} \right| ^{2} \, dE_{v,v}  $$
> For all $T\in A$, so $T(v)=0$ if and only if $\widehat{T}=0$ $E_{v,v}$-almost everywhere. Hence, $$\begin{array}{cccc} {}&{Av}&\to&{L^2(\widehat{A},E_{v,v})}\\&{Tv} &\mapsto & {\widehat{T}} \end{array}{}$$is a well-defined linear isometry. This extends to $L_{v}:\overline{Av}\to L^2(\widehat{A},E_{v,v})$ which is.a linear isometry and injective since $L_{v}(Av)=C(\widehat{A})$ and $C(\widehat{A})$ is dense in $L^2(\widehat{A},E_{v,v})$.
> 
> Let $T\in A$ and $w:=Sv$ where $S\in A$. Then, $$L_{v}(Tw)=L_{v}(TSv)=\widehat{T}\widehat{S}=\widehat{T}L_{v}(Sv)=\widehat{T}L_{v}(w)$$By continuity, this extends to all $w\in \overline{Av}$. 
> 
> Let $J\subseteq \mathbb{N}$ from the previous lemma. Then, $\mathcal{H}=\widehat{\bigoplus}_{n\in J}\overline{Av_{n}}$. Modulo rescaling, we may assume that $\sum_{n\in J}^{}\left\| v_{n} \right\|^{2}<+\infty$. Define $f\in C_{0}(\widehat{A}\times J)$. Then, $$\int_{\widehat{A}\times J} f  \, d\mu=\sum_{n\in J}^{}\int_{\widehat{A}}^{} f(x,n) \, dE_{v_{n},v_{n}}  $$and $\mu(\widehat{A}\times J)=\sum_{n\in J}^{}E_{v_{n},v_{n}}(\widehat{A})=\sum_{n\in J}^{}\left\| v_{n} \right\|^{2}<+\infty$. Therefore, $\Lambda:\mathcal{H}\to L^{2}(\widehat{A}\times J,\mu)$ where: $$\Lambda(w)(\chi,n)=L_{v_{n}}(w_{n})(\chi)$$where $w=\sum_{n\in J}^{}w_{n}$ with $w_{n}\in \overline{Av_{n}}$.
- **Remark**: from $J$ in Lemma, we can replace $\widehat{A}\times \mathbb{N}$ with $\widehat{A}\times J$ in which case $\mu(\widehat{A}\times \{ n \})>0$ for all $n\in J$. Especially, if there exists a cyclic vector for $A$, i.e. there exists $v\in \mathcal{H}$ with $\overline{Av}=\mathcal{H}$, then $\widehat{A}\times \mathbb{N}$ can be replaced with $\widehat{A}$.
---
##### Example
> [!h] Example 1
> Let $\mathcal{H}$ be finite dimensional. Then for $T\in \mathcal{B}(\mathcal{H})$ with $T=T^{*}$
---