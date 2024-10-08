#Definition #Algebra

> [!definition]
> Let $K$ be a field. The ***general linear group*** for $n\in \mathbb{N}$, denoted as $(\text{GL}(n,K),\cdot)$ is defined as: $$\text{GL}(n,K):=\{  A\in \text{M}(n,K):\det(A)\neq 0 \}$$
> where $\text{M}(n,K)$ is the set of all $n\times n$ matrices with elements in $K$ as entries.

- $\text{GL}(1,\mathbb{R})\cong (\mathbb{R}^*,\cdot)$ which means $\text{GL}(1)$ is abelian.
- For $n>1$, $\text{GL}(n,\mathbb{R})$ is non-abelian as matrix multiplications don't commute.
---
##### Properties
> [!lemma] Proposition 1
> Consider the injection: $$\begin{array}{cccc} {\Psi:}&{\text{GL}(n,\mathbb{R})}&\to&{\text{Homeo}(\mathbb{R}^n)}\\&{A} &\mapsto & {(x\mapsto Ax)} \end{array}{}$$Then, 
> 1. $\Psi(\text{GL}(n,\mathbb{R}))\subseteq \text{Homeo}(\mathbb{R}^n)$ is closed w.r.t. [[Compact-Open Topology]].
> 2. the induced subspace topology coincides with the euclidean topology on $\text{GL}(n,\mathbb{R})$.

> [!proof]-
> We have: 
> 1. We can characterize: $$\Psi(\text{GL}(n,\mathbb{R}))=\{ f\in \text{Homeo}(\mathbb{R}^n): f(\lambda a+b)=\lambda f(a)+f(b), \forall\lambda,a,b\in \mathbb{R} \}$$Then, for $\lambda,a,b\in \mathbb{R}$, the evaluation map $f\mapsto f(\lambda a+b)-\lambda f(a)-f(b)$ is continuous and therefore, $$\Psi(\text{GL}(n,\mathbb{R}))=\bigcap_{\lambda,a,b\in \mathbb{R}}^{}\text{ker }\text{ev}_{\lambda,a,b}$$is a closed set.
---
> [!lemma] Proposition 2
> We have that:
> 1. $\text{GL}(n,\mathbb{R})\cong \text{Aut}(\mathbb{R}^n)$.
> 2. Any compact subgroup of $\text{GL}(n,\mathbb{R})$ is conjugate to a subgroup of $\text{O}(n,\mathbb{R})$.

