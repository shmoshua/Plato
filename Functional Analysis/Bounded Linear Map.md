#Definition #Analysis #FunctionalAnalysis 

> [!definition]
> A [[Linear Map|linear map]] $T:V \to W$ between two [[Normed Space|normed spaces]] is ***bounded*** if $T(B)$ is [[Bounded Sets|bounded]] whenever $B \subseteq V$ is bounded. In other words,
> $$\left\| T \right\| :=\sup_{\|x\|_{V}\leq 1 }  \left\| T(x) \right\| _{W}<+\infty$$
> Then, $\mathcal{B}(V,W)$ denotes the set of all bounded linear maps $T:V \to W$. 
- **Remark**: We have for the operator norm: $$\|T\|=\sup_{\|x\|_{V}\leq 1 }  \left\| T(x) \right\| _{W}=\sup_{\|x\|_{V}= 1 }  \left\| T(x) \right\| _{W}=\sup_{x\neq 0 }  \frac{\left\| T(x) \right\| _{W}}{\|x\|_{V}}$$
- **Related Definition**: a bounded linear map $T\in \mathcal{B}(V,W)$ is an ***isometry***, if $\left\| Tv \right\|_{W}=\|v\|_{V}$ for all $v\in V$. e.g. [[Unitary Linear Map|unitary operators]].
---
##### Properties
> [!lemma] Theorem 0 (Bounded Linear Maps are Continuous)
> Let $T:V\to W$ be a linear map between normed spaces. The following are equivalent:
> 1. $T$ is [[Continuous Functions in Metric Spaces|continuous]] at $0\in V$.
> 2. $T$ is continuous.
> 3. $T$ is bounded.
> 4. $T$ is [[Lipschitz Function|Lipschitz continuous]] with Lipschitz constant $\left\| T \right\|$.

> [!proof]-
> We have that:
> - (1=>2): for all $v\in V$, $L_{v}:x\mapsto x+v$ is continuous. Therefore, $$T:=L_{T(v)}\circ T\circ L_{-v}$$As $T$ is continuous at $0$ and $L_{-v}(v)=0$, $T=L_{T(v)}\circ T\circ L_{-v}$ is continuous at $v$. 
> - (1=>3): As $T$ is continuous at $0$ and $B_{\leq 1}^W(0)$ is a neighborhood of $T(0)=0$. Therefore, there exists $B_{\leq \varepsilon}^V(0)$ s.t. $T[B_{\leq \varepsilon}^V(0)]\subseteq B^W_{\leq 1}(0)$. This shows the boundedness.
> - (3=>4): For all $x,y\in V$: $$\left\| Tx-Ty \right\| =\left\| T(x-y) \right\| \leq \left\| T \right\| \left\| x-y \right\| $$
> - (4=>1): obvious.
---
> [!lemma] Proposition 1
> If $(W,\|\cdot\|_{W})$ is a [[Banach Space|Banach space]], then $(\mathcal{B}(V,W),\|\cdot\|)$ is a Banach space.

>[!proof]-
>Let $(A_{n})_{n\ge 1}$ be a Cauchy sequence in $\mathcal{B}(V,W)$. For all $x\in V$, $$\left\| A_{n} (x)-A_{m}(x)\right\| \leq \left\| A_{n}-A_{m} \right\|\cdot \|x\|_{V} $$Therefore, $(A_{n}(x))_{n\ge 1}$ is a Cauchy sequence in $W$. Let $A(x):=\lim_{ n \to \infty }A_{n}(x)$. 
>1. **$A$ is linear**: easy to see. 
>2. **$A$ is bounded**: As $|\left\| A_{n} \right\| -\left\| A_{m} \right\| |\leq \left\| A_{n}-A_{m} \right\|$ we have that $\lim_{ n \to \infty }\left\| A_{n} \right\|$ exists. Therefore, $$\left\| A(x) \right\| \leq \left( \lim_{ n \to \infty } \left\| A_{n} \right\|  \right) \|x\|$$which implies that $A$ is bounded. 
>3. **$A_{n}$ converges to $A$ in norm**: as: $$\left\| A(x)-A_{n}(x) \right\| =\lim_{ \ell \to \infty } \left\| A_{\ell}(x)-A_{n}(x) \right\| \leq \limsup_{ \ell \to \infty } \left\| A_{\ell}-A_{n} \right\| \|x\|$$we have, $$\left\| A-A_{n} \right\|\leq \limsup_{ \ell \to \infty } \left\| A_{\ell}-A_{n} \right\|  $$Then, $$\limsup_{ n \to \infty } \left\| A-A_{n} \right\| \leq \limsup_{ n \to \infty } \limsup_{ \ell \to \infty }\left\| A_{\ell}-A_{n} \right\| =0$$therefore, $$\lim_{ n \to \infty } \left\| A-A_{n} \right\| =0$$as norms are non-negative.

