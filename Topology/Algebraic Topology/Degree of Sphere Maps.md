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
> First, let $n=0$. Then, $f:\{ \pm 1 \}\to \{ \pm 1 \}$ where $f(1)=-1$ and $f(-1)=1$. Then, we will show that the following is a commuting diagram$$\begin{CD}H_{0}(\{ -1 \})\oplus H_{0}(\{ 1 \})@>q>> H_{0}(S^0)\\@VVV@V\varepsilon_{*}VV \\\mathbb{Z}\oplus \mathbb{Z}@>>\varphi> \mathbb{Z}\end{CD}$$where $q$ is the isomorphism given by additivity and $\varphi(a,b)=a+b$.