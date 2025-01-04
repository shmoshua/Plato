#Definition #AlgebraicTopology 

> [!definition]
> Let $f:S^n\to S^n$ be a [[Continuous Function|continuous map]]. Let $H$ be a [[homology theory]] with coefficients group $\mathbb{Z}$.
> 1. 
> The ***degree*** of $f$, denoted as $\text{deg}(f)$, is the unique integer $d\in \mathbb{Z}$ s.t. $$f_{*}:\tilde{H}_{n}(S^n)\to \tilde{H}_{n}(S^n),\quad a\mapsto d \cdot a$$

---
##### Properties
> [!lemma] Proposition 1
> For all $f:S^n\to S^n$ continuous and homology theory $H$ with coefficients $\mathbb{Z}$, 
> 1. $\deg(f)$ is well-defined.
> 2. $\deg(\text{id})=1$.
> 3. $\deg(g \circ f)=\deg(g)\deg(f)$
> 4. if $f\sim g$ are [[Homotopy|homotopic]], then $\deg(f)=\deg(g)$.
> 5. $\deg(c)=0$ for any non-surjective function $f$.

> [!proof]-
> We have that:
> 1. Recall that from [[Homology Theory|Example 1]], $\tilde{H}_{n}(S^n)\cong \mathbb{Z}$.  Let $\tau:\mathbb{Z} \to \tilde{H}_{n}(S^n)$ be an isomorphism. Then, we have that: $$\begin{CD}\mathbb{Z}@>\varphi>> \mathbb{Z}\\@V\tau VV@V\tau VV\\\tilde{H}_{n}(S^n)@>>f_{*}> \tilde{H}_{n}(S^n) \end{CD}$$commutes. However, we have that $\varphi(i):= d \cdot i$ for some $d$. Hence, we have that: $$f_{*}(a)=\tau(d(\tau ^{-1}(a)))=d \cdot  a$$
> 2. We have that: $f_{*}=\text{id}_{\tilde{H}_{n}(S^n)}$.
> 3. $(g\circ f)_{*}(a)=g_{*}(f_{*}(a))=\deg(g)\deg(f)a$.
> 4. Follows from [[Homology Theory|homotopy invariance]].
> 5. Let $x\in S^n \backslash f(S^n)$. Then, $f$ can be factored into $S^n \xrightarrow{f'} S^n \backslash \{ x \}\xrightarrow{i} S^n$. Then, we have that: $$f_{*}= i_{*} \circ  f'_{*}=0$$as $S^n \backslash \{ x \}$ is contractible and hence $\tilde{H}_{p}(S^n \backslash\{ x \})=0$.
---
> [!lemma] Theorem 2
> We have that:
> 1. for $f:S^n\to S^n, (x_{0},x_{1},\dots,x_{n})\mapsto (-x_{0},x_{1},\dots,x_{n})$, $\deg(f)=-1$.
> 2. for $\tau_{i}:S^n\to S^n,(x_{0},\dots,x_{n})\mapsto (x_{0},\dots,-x_{i},\dots,x_{n})$, $\deg(\tau_{i})=-1$.
> 3. for $\sigma:S^n\to S^n,(x_{0},\dots,x_{n})\mapsto (-x_{0},\dots,-x_{n})$, $\deg(\sigma)=(-1)^{n+1}$.

> [!proof]-
> We have that:
> 1. First, let $n=0$. Then, $f:\{ \pm 1 \}\to \{ \pm 1 \}$ where $f(1)=-1$ and $f(-1)=1$.
> 
> 	Let $i^{\pm}:\{ \pm 1 \}\hookrightarrow S^0$ be the inclusion and $\tau^{\pm}:=\varepsilon  \circ i^{\pm}$. Then, $\tau^{\pm}$ is a homotopy equivalence and $\tau^{\pm}_{*}:H_{0}(\{ \pm 1\})\to \mathbb{Z}$ is an isomorphism. Now, we show that the following commutes.$$\begin{CD}H_{0}(\{ -1 \})\oplus H_{0}(\{ 1 \})@>q>> H_{0}(S^0)\\@V\tau:=\tau^-_{*}\oplus \tau^+_{*}VV@V\varepsilon_{*}VV \\\mathbb{Z}\oplus \mathbb{Z}@>>\varphi> \mathbb{Z}\end{CD}$$where $q$ is the isomorphism given by additivity i.e. $q(x,y)=i^-_{*}(x)+ i^+_{*}(y)$ and $\varphi(a,b)=a+b$. For $(x,y)\in H_{0}(\{ -1 \})\oplus H_{0}(\{ 1 \})$, we have that: $$\varphi(\tau(x,y))=\tau^-_{*}(x)+\tau^+_{*}(y)=\varepsilon_{*}(i^-_{*}(x)+i^+_{*}(y))=\varepsilon_{*}(q(x,y))$$
> 
> 
> 	Now, let $X:=\{ (a,-a):a\in \mathbb{Z} \}\subseteq \mathbb{Z}\oplus \mathbb{Z}$. Then, we have that $\tau(q^{-1}(\tilde{H}_{0}(S^0)))=X$. Indeed, for $x\in \tilde{H}_{0}(S^0)$, $\varphi(\tau(q ^{-1}(x)))=\varepsilon_{*}(x)=0$ and $\tau(q^{-1}(x))\in X$. On the other hand if $x\in X$, then $0=\varphi(x)=\varepsilon_{*}(q(\tau ^{-1}(x)))$ and $q(\tau ^{-1}(x))\in\tilde{H}_{0}(S^0)$.
> 	
> 	Hence, we get that $$\begin{CD}\tilde{H}_{0}(S^0)@<<<X@<<< \mathbb{Z}\\@Vf_{*}VV@VVV@VVa\mapsto -aV\\\tilde{H}_{0}(S^0)@>>> X @>>>\mathbb{Z}\end{CD}$$and $\deg(f)=-1$.
> 
> 	Now, let $n\geq 1$ and assume that the statement holds for all $0\leq k<n$. Let again have:
> 	1. $B^n_{+}:=\{ x\in S^n:x_{n}\geq 0 \}$
> 	2. $B^n_{-}:=\{ x\in S^n:x_{n}\leq 0 \}$
> 	3. $B^n_{+,\varepsilon}:=\{ x\in S^n:x_{n}\geq -\varepsilon \}$
> 	4. $L_{\varepsilon}:=\{ x\in S^n:-\varepsilon\leq x\leq 0 \}$
> 
> 	Then, we have that:
> 	1. $\tilde{H}_{n}(S^n)\cong H_{n}(S^n, B^n_{+})$ from [[Homology Theory|Example 1]].
> 	2. $H_{n}(S^n,B^n_{+})\cong H_{n}(S^n,B^n_{+,\varepsilon})$ as they have the same homotopy type, from [[Homology Theory|Lemma 1.3]]
> 	3. $H_{n}(S^n,B^n_{+,\varepsilon})\cong H_{n}(B^n_{-},L_{\varepsilon})$ from excision.
> 	4. $H_{n}(B^n_{-},L_{\varepsilon})\cong H_{n}(B^n_{-},S^{n-1})$ again from homotopy type.
> 	5. $\tilde{\partial}_{*}:H_{n}(B^n_{-},S^{n-1})\to \tilde{H}_{n-1}(S^{n-1})$ is an isomorphism as: $$0=\tilde{H}_{n}(B^n_{-})\to H_{n}(B^n_{-},S^{n-1}) \to \tilde{H}_{n-1}(S^{n-1}) \to \tilde{H}_{n-1}(B^{n}_{-})=0$$is an exact sequence and the fact that $B^n_{-}$ is contractible.
>    
> 	Therefore, we have that: $$\begin{CD}\tilde{H}_{n}(S^n) @>\cong>> \tilde{H}_{n-1}(S^{n-1})\\@Vf_{*}VV @V(f|_{S^{n-1}})_{*}VV\\\tilde{H}_{n}(S^n) @>\cong>> \tilde{H}_{n-1}(S^{n-1})\end{CD}$$where by induction the right column is a multiplication by -1. Hence, so is $f_{*}$ and $\deg(f)=-1$.
> 2. We will show that $\tau_{i-1}\sim \tau_{i}$ for all $1\leq i\leq n$. We have that: $$\underbrace{ \begin{bmatrix}I\\&-1\\&&-1\\&&&I\end{bmatrix} }_{ =:f }\tau_{i-1}=\tau_{i}$$ where $f\sim \text{id}$. Hence, $\tau_{i-1}\sim f \circ \tau_{i-1}=\tau_{i}$. Therefore, $\deg(\tau_{i-1})=\deg(\tau_{i})$ and as $\tau_{0}=f$ from 1, we have that $\deg(\tau_{i})=-1$.
> 3. Follows from the fact that $\sigma=\tau_{0} \circ \dots \circ \tau_{n}$. 
- **Corollary**: If $n$ is even, we have that $\sigma \not\sim \text{id}$ as $\deg(\sigma)=-1\neq 1 =\deg(\text{id})$.
---
> [!lemma] Corollary 3 (Hairy Ball Theorem)
> Let $n$ be even. 
> 1. For any continuous map $f:S^n\to S^n$, there exists $x\in S^n$ s.t. $f(x)\in \{ x,-x \}$.
> 2. For any continuous [[vector field]] $v:S^n\to \text{T}S^n$ where $\text{T}_{x}S^n:=\{ y\in \mathbb{R}^{n+1}:x{\bot}y \}$, there exists $x_{0}\in S^n$ with $v(x_{0})=0$.

> [!proof]-
> We have that:
> 1. Suppose by contradiction we have that $f(x)\notin \{ x,-x \}$ for all $x\in S^n$. Then, we define the following two homotopies: $$F:S^n\times I\to S^n,\quad (x,t)\mapsto \frac{tf(x)+(1-t)x}{\left\| tf(x)+(1-t)x \right\| }$$and $$G:S^n\times I\to S^n,\quad (x,t)\mapsto \frac{tf(x)-(1-t)x}{\left\| tf(x)-(1-t)x \right\| }$$Then, $F$ is a homotopy from $\text{id}$ to $f$ and $G$ is a homotopy from $\sigma$ to $f$ where $\sigma$ is the antipodal map from Theorem 2.3. Note that the homotopies are well-defined. Indeed, assume that $tf(x)+(1-t)x=0$ for some $x,t$. First, as $f(x)\neq x$, we have that this can only happen if $t = \frac{1}{2}$. In which case $f(x)+x = 0$ and $f(x)=-x$, which is a contradicton.
> 
> 	Hence, $\text{id}\sim \sigma$ which is a contradiction to the Corollary of Theorem 2.
> 2. Suppose by contradiction that $\text{supp }v=S^n$. Consider the map: $$f:S^n\to S^n,\quad x\mapsto \frac{v(x)}{\left\| v(x) \right\| }$$Then, clearly $f(x)\in \text{T}_{x}S^n$. However, as $x,-x\notin \text{T}_{x}S^n$, we have that $f(x)\notin \{ x,-x \}$ for all $x\in S^n$. This is a contradiction to 1. 
---
> [!lemma] Proposition 4 (Linear Maps)
> Let $A\in \text{GL}(n,\mathbb{R})$. Then, 
> 1. $\widehat{A}:\mathbb{R}^n\cup \{ \infty \}\to \mathbb{R}^n\cup \{ \infty \}$ given by $\widehat{A}|_{\mathbb{R}^n}=A$ and $\widehat{A}(\infty)=\infty$ has degree: $$\deg(\widehat{A}):=\text{sgn}(\det A)\in\{ -1,+1 \}$$

> [!proof]-
> We have that:
> 1. We first claim that for $A,B\in \text{GL}(n,\mathbb{R})$, if the statements hold for $A,B$ then it also does for $AB$. We have that: $$\deg(\widehat{AB})=\deg(\widehat{A} \circ \widehat{B})=\deg(\widehat{A})\deg(\widehat{B})=\text{sgn}(\det A)\cdot  \text{sgn}(\det B)=\text{sgn}(\det AB)$$
>    Now, let $A=E_{1}\dots E_{r}$ be the Gaussian elimination of $A$, i.e. $E_{1},\dots,E_{r}\in \text{GL}(n,\mathbb{R})$ are elementary matrices of the following type:
>    $$\begin{bmatrix}I_{i}\\&\lambda\\&&I_{n-i-1}\end{bmatrix},\begin{bmatrix} I_{i-1}& \\&1&&\xi \\&&I_{j-i-1}&\\&&&1 \\&&&&I_{n-j} \end{bmatrix},\begin{bmatrix} I_{i-1}& \\&&&1 \\&&I_{j-i-1}&\\&1&& \\&&&&I_{n-j} \end{bmatrix}$$where $\lambda\neq 0$ and $\xi\in \mathbb{R}$. Hence, it suffices to show that the statement holds for these elementary matrices.
>    1. For $E$ in Type 1, we have that: $\widehat{E} \sim \widehat{\begin{bmatrix}I_{i}\\&\text{sgn}(\lambda)\\&&I_{n-i-1}\end{bmatrix}}$. Further, we have that: $\det(E)=\lambda$. Therefore, we have that: $\deg(\widehat{E})=\text{sgn}(\lambda)=\text{sgn}(\det(E))$.
>    2. For $E$ in Type 2, we first define $$E_{t}:=\begin{bmatrix} I_{i-1}& \\&1&&t\xi \\&&I_{j-i-1}&\\&&&1 \\&&&&I_{n-j} \end{bmatrix}$$Then, $$F:\mathbb{R}^n\cup \{ \infty \}\times[0,1]\to \mathbb{R}^n\cup \{ \infty \},\quad (x,t)\mapsto  \widehat{E}_{t}(x)$$defines a homotopy from $\widehat{E}$ to $\text{id}$. Therefore, $\deg(\widehat{E})=\deg(\text{id})=1=\text{sgn}(1)=\text{sgn}(\det E)$.
>    3.  For $E$ in Type 3, $E$ is a reflection about some hyperplane in $\mathbb{R}^n$. By changing coordinates, we can write $E$ as $\begin{bmatrix}I\\&-1\end{bmatrix}$. Hence, $$\deg(\widehat{E})=-1=\text{sgn}(-1)=\text{sgn}(\det E)$$
---
> [!lemma] Theorem 5 (Smooth Maps)
> Let $f:S^n\to S^n$ be a [[Smooth Function|smooth map]]. For $p\in S^n$, we define $$\varepsilon_{p}(f):=\text{sgn}(\det d_p(\sigma \circ f))\in\{ -1,0,+1 \}$$where $\sigma\in \text{SO}(n+1)$ s.t. $\sigma(f(p))=p$. Then,
> 1. $\varepsilon_{p}(f)$ is independent of the choice of $\sigma$.
> 2. If $q\in S^n$ is a [[Submanifold|regular value]] s.t. $f^{-1}(q)=\{ p \}\subseteq S^n$, then $\deg(f)=\varepsilon_{p}(f)\in \{ -1,+1 \}$.

> [!proof]+
> We have that:
> 1. Let $\sigma,\sigma'$ be two such maps. Then, $$\sigma'\circ f=(\sigma'\circ \sigma ^{-1})\circ (\sigma \circ f)$$and we have: $$\det d_{p}(\sigma'\circ f)=\det (d_{p}(\sigma' \circ \sigma ^{-1})d_{p}(\sigma \circ f))=\det(\sigma'\circ \sigma ^{-1})\det(d_{p}(\sigma \circ f))=\det(d_{p}(\sigma \circ f))$$
> 2. Let $\hat{\pi}:S^n\to \mathbb{R}^n \cup \{ \infty\}$ be the homeomorphism from [[One-Point Compactification|Example 1]]. Let $\sigma_{1},\sigma_{2}\in \text{SO}(n+1)$ with $\sigma_{1}(0)=p$ and $\sigma_{2}(q)=0$. Then, let $f':= \sigma_{2} \circ f \circ \sigma_{1}$. Then, if the statement holds for $f'$, we have that: $$\deg(f)=\deg(f')=\text{sgn}(\det d_{0}( \sigma_{2} \circ  f \circ  \sigma_{1}))=\text{sgn}(\det d_{p}(\sigma \circ  f))=\varepsilon_{p}(f)$$Hence, it suffices to show for the case where $p=q=0$.