#Definition #AlgebraicTopology 

> [!definition]
> Let $f:S^n\to S^n$ be a [[Continuous Function|continuous map]]. Let $H$ be a [[homology theory]] with coefficients group $\mathbb{Z}$.
> 1. 
> The ***degree*** of $f$, denoted as $\text{deg}(f)$, is the unique integer $d\in \mathbb{Z}$ s.t. $$f_{*}:\tilde{H}_{n}(S^n)\to \tilde{H}_{n}(S^n),\quad a\mapsto d \cdot a$$

^475803

---
##### Properties
> [!lemma] Proposition 1
> For all $f:S^n\to S^n$ continuous and homology theory $H$ with coefficients $\mathbb{Z}$, 
> 1. $\deg(f)$ is well-defined.
> 2. $\deg(\text{id})=1$.
> 3. $\deg(g \circ f)=\deg(g)\deg(f)$
> 4. if $f\sim g$ are [[Homotopy|homotopic]], then $\deg(f)=\deg(g)$.
> 5. $\deg(c)=0$ for any non-surjective function $f$.

^0c3745

> [!proof]-
> We have that:
> 1. Recall that from [[Homology Theory|Example 1]], $\tilde{H}_{n}(S^n)\cong \mathbb{Z}$.  Let $\tau:\mathbb{Z} \to \tilde{H}_{n}(S^n)$ be an isomorphism. Then, we have that: $$\begin{CD}\mathbb{Z}@>\varphi>> \mathbb{Z}\\@V\tau VV@V\tau VV\\\tilde{H}_{n}(S^n)@>>f_{*}> \tilde{H}_{n}(S^n) \end{CD}$$commutes. However, we have that $\varphi(i):= d \cdot i$ for some $d$. Hence, we have that: $$f_{*}(a)=\tau(d(\tau ^{-1}(a)))=d \cdot  a$$
> 2. We have that: $f_{*}=\text{id}_{\tilde{H}_{n}(S^n)}$.
> 3. $(g\circ f)_{*}(a)=g_{*}(f_{*}(a))=\deg(g)\deg(f)a$.
> 4. Follows from [[Homology Theory|homotopy invariance]].
> 5. Let $x\in S^n \backslash f(S^n)$. Then, $f$ can be factored into $S^n \xrightarrow{f'} S^n \backslash \{ x \}\xrightarrow{i} S^n$. Then, we have that: $$f_{*}= i_{*} \circ  f'_{*}=0$$as $S^n \backslash \{ x \}$ is contractible and hence $\tilde{H}_{p}(S^n \backslash\{ x \})=0$.

^f7210e

---
> [!lemma] Theorem 2
> We have that:
> 1. for $f:S^n\to S^n, (x_{0},x_{1},\dots,x_{n})\mapsto (-x_{0},x_{1},\dots,x_{n})$, $\deg(f)=-1$.
> 2. for $\tau_{i}:S^n\to S^n,(x_{0},\dots,x_{n})\mapsto (x_{0},\dots,-x_{i},\dots,x_{n})$, $\deg(\tau_{i})=-1$.
> 3. for $\sigma:S^n\to S^n,(x_{0},\dots,x_{n})\mapsto (-x_{0},\dots,-x_{n})$, $\deg(\sigma)=(-1)^{n+1}$.

^0901d5

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

^cb5ea4

- **Corollary**: If $n$ is even, we have that $\sigma \not\sim \text{id}$ as $\deg(\sigma)=-1\neq 1 =\deg(\text{id})$. ^d5b3d2
---
> [!lemma] Corollary 3 (Hairy Ball Theorem)
> Let $n$ be even. 
> 1. For any continuous map $f:S^n\to S^n$, there exists $x\in S^n$ s.t. $f(x)\in \{ x,-x \}$.
> 2. For any continuous [[vector field]] $v:S^n\to \text{T}S^n$ where $\text{T}_{x}S^n:=\{ y\in \mathbb{R}^{n+1}:x{\bot}y \}$, there exists $x_{0}\in S^n$ with $v(x_{0})=0$.
> 3. For any continuous map $f:S^n\to S^n$, if $f$ has no fixed point, then $\deg f=(-1)^{n+1}$
> 4. For any free action $G \curvearrowright S^n$, $G$ is either trivial or isomorphic to $\mathbb{Z} / 2\mathbb{Z}$.

^2fc6d4

> [!proof]-
> We have that:
> 1. Suppose by contradiction we have that $f(x)\notin \{ x,-x \}$ for all $x\in S^n$. Then, we define the following two homotopies: $$F:S^n\times I\to S^n,\quad (x,t)\mapsto \frac{tf(x)+(1-t)x}{\left\| tf(x)+(1-t)x \right\| }$$and $$G:S^n\times I\to S^n,\quad (x,t)\mapsto \frac{tf(x)-(1-t)x}{\left\| tf(x)-(1-t)x \right\| }$$Then, $F$ is a homotopy from $\text{id}$ to $f$ and $G$ is a homotopy from $\sigma$ to $f$ where $\sigma$ is the antipodal map from Theorem 2.3. Note that the homotopies are well-defined. Indeed, assume that $tf(x)+(1-t)x=0$ for some $x,t$. First, as $f(x)\neq x$, we have that this can only happen if $t = \frac{1}{2}$. In which case $f(x)+x = 0$ and $f(x)=-x$, which is a contradicton.
> 
> 	Hence, $\text{id}\sim \sigma$ which is a contradiction to the Corollary of Theorem 2.
> 2. Suppose by contradiction that $\text{supp }v=S^n$. Consider the map: $$f:S^n\to S^n,\quad x\mapsto \frac{v(x)}{\left\| v(x) \right\| }$$Then, clearly $f(x)\in \text{T}_{x}S^n$. However, as $x,-x\notin \text{T}_{x}S^n$, we have that $f(x)\notin \{ x,-x \}$ for all $x\in S^n$. This is a contradiction to 1. 
> 3. Let $f$ have no fixed point. Then, for any $x\in X$, $(1-t)f(x)-tx\neq 0$ for all $t\in [0,1]$. Therefore, $$F:S^n\times I\to S^n,\quad (x,t)\mapsto \frac{(1-t)f(x)-tx}{\left\| (1-t)f(x)-tx \right\| }$$is a homotopy from $f$ to $-\text{id}$. Therefore, $\deg(f)=\deg(\sigma)=(-1)^{n+1}$. 
> 4. Let $\rho:G\to \text{Homeo}(S^n)$. Notice that for a homeomorphism $f\in \text{Homeo}(S^n)$, $\deg(f)\in\{ \pm 1 \}$. Therefore, we can define: $$d:G\to \{ \pm 1 \},\quad g\mapsto \deg(\rho(g))$$where this is a group homomorphism as: $$d(gh)=\deg(\rho(gh))=\deg(\rho(g)\circ \rho(h))=\deg(\rho(g))\deg(\rho(h))=d(g)d(h)$$However, for any $e\neq g\in G$, as the action is free $\rho(g)$ has no fixed point and by 3, $\deg(f)=(-1)^{n+1}=-1$. Hence, $\text{ker }d= \{ e \}$ and $G$ is isomorphic to a subset of $\{ \pm 1 \}$.
^05f580

---
> [!lemma] Proposition 4 (Linear Maps)
> Let $A\in \text{GL}(n,\mathbb{R})$. Then, 
> 1. $\widehat{A}:\mathbb{R}^n\cup \{ \infty \}\to \mathbb{R}^n\cup \{ \infty \}$ given by $\widehat{A}|_{\mathbb{R}^n}=A$ and $\widehat{A}(\infty)=\infty$ has degree: $$\deg(\widehat{A}):=\text{sgn}(\det A)\in\{ -1,+1 \}$$

^d93efe

> [!proof]-
> We have that:
> 1. We first claim that for $A,B\in \text{GL}(n,\mathbb{R})$, if the statements hold for $A,B$ then it also does for $AB$. We have that: $$\deg(\widehat{AB})=\deg(\widehat{A} \circ \widehat{B})=\deg(\widehat{A})\deg(\widehat{B})=\text{sgn}(\det A)\cdot  \text{sgn}(\det B)=\text{sgn}(\det AB)$$
>    Now, let $A=E_{1}\dots E_{r}$ be the Gaussian elimination of $A$, i.e. $E_{1},\dots,E_{r}\in \text{GL}(n,\mathbb{R})$ are elementary matrices of the following type:
>    $$\begin{bmatrix}I_{i}\\&\lambda\\&&I_{n-i-1}\end{bmatrix},\begin{bmatrix} I_{i-1}& \\&1&&\xi \\&&I_{j-i-1}&\\&&&1 \\&&&&I_{n-j} \end{bmatrix},\begin{bmatrix} I_{i-1}& \\&&&1 \\&&I_{j-i-1}&\\&1&& \\&&&&I_{n-j} \end{bmatrix}$$where $\lambda\neq 0$ and $\xi\in \mathbb{R}$. Hence, it suffices to show that the statement holds for these elementary matrices.
>    1. For $E$ in Type 1, we have that: $\widehat{E} \sim \widehat{\begin{bmatrix}I_{i}\\&\text{sgn}(\lambda)\\&&I_{n-i-1}\end{bmatrix}}$. Further, we have that: $\det(E)=\lambda$. Therefore, we have that: $\deg(\widehat{E})=\text{sgn}(\lambda)=\text{sgn}(\det(E))$.
>    2. For $E$ in Type 2, we first define $$E_{t}:=\begin{bmatrix} I_{i-1}& \\&1&&t\xi \\&&I_{j-i-1}&\\&&&1 \\&&&&I_{n-j} \end{bmatrix}$$Then, $$F:\mathbb{R}^n\cup \{ \infty \}\times[0,1]\to \mathbb{R}^n\cup \{ \infty \},\quad (x,t)\mapsto  \widehat{E}_{t}(x)$$defines a homotopy from $\widehat{E}$ to $\text{id}$. Therefore, $\deg(\widehat{E})=\deg(\text{id})=1=\text{sgn}(1)=\text{sgn}(\det E)$.
>    3.  For $E$ in Type 3, $E$ is a reflection about some hyperplane in $\mathbb{R}^n$. By changing coordinates, we can write $E$ as $\begin{bmatrix}I\\&-1\end{bmatrix}$. Hence, $$\deg(\widehat{E})=-1=\text{sgn}(-1)=\text{sgn}(\det E)$$

^db8fdc

---
> [!lemma] Theorem 5 (Smooth Maps)
> Let $f:S^n\to S^n$ be a [[Smooth Function|smooth map]]. For $p\in S^n$, we define $$\varepsilon_{p}(f):=\text{sgn}(\det d_p(\sigma \circ f))\in\{ -1,0,+1 \}$$where $\sigma\in \text{SO}(n+1)$ s.t. $\sigma(f(p))=p$. Then,
> 1. $\varepsilon_{p}(f)$ is independent of the choice of $\sigma$.
> 2. If $q\in S^n$ is a [[Submersion|regular value]] s.t. $f^{-1}(q)=\{ p \}\subseteq S^n$, then $\deg(f)=\varepsilon_{p}(f)\in \{ -1,+1 \}$.

^f9efff

> [!proof]-
> We have that:
> 1. Let $\sigma,\sigma'$ be two such maps. Then, $$\sigma'\circ f=(\sigma'\circ \sigma ^{-1})\circ (\sigma \circ f)$$and we have: $$\det d_{p}(\sigma'\circ f)=\det (d_{p}(\sigma' \circ \sigma ^{-1})d_{p}(\sigma \circ f))=\det(\sigma'\circ \sigma ^{-1})\det(d_{p}(\sigma \circ f))=\det(d_{p}(\sigma \circ f))$$
> 2. Let $\hat{\pi}:S^n\to \mathbb{R}^n \cup \{ \infty\}$ be the homeomorphism from [[One-Point Compactification|Example 1]]. Let $\sigma_{1},\sigma_{2}\in \text{SO}(n+1)$ with $\sigma_{1}(0)=p$ and $\sigma_{2}(q)=0$. Then, let $f':= \sigma_{2} \circ f \circ \sigma_{1}$. Then, if the statement holds for $f'$, we have that: $$\deg(f)=\deg(f')=\text{sgn}(\det d_{0}( \sigma_{2} \circ  f \circ  \sigma_{1}))=\text{sgn}(\det d_{p}(\sigma_{1}\circ \sigma_{2}\circ  f))=\varepsilon_{p}(f)$$Hence, it suffices to show for the case where $p=q=0$.
>    
>    We first assume that $d_{0}f=\text{id}$. Then, by Taylor, there exists $\delta>0$ s.t. $$f(x)=x+g(x),\quad \forall \|x\|\leq\delta$$where $\left\| g(x) \right\|= o(\|x\|)$ as $\|x\|\to 0$. Now, notice that as $x\to 0$, $$\frac{\left\| g(x) \right\| }{\left\| f(x) \right\|  }=\frac{1}{\left\| \frac{x}{\left\| g(x) \right\| } +\frac{g(x)}{\left\| g(x) \right\| }\right\|  }\leq \frac{1}{\frac{\left\| x \right\| }{\left\| g(x) \right\| }-1}\to 0$$Therefore, let $0<\varepsilon<\delta / 2$ s.t. for $0\leq  \|x\|\leq2\varepsilon$ it holds that $\frac{\left\| g(x) \right\|}{\left\| f(x) \right\|}< \frac{1}{100}$. Now we define the following homology: $$F:S^n\times I\to S^n,\quad (x,t)\mapsto \begin{cases}f(x)-tg(x)&\|x\|\leq \varepsilon\\f(x)-t\left( 2-\frac{\|x\|}{\varepsilon} \right) g(x)&\varepsilon< \|x\|\leq 2\varepsilon\\f(x)&2\varepsilon< \|x\|\end{cases}$$
>    where $F$ is well-defined and continuous. Then, $F(\cdot, 0) = f$ and let $F(\cdot,1)=:f_{1}$. Now, 
>    1. **Claim 1**: For all $x\neq 0$, $f_{1}(x)\neq 0$. 
>     For all $\|x\|\leq \varepsilon$, $f_{1}(x)=f(x)-g(x)=x$. Hence, the statement holds. For $\|x\|\geq 2\varepsilon$, we have that $f_{1}(x)=f(x)$ and as $f^{-1}(0)=\{ 0 \}$, it holds. 
>     
> 	    Finally, for $\varepsilon\leq \|x\|\leq 2\varepsilon$, assume that $f_{1}(x)=0$, i.e. we have that $f(x)=\left( \frac{2\varepsilon-\|x\|}{\varepsilon} \right)g(x)$. Therefore, $$\frac{\left\| g(x) \right\| }{\left\| f(x) \right\| }=\frac{1}{2-\frac{\|x\|}{\varepsilon}}\geq \frac{1}{2}$$which is a contradiction. 
> 	2. **Claim 2**: For $r>0$ small enough, we have that $f^{-1}_{1}(\{ x \})=\{ x \}$ for all $\|x\|\leq r$
> 	   Assume otherwise. Then, there exists a sequence $r_{n}\to 0$ and $\|x_{n}\|\leq r$ and $y_{n}$ s.t. $\left\| y_{n} \right\|> \varepsilon$ s.t. $f(y_{n})=x_{n}$. (as $f_{1}(x_{n})=x_{n}$) Now, as $S^n$ is compact, there exists a subsequence $y_{n_{k}}\to y$. Therefore, we have that $$f_{1}(y)=f_{1}(\lim_{ k \to \infty } y_{n_{k}})=\lim_{ k \to \infty } f_{1}(y_{n_{k}})=\lim_{ k \to \infty } x_{n_{k}}=0$$But $y\neq 0$, which is a contradiction to Claim 1. 
> 	   
> 	Now, let $0<r<\varepsilon$ be from Claim 2. We define $K:=S^n \backslash B_{\leq r}(0)$. Then, we have that from Claim 2, $f_{1}(K)\subseteq K$. Also, $f_{1}|_{\partial K}=\text{id}|_{\partial K}$ as $\partial K\subseteq B_{\leq \varepsilon}(0)$. Therefore, we can consider $f_{1}|_{K}:(K,\partial K)\to(K,\partial K)$. 
> 	- **Claim 3:** $f_{1}|_{K}\sim \text{id}_{K}$ relative to $\partial K$.
> 	  By stereographic projection from the south pole, we can identify $K$ as $B_{\leq R}(0)$ (where $0$ is the north pole). Then, let: $$G:K\times I\to K,\quad (x,t)\mapsto tx+(1-t)f_{1}(x)$$which is a homotopy. 
> 	
> 	As $f_{1}|_{B_{\leq r}(0)}=\text{id}|_{B_{\leq r}(0)}$, we have that $f_{1}\sim \text{id}$ and $f\sim \text{id}$. Therefore, we can conclude that: $$\deg(f)=\deg(\text{id})=1=\text{sgn}(\det d_{p}f)=\varepsilon_{0}(f)$$
> 	
> 	Now, let $A:=d_{0}f$ be any not necessarily $\text{id}$. As $0$ is a regular value, we have that $A$ is injective and invertible. Then, we can consider: $$h:=\widehat{A^{-1}} \circ  f$$Then, $d_{0}h=A^{-1}A = \text{id}$. Therefore, $$1=\deg(h)=\deg(\widehat{A^{-1}})\deg(f)=\text{sgn}\left(\det(A)\right)\deg(f)=\varepsilon_{0}(f)\deg(f)$$
> 

^d81610

---
> [!lemma] Theorem 6 (Bouquet of Spheres)
> Let $Y$ be a space with a base point $y_{0}\in Y$. Further, let $E_{1},\dots,E_{k}\subseteq S^n$ be disjoint open s.t. $E_{i}\cong \mathbb{R}^n$. Let $f:S^n\to Y$ be continuous s.t. $f(S^n \backslash E_{1}\cup\dots \cup E_{k})=\{ y_{0} \}$. Then, 
> 1. $f$ factors into $h\circ g$ where $g:S^n\to S^n_{1}\lor\dots \lor S^n_{k}$ is the quotient map of the homeomorphism $S^n / (S^{n} \backslash (E_{1}\cup\dots \cup E_{k}))\to S^n_{1}\lor\dots \lor S^n_{k}$ and $h:S^n_{1}\lor\dots \lor S^n_{k}\to Y$.
> 2. Let $f_{q}:=h \circ i_{q} \circ p_{q} \circ g:S^n\to Y$. It holds that: $$f_{*}=\sum_{q=1}^{k}(f_{q})_{*}$$

^605f69

> [!proof]-
> We have that: 
> 1. Clear.
> 2. Let $\alpha\in \tilde{H}_{n}(S^n)$. Then, $$f_{*}(\alpha)=h_{*} \circ  g_{*}(\alpha)=\sum_{q=1}^{k}h_{*}\circ  (i_{q})_{*} \circ  (p_{q})_{*} \circ  g_{*}(\alpha)=\sum_{q=1}^{k}(f_{q})_{*}(\alpha)$$as $\sum_{q=1}^{k}(i_{q})_{*}\circ(p_{q})_{*}=\text{id}$. 

^76f00b

---
> [!lemma] Theorem 7 (Smooth Maps II)
> Let $f:S^n\to S^n$ be smooth and $p\in S^n$ is a regular value s.t. $f^{-1}(p)=\{ q_{1},\dots,q_{k} \}$. Then, 
> 1. $\deg(f)=\sum_{j=1}^{k}\varepsilon_{q_{j}}(f)$. 

^a38c18

> [!proof]-
> Assume $f^{-1}(p)\neq \varnothing$. Then, $d_{q_{j}}f:\text{T}_{q_{j}}S^n\to \text{T}_{p}S^n$ are surjective and isomorphisms. Therefore, by [[Local Diffeomorphism|inverse function theorem]], there exist disjoint  open neighborhoods $U_{i}\ni q_{i}$ and $V_{i}\ni p$ s.t. $f|_{U_{i}}:U_{i}\to V_{i}$ is a diffeomorphism. Wlog we may assume that $U_{1},\dots,U_{k}\cong \mathbb{R}^n$ and $V:=V_{1}=\dots=V_{k}$ (otherwise reduce $V$ to the intersection). 
> 
> Now, there exists a homotopy $F:S^n\times I\to S^n$ s.t. $F(\cdot,0)=\text{id}$ and $F(\cdot,1)=:\phi$ where: 
> 1. $\phi(V)=S^n \backslash\{ -p \}$.
> 2. $\phi(S^n \backslash V)=\{ -p \}$
> 3. $\phi(p)=p$
> 4. $\phi$ is smooth and $d_{p}\phi=\text{id}$. 
>    
> Then, $\phi \circ f \sim f$. However, also notice that $(\phi \circ f)(S^n \backslash U_{1}\cup\dots \cup U_{k})=\{ -p \}$. Therefore, $$(\phi \circ f)_{*}=\sum_{i=1}^{k}(\phi \circ  f)_{i*}$$and further, notice that $(\phi \circ f)_{i}:S^n\to S^n$ with $p\in S^n$ regular with $(\phi \circ f)_{i}^{-1}(p)=\{ q_{i} \}.$ Hence, from Theorem 5, $$\deg(f)=\deg(\phi \circ f)=\sum_{i=1}^{k}\deg((\phi \circ f)_{i*})=\sum_{i=1}^{k}\varepsilon_{q_{i}}((\phi \circ  f)_{i})$$To conclude, we have that: $$d_{q_{i}}((\phi \circ  f)_{i})=d_{q_{i}}(\phi \circ f)=d_{q_{i}}f$$Hence, $\deg(f)=\sum_{i=1}^{k}\varepsilon_{q_{i}}(f)$.

^184b4e

---
> [!lemma] Corollary 8 
> Let $f:S^n\to S^n$ be continuous. Then, $\deg(f)$ is independent of the homology theory $H$, i.e. for homology theories $H_{1},H_{2}$ with coefficients group $\mathbb{Z}$, we have that: $$\deg_{H_{1}}(f)=\deg_{H_{2}}(f)$$

^c688e8

> [!proof]-
> We have that by [[Smooth Manifold|Theorem 4]], there exists $g:S^n\to S^n$ smooth s.t. $f\sim g$. Further, by [[Submersion|Sard]], $g$ has a regular value. But by Theorem 7, $$\deg_{H_{1}}(f)=\deg_{H_{1}}(g)=\sum_{j=1}^{k}\varepsilon_{q_{j}}(f)=\deg_{H_{2}}(g)=\deg_{H_{2}}(f)$$

^471a89

---
> [!lemma] Theorem 9 (Hopf)
> Let $f,g:S^n\to S^n$, 
> 1. $f\sim g$ if and only if $\deg(f)=\deg(g)$.

^379be4

---
> [!lemma] Theorem 10 (Degree with Coefficients)
> Let $f:S^n\to S ^n$ be a continuous map and $G$ an abelian group.
> 1. For $f_{*}:\tilde{H}_{n}(S^n;G)\to \tilde{H}_{n}(S^n;G)$ is also given as $f_{*}(a)=\deg(f)\cdot a$ where $\deg(f)$ is the degree given with $\mathbb{Z}$ as coordinates.

^1b2ced

> [!proof]-
> Consider $\sigma_{n}:\Delta_{n}\to \Delta_{n} / \partial \Delta_{n}\cong S^n$ be the quotient map. Then, by [[Singular Homology|Proposition 5]], $[\sigma_{n}]$ is a generator of $H_{n}(\Delta_{n} / \partial \Delta_{n},*)\cong H_{n}(S^n, *)\cong \tilde{H}_{n}(S^n)$. 
> 
> Hence, $f\circ\sigma_{n}$ is homologous to $\deg(f)\cdot\sigma_{n}$, i.e. there exists $c=\sum_{j}^{}n_{j}\tau_{j}$ with $\tau_{j}:\Delta_{n+1}\to S^n$ s.t.: $$f\circ \sigma_{n}-\deg(f)\sigma_{n}=\partial c$$
> 
> Now, for all $g\in G$, we have that: $$f_{c}(g\sigma_{n})-\deg(f)(g\sigma_{n})=\partial (gc),\quad f_{*}[g\sigma_{n}]=\deg(f)[g\sigma_{n}]$$Hence, $f_{*}(a)=\deg(f)a$ for all $a\in \tilde{H}_{n}(S^n ; G)$.

^feb704

- **Corollary**: The recipe for [[Cellular Chain Complex|cellular homology]] also works for coefficients $G$.  ^b2f009
---
###### Borsuk-Ulam Theorem

> [!lemma] Lemma 1
> Let $\pi:X\to Y$ be a 2:1 [[Covering Space|covering]]. Let $\Theta:X\to X$ be the unique non-trivial map s.t. $\pi=\Theta \pi$.
> 1. there exists a chain map: $T:\mathcal{S}(Y;\mathbb{Z} / 2\mathbb{Z})\to \mathcal{S}(X; \mathbb{Z} / 2\mathbb{Z})$ s.t. $$T(\sigma)=\tilde{\sigma}+\Theta \circ \tilde{\sigma},\quad \forall \sigma:\Delta_{n}\to Y$$where $\tilde{\sigma}:\Delta_{n}\to X$ is a choice of lift given by [[Lift|Theorem 2.2]].
> 2. the following is a SES: $$0\to \mathcal{S}(Y;\mathbb{Z} / 2\mathbb{Z})\xrightarrow{T} \mathcal{S}(X;\mathbb{Z} / 2\mathbb{Z})\xrightarrow{\pi_{c}} \mathcal{S}(Y;\mathbb{Z} / 2\mathbb{Z})\to 0$$

^0b154f

> [!proof]-
> We have that:
> 1. We first show that $T$ is well-defined. If $\tilde{\sigma}'$ is another choice of the lift, then as $\pi$ is a 2:1 covering, $\tilde{\sigma}'=\Theta\tilde{\sigma}$. Hence, $$\tilde{\sigma}'+\Theta\tilde{\sigma}'=\Theta\tilde{\sigma}+\underbrace{ \Theta\Theta }_{ =\text{id} } \tilde{\sigma}=\tilde{\sigma}+\Theta\tilde{\sigma}$$
> 	To show that it is a chain map, we have that: $$\partial(T\sigma)=\partial\tilde{\sigma}+\partial\Theta\tilde{\sigma}=\partial\tilde{\sigma}+\Theta \partial\tilde{\sigma}=T(\partial\sigma)$$as $\pi \circ \partial\tilde{\sigma}=\partial(\pi \circ \tilde{\sigma})=\partial \sigma$.
> 2. We first show that $T$ is injective. If $T(\sigma)=\tilde{\sigma}+\Theta \tilde{\sigma}=0$ then $\tilde{\sigma}=0$ and $\sigma=0$. 
>    
>    To show that $\pi_{c}$ is surjective, let $\sigma:\Delta_{n}\to Y$. Then, $\pi_{c}(\tilde{\sigma})=\sigma$. 
>    
>    Lastly, $$\pi_{c} (T(\sigma))=\pi_{c}(\tilde{\sigma}+\Theta \tilde{\sigma})=\sigma+\sigma=0$$Hence, $\text{im } T\subseteq \text{ker }\pi_{c}$. Conversely, if $\pi_{c}(\tilde{\sigma})=0$, then either $\tilde{\sigma}=0$. If not, we have that $\pi_{c}(\tilde{\sigma})=\sigma+\Theta\sigma=T(\sigma)$. 

^54871b

---
> [!lemma] Lemma 2
> Let $\pi:X\to Y,\pi':X'\to Y'$ be two 2:1 coverings. Let $\Theta:X\to X$ and $\Theta':X'\to X'$ be the unique non-trivial maps s.t. $\pi=\Theta \pi$ and $\pi'=\Theta'\pi'$ respectively. 
> 1. Let $f:X\to X'$ s.t. $\Theta' \circ f=f\circ\Theta$, then there exists a map $\overline{f}:Y\to Y'$ s.t. $\overline{f} \circ\pi=\pi' \circ f$.
> 2. the following two SES's commute: $$\begin{CD}0@>>> \mathcal{S}(Y;\mathbb{Z} / 2\mathbb{Z})@>T>> \mathcal{S}(X;\mathbb{Z} / 2\mathbb{Z})@>\pi_{c}>> \mathcal{S}(Y;\mathbb{Z} / 2\mathbb{Z})\to 0\\&@V\overline{f}_{c}VV@Vf_{c}VV@V\overline{f}_{c}VV\\0@>>> \mathcal{S}(Y';\mathbb{Z} / 2\mathbb{Z})@>T'>> \mathcal{S}(X';\mathbb{Z} / 2\mathbb{Z})@>\pi'_{c}>> \mathcal{S}(Y';\mathbb{Z} / 2\mathbb{Z})\to 0\end{CD}$$