---
> [!lemma] Proposition 2
> A linear map $T:V \to W$ is bounded if $V$ is finite-dimensional.

> [!proof]-
> Let us define another norm for $V$:$$\|v\|:=\|v\|_{V}+\left\| T(v) \right\| _{W}$$Then, from the [[Equivalence of Norms|equivalence of norms]] in finite dimensions, there exists $c>0$ s.t. $$\|v\|_{V}+\left\| T(v) \right\| _{W}=\|v\|\leq c\|v\|_{V}$$Therefore, for all $v\in V$:$$\left\| T(v) \right\| _{W}\leq (c-1)\|v\|_{V}$$In particular, we have that $c-1\geq 0$. This shows that $\left\| T \right\|$ is bounded.
---
> [!lemma] Corollary 3 (from Hahn-Banach)
> Let $(V,\|\cdot\|)$ be a [[Analysis/Normed Space|normed $\mathbb{K}$-vector space]] and $M \subseteq V$ a $\mathbb{K}$-vector subspace. For $f\in \mathcal{B}(M,\mathbb{K})$, there exists $F\in \mathcal{B}(V,\mathbb{K})$ s.t.
> 1. $\left. F \right|_{M}=f$ and 
> 2. $\left\| F \right\|=\left\| f \right\|$.

> [!proof]-
> By hypothesis, we have $|f(v)|\leq \left\| f \right\|\|v\|$ for all $v\in M$. Let $p:V \to [0,+\infty)$ be defined by: $$p(v)=\left\| f \right\| \|v\|$$Then, with [[Seminorm|Hahn-Banach]], we get a $\mathbb{K}$-linear form $F:V \to \mathbb{K}$ with $\left. F \right|_{M}=f$ and $$\left| F(v) \right| \leq p(v)=\left\| f \right\| \|v\|,\quad\forall v\in V$$This means, 
> $$\left\| f \right\| =\sup_{\|v\|\leq 1,v\in M}|f(v)|=\sup_{\|v\|\leq 1,v\in M}|F(v)|\leq\sup_{\|v\|\leq 1,v\in V}|F(v)|=\left\| F \right\| \leq \left\| f \right\| $$
> Therefore, $\left\| F \right\|=\left\| f \right\|$.
---
> [!lemma] Proposition 4 
> Let $T:V\to W$ be a linear map between normed vector spaces, where $W$ is finite-dimensional. Then, $T$ is continuous if and only if $\text{ker }T$ is closed.

