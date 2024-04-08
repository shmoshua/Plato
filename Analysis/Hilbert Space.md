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
> [!lemma] Theorem
> Let $\mathcal{H}$ be a [[Separable Space|separable]] Hilbert space and $A\subseteq \mathcal{B}(\mathcal{H})$ is a [[C*-Algebra|commutative sub-$C^{*}$-algebra]] containing $\text{id}_{\mathcal{H}}$. Then, 
> 1. there exists a finite positive Borel regular measure $\mu$ on $\widehat{A}\times \mathbb{N}$
> 2. there exists a Hilbert space isomorphism $\Lambda:\mathcal{H}\to L^{2}(\widehat{A}\times \mathbb{N},\mu)$ s.t. for all $T\in A$ and $v\in \mathcal{H}$, $$\Lambda(Tv)(\chi,n)=\widehat{T}(\chi)\Lambda(v)(\chi,n)$$In other words, the following diagram commutes: $$\begin{CD}\mathcal{H} @>\Lambda>>L^2(\widehat{A}\times \mathbb{N},\mu)\\@VTVV&@VVM_{\widehat{T}}V\\\mathcal{H}@>\Lambda>>L^2(\widehat{A}\times \mathbb{N},\mu)\end{CD}$$where $M_{\widehat{T}}$ is a [[Multiplication Operator on Lp Space|multiplication operator]] s.t. $(M_{\widehat{T}}f)(\chi,n)=\widehat{T}(\chi)f(\chi,n)$.
---
##### Example
> [!h] Example 1
> Let $\mathcal{H}$ be finite dimensional. Then for $T\in \mathcal{B}(\mathcal{H})$ with $T=T^{*}$