^f28141

> [!proof]-
> We have: 
> 1. Define $\overline{f}:Y\to Y'$ s.t. $\overline{f}(\pi(x))=\pi'(f(x))$. We show that this is well-defined. Let $\tilde{x},\tilde{x}'$ be the two choices of lift of $x$. Then, $$\pi'(f(\tilde{x}'))=\pi'(f(\Theta(\tilde{x})))=\pi'(\Theta'(f(\tilde{x})))=\pi'(f(\tilde{x}))$$
> 2. We have that: $$f_{c}(T(\sigma))=f_{c}(\tilde{\sigma}+\Theta\tilde{\sigma})=f\circ \tilde{\sigma}+\Theta' \circ  f \circ  \tilde{\sigma}=T'(\pi'(f(\tilde{\sigma})))=T'(\overline{f}_{c}(\sigma))$$

^ac52f2

---
> [!lemma] Lemma 3
If there exists a continuous function $\phi:S^n\to S^m$ that is odd, i.e. $\phi(-x)=-\phi(x)$ for all $x\in S^n$. Then, $n\leq m$

^08fde8

> [!proof]-
> Assume $n>m$ by contradiction. Assume wlog that $m>0$ as for $m=0$ the statement is clear. Using Lemma 2 on $X:= S^n$, $X':= S^m$ and $Y:= \mathbb{R}\mathbb{P}^n$ and $Y':=\mathbb{R}\mathbb{P}^m$, we have that: $$\Theta' \circ  \phi=\phi \circ  \Theta$$by assumption and we have that there exists a map $\tilde{\phi}:\mathbb{R}\mathbb{P}^n\to \mathbb{R}\mathbb{P}^m$ with $\overline{\phi} \circ \pi=\pi' \circ \phi$.
> 
> Now, consider the LES associated to $S^m$ and $\mathbb{R}\mathbb{P}^m$. We have by Lemma 1:
> 1. $T'_{*}:H_{m}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2\mathbb{Z})\to H_{m}(S^m , \mathbb{Z} / 2\mathbb{Z})$ is an isomorphism. Indeed, both maps are isomorphic to $\mathbb{Z} / 2\mathbb{Z}$ and $T'_{*}$ is injective as: 
> $$0\to H_{m}(\mathbb{R}\mathbb{P}^m, \mathbb{Z} / 2\mathbb{Z}) \xrightarrow{T'_{*}} H_{m}(S^{m}, \mathbb{Z} / 2\mathbb{Z})\xrightarrow{\pi'_{*}} H_{m}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2 \mathbb{Z})\xrightarrow{\partial_{*}} \dots$$
> 1. $\partial_{*}:H_{k}(\mathbb{R}\mathbb{P}^m; \mathbb{Z} / 2\mathbb{Z})\to H_{k-1}(\mathbb{R}\mathbb{P}^m, \mathbb{Z} / 2\mathbb{Z})$ is an isomorphism for all $1\leq k\leq m$. 
>    Indeed, $$H_{m}(\mathbb{R}\mathbb{P}^m, \mathbb{Z} / 2\mathbb{Z}) \xrightarrow{\cong} H_{m}(S^{m}, \mathbb{Z} / 2\mathbb{Z})\xrightarrow{\pi'_{*}} H_{m}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2 \mathbb{Z})\xrightarrow{\partial_{*}}  H_{m-1}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2 \mathbb{Z})\to \dots$$Here as $T'_{*}$ is an isomorphism, $\partial_{*}$ is injective and as both groups are isomorphic to $\mathbb{Z} / 2\mathbb{Z}$, $\partial_{*}$ is an isomorphism. For every $1< k< m$, $$0\cong H_{k}(S^{m}, \mathbb{Z} / 2\mathbb{Z})\xrightarrow{\pi'_{*}} H_{k}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2 \mathbb{Z})\xrightarrow{\partial_{*}}  H_{k-1}(\mathbb{R}\mathbb{P}^m , \mathbb{Z} / 2 \mathbb{Z})\to  H_{k-1}(S^m , \mathbb{Z} / 2 \mathbb{Z})\cong 0$$Hence, $\partial_{*}$ is an isomorphism. Finally, $\partial_{*}$ is also an isomorphism for $k=1$, analogously to $k=m$. 
>    
>  Now, consider the commutative diagram: $$\begin{CD}H_{k}(\mathbb{R}\mathbb{P}^n;\mathbb{Z} / 2\mathbb{Z})@>\partial_{*}>> H_{k-1}(\mathbb{R}\mathbb{P}^n ; \mathbb{Z} / 2\mathbb{Z})\\ @V\overline{\phi}_{*}VV@V\overline{\phi}_{*}VV\\ H_{k}(\mathbb{R}\mathbb{P}^m;\mathbb{Z} / 2\mathbb{Z})@>>\partial_{*}> H_{k-1}(\mathbb{R}\mathbb{P}^m ; \mathbb{Z} / 2\mathbb{Z}) \end{CD}$$If $k=1$, then as $\mathbb{R}\mathbb{P}^n, \mathbb{R}\mathbb{P}^m$ are both path-connected, any map induces an isomorphism in the zeroth homology. As $\partial_{*}$'s are isomorphisms as well, $\overline{\phi}_{i}$ is an isomorphism at degree $k$ as well. 
>  
>  Inductively, we have that $\overline{\phi}_{*}:H_{m}(\mathbb{R}\mathbb{P}^n;\mathbb{Z} / 2\mathbb{Z})\to H_{m}(\mathbb{R}\mathbb{P}^m;\mathbb{Z} / 2\mathbb{Z})$ is an isomorphism. Hence, we have that: $$\begin{CD}H_{m}(\mathbb{R}\mathbb{P}^n;\mathbb{Z} / 2\mathbb{Z})@>T_{*}>> H_{m}(S^n ; \mathbb{Z} / 2\mathbb{Z})\\ @V\overline{\phi}_{*}V\cong V@V\phi_{*}VV\\ H_{m}(\mathbb{R}\mathbb{P}^m;\mathbb{Z} / 2\mathbb{Z})@>\cong>T'_{*}> H_{m}(S^m ; \mathbb{Z} / 2\mathbb{Z}) \end{CD}$$However, this is a contradiction as $H_{m}(S^n;\mathbb{Z} / 2\mathbb{Z})\cong 0$ where $H_{m}(\mathbb{R}\mathbb{P}^m;\mathbb{Z} / 2\mathbb{Z})\cong \mathbb{Z} / 2\mathbb{Z}$. 
>    
>    

^fd0c59

---

> [!lemma] Theorem 4 (Borsuk-Ulam)
> Let $f:S^n\to \mathbb{R}^n$ be a continuous map. 
> 1. There exists $x\in S^n$ s.t. $f(x)=f(-x)$.

^b87953

> [!proof]-
> Assume that such a point doesn't exist. Then, we define: $$\phi:S^n\to S^{n-1},\quad x\mapsto \frac{f(x)-f(-x)}{\left\| f(x)-f(-x) \right\| }$$Then, $\phi$ is well-defined and $\phi(-x)=-\phi(x)$. Hence, by Lemma 3, we have that $n\leqn-1$, which is a contradiction.

^25a61e

---
##### Examples
> [!h] Example 1
> Consider $S^1\subseteq \mathbb{C}$. 
> 1. for $f:S^1\to S^1,z\mapsto z^k$, $\deg(f)=k$ for all $k\in \mathbb{Z}$.

^5ba85b

> [!proof]-
> We have that:
> 1. $f$ is a smooth map. First, $k\geq 1$. Let $\omega$ be the $k$-th root of unity. Then, $\frac{d}{dz}f(\omega)=k\omega^{k-1}$ which is regular as it is non-zero. Hence, $1$ is a regular value with $1,\omega,\dots,\omega^{k-1}$  as the preimage. As we have that $\det\frac{d}{dz}f(\omega)$ is multiplication by a complex number, its determinant is always positive. Hence, $\deg(f)=k$.
>    
>    If $k=0$, then $f$ is constant and $\deg(f)=0$.
>    
>    If $k< 0$, then $\deg(z^{-1})=-1$ as it is a reflection and we have that $\deg(z^{-k})=\deg(z^{-1})\deg(z^k)=-k$.

^460c1d