> [!proof]-
> =>: If $T$ is continuous, as $\{ 0 \}$ is closed, $\text{ker }T=T^{-1}[\{ 0 \}]$ is closed.
> 
> <=: If $\text{ker }T$ is closed, $V /\text{ker }T$ is a normed vector space and we can define: $$\begin{array}{cccc} {\overline{T}:}&{V / \text{ker }T}&\to&{W}\\&{x+\text{ker }T} &\mapsto & {Tx} \end{array}{}$$As $V/\text{ker }T$ is isomorphic to a subspace of $W$, $\overline{T}$ is bounded by Proposition 2 and $T=\overline{T}\circ\pi$ is continuous as a composition of two continuous functions.  
---
> [!lemma] Theorem 4 (Banach-Steinhaus)
> Let $(V,\|\cdot\|_{V})$ be a [[Banach space]], $(W,\|\cdot\|_{W})$ a [[normed space]] and for $\lambda\in \Lambda$, $T_{\lambda}\in \mathcal{B}(V,W)$ s.t. $$\sup_{\lambda\in \Lambda}\|T_{\lambda}(v)\|_{W}<+\infty$$for all $v\in V$. Then, $$\sup_{\lambda\in\Lambda}\left\|T_{\lambda}  \right\|<+\infty $$

> [!proof]-
> Let $f_{\lambda}:V \to \mathbb{R}_{\geq 0}$ defined as $f_{\lambda}(v)=\left\| T_{\lambda}(v) \right\|_{W}$. Then, by [[Complete Metric Space|Principle of Uniform Boundedness]], there exists $w\in V$, $r>0$ and $c>0$ s.t. $$f_{\lambda}(v)\leq c$$for all $v\in B(w,r)$ and $\lambda\in \Lambda$. By setting $v=w+u$ with $u\in B(0,r)$, 
> $$\left\| T_{\lambda}(u) \right\|-\left\| T_{\lambda}(w) \right\| \leq \left\| T_{\lambda}(w)+T_{\lambda}(u) \right\|=\left\| T_{\lambda}(w+u) \right\| \leq c  $$and $$\left\| T_{\lambda} \right\| =\sup_{\|u\| <1}\left\| T_{\lambda}(u) \right\| =\sup_{\|u\|< r} \frac{\left\| T_{\lambda}(u) \right\| }{r}\leq  \frac{1}{r}(c+\left\|  T_{\lambda}(w)\right\|)\leq \frac{2c}{r} $$for all $\lambda\in \Lambda$.
- **Remark**: If $V$ is not Banach, this does not hold. Consider $$V:=\{ x:\mathbb{N}\to \mathbb{\mathbb{R}^+}|\sup_{k\geq 0}k x_{k} <+\infty \}$$and $T_{\lambda}:V\to \mathbb{R}, T_{\lambda}(x)=\lambda x_{\lambda}$  for all $\lambda\in \mathbb{N}$. Then, 
	1. $\sup_{\lambda\in \mathbb{N}}\left| \lambda x_{\lambda} \right|=\sup_{\lambda\in \mathbb{N}}\lambda x_{\lambda} <+\infty$ for all $x\in V$ but
	2. $\sup_{\lambda\in \mathbb{N}}\left\| T_{\lambda} \right\|=\sup_{\lambda\in \mathbb{N}}\lambda$.
---
> [!lemma] Corollary 5
> Let $(T_{n})_{n}\subseteq \mathcal{B}(V,W)$ where $V$ is a [[Banach space]]. Assume that there exists $T$ s.t. for all $x\in X$:$$T(x)=\lim_{ n \to \infty } T_{n}(x)$$Then, 
> 1. $\sup_{n\geq 1}\left\| T_{n} \right\|<+\infty$
> 2. $T\in \mathcal{B}(V,W)$
> 3. $\left\| T \right\|\leq \liminf_{ n \to \infty }\left\| T_{n} \right\|$

> [!proof]-
> We have that: 
> 1. Since $(T_{n}(x))_{n}$ converges for all $x\in V$, $(T_{n}(x))_{n}$ is bounded and $$\sup_{n\geq 1}\left\| T_{n}(x) \right\| <+\infty$$for all $x\in X$ and using Banach-Steinhaus, $$\sup_{n\geq 1}\left\| T_{n} \right\| <+\infty$$
> 2. We easily see that $T$ is linear. Now, let $K:=\liminf_{ n \to \infty }\left\| T_{n} \right\|$. Then, there exists a subsequence $(n_{k})_{k}$ s.t. $K=\lim_{ k \to \infty }\left\| T_{n_{k}} \right\|$. 
> 	
> 	As this is a subsequence, we have that for all $x\in X$: $T(x)=\lim_{ k \to \infty }T_{n_{k}}(x)$. Therefore, $$\left\| T(x) \right\| =\lim_{ k \to \infty } \left\| T_{n_{k}}(x) \right\| \leq \|x\|\lim_{ k \to \infty } \left\| T_{n_{k}} \right\| =K\|x\| $$Therefore, $\|T\|\le K$ and $T$ is bounded.
> 3. From 2.