> [!proof]-
> We have:
> 1. Consider the map: $$\Psi:\text{GL}(n,\mathbb{R})\to \text{Aut}(\mathbb{R}^n),\quad A\mapsto (x\mapsto Ax)$$
> Then, 
>    1. **Showing $\Psi(A)\in \text{Aut}(\mathbb{R}^n)$:**
> 		   We know that $\Psi(A)$ is continuous, bijective with a continuous inverse. Further, the linearity guarantees that it is a homomorphism.
> 	1. **Showing $\Psi$ is injective**:
>    Let $\Psi(A)(x)=x$ for all $x\in \mathbb{R}^n$. Then, $Ax=x$ for all $x\in \mathbb{R}^n$ and $A=I_{n}$.
>    3. **Showing $\Psi$ is surjective**:
>    Let $\varphi\in \text{Aut}(\mathbb{R}^n)$. Let $A:=[A_{1}|\dots|A_{n}]$ where $A_{i}:=\varphi(e_{i})$. Then, for any $x:=\sum_{i=1}^{n}\xi_{i}e_{i}\in \mathbb{R}^n$, $$\Psi(A)(x)=\sum_{i=1}^{n}\xi_{i}A_{i}=\sum_{i=1}^{n}\xi_{i}\varphi(e_{i})=\varphi\left( \sum_{i=1}^{n}\xi_{i}e_{i} \right)=\varphi(x)$$
>    4. **Showing that $\Psi$ is continuous**:
>    We want to show that if $A_{n}\to A$, $\Psi(A_{n})\to \Psi(A)$ in $\text{Aut}(\mathbb{R}^n)$. As $\mathbb{R}^n$ is metric, the compact open topology coincides with the topology of compact convergence. Let $K$ compact $\varepsilon>0$ s.t $$\mathcal{U}(\Psi(A),K,\varepsilon):=\{g:\mathbb{R}^n\to \mathbb{R}^n|\ \text{sup}_{x\in K}\|Ax-g(x)\|_{2}<\varepsilon  \}$$As we have $\|(A_{n}-A)x\|_{2}\leq\|A_{n}-A\|\|x\|_{2}\leq\|A_{n}-A\|_{F}\|x\|_{2}$, if we let $c:=\sup_{x\in K}\|x\|_{2}$, we find $N$ s.t. $\|A_{n}-A\|_{F}< \varepsilon /c$ for all $n\geq N$. Then, for any $x\in K$, $\|(A_{n}-A)x\|_{2}<\varepsilon$ and $\Psi(A_{n})\in \mathcal{U}(\Psi(A),K,\varepsilon)$. This proves the statement.
>    5. **Showing that $\Psi ^{-1}$ is continuous**:
>    Let $B_{<\varepsilon}(I)$ be an open ball. Then, let $K:= B_{\leq 1}(0)$ and $A\in B_{<\varepsilon}(I)$. From the equivalence of norm, there exists $\varepsilon'$ s.t. if $\|A-B\|<\varepsilon'$ then $\|A-B\|_{F}<\varepsilon$. Then, $$\mathcal{U}(\Psi(A),K,\varepsilon')\subseteq \Psi(B_{<\varepsilon}(I))$$This proves the statement.
> 2. Let $K\leq \text{GL}(n,\mathbb{R})$ compact and let $\mu$ be the left Haar measure of $K$. As $K$ is compact, it is [[Unimodular Group|unimodular]] and $\mu$ is also the right Haar measure. Moreover, $\mu$ is finite as $K$ is compact. Let $(,)$ be a positive definite scalar product. Then, we define: $$\braket{ v , w } :=\int_{K}(gv,gw) \, d\mu(g) $$Then, 
> 	- **$\braket{  ,  }$ is $K$-invariant**
> 	  where $K$-invariant means that $\braket{ gv , gw }=\braket{ v , w }$. We have: $$\begin{align}\braket{ hv , hw } =\int_{K}(ghv,ghw) \, d\mu(g)=\int_{K}(gv,gw) \, d\mu(g)=\braket{ v , w }   \end{align}$$where we use the right invariance of $\mu$.
> 	- **$\braket{  ,  }$ is a positive definite scalar product**. 
> 	  we have that: 
> 	   1. $\braket{ \alpha v_{1}+v_{2} , w } =\int_{K}(g\alpha v_{1}+gv_{2},w) \, dx =\alpha\braket{  v_{1} , w }+ \braket{ v_{2} , w }$ and 
> 	   2. $\overline{\braket{ w , v }}=\int_{K}\overline{(gw,gv)} \, d\mu(g)=\int_{K}^{} (gv,gw) \, d\mu(g)=\braket{ v , w }$
> 	   3. $\braket{ v , v }=0$ then $\int_{K}(gv,gv)  \, d\mu(g)=0$ and $(gv,gv)=0$ which means $v=0$. The other direction holds trivially.
> 	
> 	Therefore, there exists $A,B\in \text{Mat}_{n,n}(\mathbb{R})$ s.t. $\braket{ v , w }=v^\top Aw$, $A$ symmetric positive definite and $B$ symmetric positive definite with $B^{2}=A$.
> 	
> 	We claim that $B^{-1}KB\leq \text{O}(n,\mathbb{R})$. For $g\in K$, we have: $$B^{-1}gB  B g^\top B^{-1}=B^{-1}\underbrace{ gAg^\top }_{ A } B^{-1}=B^{-1}AB^{-1}=I_{n}$$Therefore, $B^{-1}gB$ is orthogonal.
---
> [!lemma] Proposition 3
> Let $\mathfrak{gl}(n,\mathbb{R})$ be the [[Lie algebra]] of $\text{GL}(n,\mathbb{R})$. Consider the map: $$\text{Mat}_{n,n}(\mathbb{R})\to \mathfrak{gl}(n,\mathbb{R}),\quad A\mapsto A_{I}$$where $A_{I}(f):= \left. \frac{d}{dt} \right|_{t=0}f(I+tA)$ for $f\in C^\infty(\text{Mat}_{n,n}(\mathbb{R}))$. Then, 
> 1. this map is a Lie algebra isomorphism, where $\text{Mat}_{n,n}(\mathbb{R})$ is endowed with $[A,B]=AB-BA$.

> [!proof]-
> We need to show that: $[A,B]_{I}=[A_{I},B_{I}]$. Recall that we have: $[A_{I},B_{I}]=[A_{I}^L,B_{I}^L]_{I}$ where, $$\mathfrak{gl}(n,\mathbb{R})\to\Gamma(\text{TGL}(n,\mathbb{R})),\quad X\mapsto X^L$$with $(X^L)_{g}:=d_{I}L_{g}(X)$.
> 
> As $\text{GL}(n,\mathbb{R})\subseteq \text{Mat}_{n,n}(\mathbb{R})$ open, we can use [[Tangent Space|Example 2]]. Therefore, we want to show that: $$[A,B]_{I}=[A^L_{I},B^L_{I}]_{I}\in\mathfrak{gl}(n,\mathbb{R})$$Per Example 2, this can be done by checking that $d_{I}\lambda([A,B]_{I})=d_{I}\lambda([A^L_{I},B^L_{I}]_{I})$ for all $\lambda\in \text{Mat}_{n,n}(\mathbb{R})^{*}$. We have:
> 1. $d_{I}\lambda([A,B]_{I})=[A,B]_{I}(\lambda)=\left. \frac{d}{dt} \right|_{t=0}\lambda(I+t[A,B])=\lambda([A,B])=\lambda(AB)-\lambda(BA)$.
> 2. $d_{I}\lambda([A^L_{I},B^L_{I}]_{I})=[A_{I}^L,B_{I}^L]_{I}(\lambda)=A_{I}(B^L_{I}(\lambda))-B_{I}(A_{I}^L(\lambda))$.
>    
>  We will show that $A_{I}(B^L_{I}(\lambda))=\lambda(AB)$. We have: $$\begin{align}A_{I}(B_{I}^L(\lambda))&=A_{I}(g\mapsto (B_{I}^L)_{g}(\lambda))\\&=A_{I}(g\mapsto d_{I}L_{g}(B_{I})(\lambda))\\&=A_{I}(g\mapsto B_{I}(h\mapsto\lambda(gh)))\\&=A_{I}(g\mapsto \lambda(gB))\\&=\lambda(AB)\end{align}$$This concludes the proof by symmetry.
- **Remark**: This allows us to also treat $\mathfrak{gl}(n,\mathbb{R})$ as $\text{Mat}_{n,n}(\mathbb{R})$.
---
> [!lemma] Theorem 4 (Ado)
> Any finite dimensional [[Lie algebra]] over $\mathbb{R}$ is a Lie subalgebra of $\mathfrak{gl}(n,\mathbb{R})$ for some $n\in \mathbb{N}$.
- **Corollary**: Any Lie group $G$ is locally isomorphic to a subgroup of $\text{GL}(n,\mathbb{R})$ for some $n\in \mathbb{N}$, as $\mathfrak{g}$ is a Lie subalgebra of $\mathfrak{gl}(n,\mathbb{R})$ by [[Lie Subgroup|Theorem 1]] there exists a Lie subgroup of $\text{GL}(n,\mathbb{R})$ corresponding with the Lie subalgebra and by [[Lie Algebra|Theorem 5]], there exists a local isomorphism.
---
