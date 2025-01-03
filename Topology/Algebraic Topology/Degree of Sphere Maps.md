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
> Let $$f:S^n\to S^n,\quad (x_{0},x_{1},\dots,x_{n})\mapsto (-x_{0},x_{1},\dots,x_{n})$$
> 1. $\deg(f)=-1$.

> [!proof]+
> First, let $n=0$. Then, $f:\{ \pm 1 \}\to \{ \pm 1 \}$ where $f(1)=-1$ and $f(-1)=1$.
> 
> Let $i^{\pm}:\{ \pm 1 \}\hookrightarrow S^0$ be the inclusion and $\tau^{\pm}:=\varepsilon  \circ i^{\pm}$. Then, $\tau^{\pm}$ is a homotopy equivalence and $\tau^{\pm}_{*}:H_{0}(\{ \pm 1\})\to \mathbb{Z}$ is an isomorphism. Now, we show that the following commutes.$$\begin{CD}H_{0}(\{ -1 \})\oplus H_{0}(\{ 1 \})@>q>> H_{0}(S^0)\\@V\tau:=\tau^-_{*}\oplus \tau^+_{*}VV@V\varepsilon_{*}VV \\\mathbb{Z}\oplus \mathbb{Z}@>>\varphi> \mathbb{Z}\end{CD}$$where $q$ is the isomorphism given by additivity i.e. $q(x,y)=i^-_{*}(x)+ i^+_{*}(y)$ and $\varphi(a,b)=a+b$. For $(x,y)\in H_{0}(\{ -1 \})\oplus H_{0}(\{ 1 \})$, we have that: $$\varphi(\tau(x,y))=\tau^-_{*}(x)+\tau^+_{*}(y)=\varepsilon_{*}(i^-_{*}(x)+i^+_{*}(y))=\varepsilon_{*}(q(x,y))$$
> 
> 
> Now, let $X:=\{ (a,-a):a\in \mathbb{Z} \}\subseteq \mathbb{Z}\oplus \mathbb{Z}$. Then, we have that $\tau(q^{-1}(\tilde{H}_{0}(S^0)))=X$. Indeed, for $x\in \tilde{H}_{0}(S^0)$, $\varphi(\tau(q ^{-1}(x)))=\varepsilon_{*}(x)=0$ and $\tau(q^{-1}(x))\in X$. On the other hand if $x\in X$, then $0=\varphi(x)=\varepsilon_{*}(q(\tau ^{-1}(x)))$ and $q(\tau ^{-1}(x))\in\tilde{H}_{0}(S^0)$.
> 
> Hence, we get that 
> $$\begin{CD}\tilde{H}_{0}(S^0)@<<<X@<<< \mathbb{Z}\\@Vf_{*}VV@VVV@VVa\mapsto -aV\\\tilde{H}_{0}(S^0)@>>> X @>>>\mathbb{Z}\end{CD}$$and $\deg(f)=-1$.
> 
> Now, let $n\geq 1$ and assume that the statement holds for all $0\leq k<n$. Let again have:
> 1. $B^n_{+}:=\{ x\in S^n:x_{n}\geq 0 \}$
> 2. $B^n_{-}:=\{ x\in S^n:x_{n}\leq 0 \}$
> 3. $B^n_{+,\varepsilon}:=\{ x\in S^n:x_{n}\geq -\varepsilon \}$
> 4. $L_{\varepsilon}:=\{ x\in S^n:-\varepsilon\leq x\leq 0 \}$
> 
> Then, we have that:
> 1. $\tilde{H}_{n}(S^n)\cong H_{n}(S^n, B^n_{+})$ from [[Homology Theory|Example 1]].
> 2. $H_{n}(S^n,B^n_{+})\cong H_{n}(S^n,B^n_{+,\varepsilon})$ as they have the same homotopy type, from [[Homology Theory|Lemma 1.3]]
> 3. $H_{n}(S^n,B^n_{+,\varepsilon})\cong H_{n}(B^n_{-},L_{\varepsilon})$ from excision.
> 4. $H_{n}(B^n_{-},L_{\varepsilon})\cong H_{n}(B^n_{-},S^{n-1})$ again from homotopy type.
> 5. $\tilde{\partial}_{*}:H_{n}(B^n_{-},S^{n-1})\to \tilde{H}_{n-1}(S^{n-1})$ is an isomorphism as: $$0=\tilde{H}_{n}(B^n_{-})\to H_{n}(B^n_{-},S^{n-1}) \to \tilde{H}_{n-1}(S^{n-1}) \to \tilde{H}_{n-1}(B^{n}_{-})=0$$is an exact sequence and the fact that $B^n_{-}$ is contractiable.
>    
> Therefore, we have that: $$\begin{CD}\tilde{H}_{n}(S^n) @>\cong>> \tilde{H}_{n-1}(S^{n-1})\\@Vf_{*}VV @V(f|)VV\\\tilde{H}_{n}(S^n) @>\cong>> \tilde{H}_{n-1}(S^{n-1})\end{CD}$$