- **Remark**: This does not mean that $\left\| T_{n}-T \right\|\to0$. 
  Counterexample: Let $$\begin{array}{cccc} {T_{n}:}&{\ell^{2}(\mathbb{N})}&\to&{\ell^{2}(\mathbb{N})}\\&{x=\sum_{k=0}^{\infty}x_{k}\delta_{k}} &\mapsto & {x_{n}\delta_{n}} \end{array}{}$$i.e. the projection on $\delta_{n}$. As $\sum_{n=0}^{\infty}\left| x_{n} \right|^{2}<\infty$, we have that $\lim_{ n \to \infty }\left| x_{n} \right|=0$ and $$\left\| T_{n}(x) \right\| =\left\| x_{n}\delta_{n} \right\| =|x_{n}|\to 0$$for all $x\in \ell^{2}(\mathbb{N})$. So $T_{n}(x)\to 0$. However, $\left\| T_{n} \right\|=1$.
---
> [!lemma] Theorem 6 (Open Mapping Theorem)
> Let $V,W$ be [[Banach Space|Banach spaces]] and $T\in \mathcal{B}(V,W)$ a surjective map. Then, there exists $c>0$ s.t. $$B_{<c}(0)\subseteq T(B_{<1}(0))$$
> In particular, $T$ is [[Open and Closed Maps|open]].

>[!proof]-
>We have that:
>1. **Showing there exists $\varepsilon>0$ with $B_{<\varepsilon}(0)\subseteq  \overline{T(B_{<1}(0))}$**:
>	Since $T$ is surjective, for all $w\in W$, there exists $n\geq 1$ s.t. $$w\in T(B_{<n}(0))\subseteq  \overline{T(B_{<n}(0))}$$and $W=\bigcup_{n\geq 1}^{}\overline{T(B_{<n}(0))}$. By [[Complete Metric Space|Baire Category Theorem]], there exists $n_{0}\geq 1$ s.t. $\overline{T(B_{<n_{0}}(0))}^\circ\neq \varnothing$. Therefore,   $\overline{T(B_{<1}(0))}^\circ\neq \varnothing$. 
>	
>	Let $x\in W$ and $\varepsilon>0$ s.t. $B_{<2\varepsilon}(x)\subseteq \overline{T(B_{<1}(0))}$. Then, $$\begin{align}\overline{T(B_{<1}(0))}+\overline{T(B_{<1}(0))}&=\overline{T(B_{<1}(0))}-\overline{T(B_{<1}(0))}\\&\supseteq B_{<2\varepsilon}(x)-B_{<2\varepsilon}(x)\\&=B_{<2\varepsilon}(x)+B_{<2\varepsilon}(-x)\\&\supseteq B_{<2\varepsilon}(0)\end{align}$$
>	
>	Next, observe that if $(v_{n})_{n},(w_{n})_{n}\subseteq B_{<1}^V(0)$ s.t. $T(v_{n})$ and $T(w_{n})$ converge, then: $$T(v_{n}+w_{n})=T(v_{n})+T(w_{n})$$converges and $(v_{n}+w_{n})_{n}\subseteq B_{<2}(0)$. This implies that: $$\overline{T(B_{<1}(0))}+\overline{T(B_{<1}(0))}\subseteq\overline{T(B_{<2}(0))}$$Therefore, $B_{<2\varepsilon}(0)\subseteq \overline{T(B_{<2}(0))}$ and $$B_{<\varepsilon}(0)\subseteq \overline{T(B_{<1}(0))}$$
>2.  **Showing there exists $c>0$ with $B_{<c}(0)\subseteq  T(B_{<1}(0))$**:
> 	Let $c=\varepsilon/2$ and $y\in B_{<c}^W(0)\subseteq \overline{T(B_{< 1/2}(0))}$. We will now iteratively find a sequence $(z_{n})_{n}\subseteq V$ where:
> 	1. $z_{1}\in B^V_{<1 / 2}(0)$ with $\left\| y-T(z_{1}) \right\|_{W}<c / 2$
> 	2. $z_{2}\in B^V_{<1 / 4}(0)$ with $\left\| y-T(z_{1})-T(z_{2}) \right\|_{W}<c / 4$
> 	3. $z_{n}\in B_{< 1 / 2^n}^V(0)$ s.t. $\left\| y-\sum_{i=1}^{n}T(z_{i}) \right\|_{W}=\left\| y-T\left( \sum_{i=1}^{n}z_{i} \right) \right\|_{W}< c /2^n$
> 	
> 	Further, notice that $\left( \sum_{i=1}^{n}z_{i} \right)_{n}$ is a Cauchy sequence, as for $n\geq m\geq N$: $$\left\| \sum_{i=1}^{n}z_{i}-\sum_{i=1}^{m}z_{i} \right\| \leq \sum_{i=m+1}^{n}\|z_{i}\|\le \sum_{i=m+1}^{n} \frac{1}{2^i}\leq \frac{1}{2^m}\leq \frac{1}{2^N}$$Therefore, $\sum_{i=1}^{n}z_{i} \to x$ in $V$ and since $\left\| y-T\left( \sum_{i=1}^{n}z_{i} \right) \right\|< \frac{c}{2^n}$, we get that $y=T(x)$. However, $$\|x\|\le \sum_{i=1}^{\infty}\left\| z_{i} \right\| < \sum_{i=1}^{\infty} \frac{1}{2^i}= 1$$It follows that $B_{<c}(0)\subseteq T(B_{<1}(0))$.
> 3. **Showing $T$ is open**:
>    Let $U\subseteq V$ be an open set. Then, for any $v\in U$, there exists $\varepsilon>0$ s.t. $B_{<\varepsilon}(v)\subseteq U$.  Then,$$B_{<c\varepsilon }(T(v))=T(v)+B_{<c \varepsilon}(0)\subseteq T(v)+T(B_{<\varepsilon}(0))=T(B_{<\varepsilon}(v))\subseteq T(U)$$Therefore, $T(U)$ is open.
- **Corollary**: Let $V,W$ be Banach spaces and if $T\in \mathcal{B}(V,W)$ bijective, then, $T^{-1}\in \mathcal{B}(W,V)$ as $(T^{-1})^{-1}(U)=T(U)$ for any open $U\subseteq V$.
---
> [!lemma] Theorem 7 (Closed Graph Theorem)
> Let $V,W$ be Banach spaces and $T:V\to W$ linear. Then, the following are equivalent:
> 1. $T\in \mathcal{B}(V,W)$ 
> 2. $\text{graph}(T)\subseteq V\times W$ is closed.
> 3. If $x_{n}\to 0$ is $V$ and $Tx_{n}\to y$ in $V$, then $y=0$.

> [!proof]+
> We have:
> 1. (1=>2): Holds since $W$ is [[Hausdorff Space|Hausdorff]]. Let $(x,y)\in V\times W \backslash\text{graph}(T)$. Then, $y$ and $Tx$ are disjoint and there exists $U_{1}\ni y$ and $U_{2}\ni Tx$ disjoint. 
> 
> 1. First, we define a norm in $V\times W$ as: $$\left\| (v,w) \right\| =\|v\|_{V}+\|w\|_{W}$$
> Then, $V\times W$ is a Banach space and as $\text{graph}(T)$ is closed and also is a linear subspace, it is also a Banach space.
> 
> Let $P_{V}:V\times W \to V$ and $P_{W}:V\times W\to W$ be projections. Then,
> 1. $P_{V}|_{\text{graph}(T)}:\text{graph}(T)\to V$ is bijective and hence, $(P _{V}|_{\text{graph}(T)})^{-1}$ is continuous from bounded inverse theorem.
> 
> Therefore, $$P_{W}\circ (P _{V}|_{\text{graph}(T)})^{-1}=T$$is continuous and bounded.
> 
> 2=>3: $(x_{n},T(x_{n}))\to(0,y)$. However, as the graph is closed, $y=T(0)=0$.
> 3=>2: Let $(x_{n},T(x_{n}))\to(x,y)$. Then, $x_{n}-x\to 0$ and $T(x_{n}-x)=T(x_{n})-T(x)\to y-T(x)$. Therefore, $T(x)=y$ and the graph is closed.

- **Remark**: The converse holds since $W$ is [[Hausdorff space|Hausdorff]].
- **Remark**: $f(x)=\begin{cases}1/x&x\neq 0\\0&x=0\end{cases}$   has a closed graph but is not continuous.
- **Remark**: If $V$ is not Banach, the theorem does not hold. 
  Example: The map: $$\begin{array}{cccc} {L:}&{C^1([0,1])}&\to&{C^0([0,1])}\\&{f} &\mapsto & {f'} \end{array}{}$$is not bounded (consider oscillations with small amplitude but has high frequency). However, the graph is closed.
---
> [!lemma] Theorem 8 (BLT Theorem)
>  Let $(B_{1},\|\cdot\|_{1}),(B_{2},\|\cdot\|_{2})$ be [[Banach Space|Banach spaces]], $D\subseteq B_{1}$ a vector subspace and $T\in \mathcal{B}(D,B_{2})$. Then, $T$ extends uniquely to a bounded linear operator $T_{\text{ext}}:\overline{D}\to B_{2}$. 
> 
>  If in addition $\left\| T(v) \right\|_{2}=\|v\|_{1}$ for all $v\in D$, then the same holds for $T_{\text{ext}}$.

> [!proof]-
> Let $v\in \overline{D}$. Then, there exists $(v_{n})_{n}\subseteq D$ s.t. $v_{n}\to v$. We then define: $$T_{\text{ext}}(v)=\lim_{ n \to \infty } Tv_{n}$$
> Notice that: $$\left\| Tv_{n}-Tv_{m} \right\|_{2}\leq\|T\|\cdot \|v_{n}-v_{m}\|_{1} $$Therefore, $(Tv_{n})_{n}$ is a Cauchy sequence, which converges. 
>  
> Now let $(w_{n})_{n}$ be another sequence s.t. $w_{n}\to v$. Then, $$\left\| \lim_{ n \to \infty }Tv_{n}-\lim_{ n \to \infty } Tw_{n}  \right\|\leq \left\| T \right\| \lim_{ n \to \infty } \left\| v_{n}-w_{n} \right\| =0 $$Therefore, $T_{\text{ext}}(v)$ does not depend on the sequence chosen.
> 
> We now show the uniqueness of $T_{\text{ext}}$. If $T'$ is another bounded linear extension, then: $$T'(v)=T'(\lim_{ n \to \infty } v_{n })=\lim_{ n \to \infty } T'v_{n}=\lim_{ n \to \infty } Tv_{n}=T_{\text{ext}}(v)$$
> 
> Lastly, assume that $\left\| Tv \right\|_{2}=\|v\|_{1}$ for all $v\in D$. Then: $$\left\| T_{\text{ext}}(v) \right\|_{2} =\left\| \lim_{ n \to \infty } Tv_{n} \right\|_{2} =\lim_{ n \to \infty } \left\| Tv_{n} \right\|_{2} =\lim_{ n \to \infty } \left\| v_{n} \right\|_{1}=\|v\|_{1} $$