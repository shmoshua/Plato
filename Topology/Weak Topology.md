#Definition #FunctionalAnalysis 

> [!definition]
> Let $V$ be a [[topological vector space]] and $V^{*}$ its [[Dual Space|dual]]. Then,
> 1. the $\sigma(V,V^{*})$***-topology*** on $V$ is the topology defined by $\{ \|\cdot\|_{\lambda} \}_{\lambda\in V^{*}}$ where for all $v\in V$:$$\|v\|_{\lambda}=\left| \lambda (v) \right| $$often called the ***weak topology***.
> 2. the $\sigma(V^{*},V)$***-topology*** on $V^{*}$ is the topology defined by $\{ \|\cdot\|_{v} \}_{v\in V}$ where for all $f\in V^{*}$:$$\|f\|_{v}=\left| f (v) \right| $$
> 	often called the ***weak\* topology***.
---
##### Properties
> [!lemma] Lemma 0
> For a finite-dimensional [[normed space]] $V$, $\sigma(V,V^{*})$ coincides with the norm topology.

> [!proof]-
> We have that for $x\in V$, $\lambda\in V^{*}$, $$N(v,\|\cdot \|_{\lambda},\varepsilon)=\{ w\in V:\left| \lambda(v)-\lambda(w) \right|<\varepsilon  \}=\lambda ^{-1}(B_{<\varepsilon}(\lambda(v)))$$Therefore, $N(v,\|\cdot\|_{\lambda},\varepsilon)$ is open w.r.t the norm topology. 
> 
> Conversely, for an open ball $B_{<\varepsilon}(x)$, we have: $$$$
---
> [!lemma] Lemma 1
> We have that:
> 1. $\{ \|\cdot\|_{v} \}_{v\in V}$ is sufficient. Therefore, $\sigma(V^{*},V)$-topology on $V^{*}$ is [[Hausdorff space|Hausdorff]]. 
> 2. If $V$ is a topological vector space defined by a sufficient family of semi-norms, $\{ \|\cdot\|_{\lambda} \}_{\lambda\in V^{*}}$ is sufficient. In which case $\sigma(V,V^{*})$-topology is Hausdorff.

> [!proof]-
> We have:
> 1. For $f\in V^{*}$, if $f\neq 0$ there exists $v\in V$ s.t. $f(v)\neq 0$. Therefore, $$\left\| f \right\| _{v}=\left| f(v) \right| \neq 0$$ 
> 2. Let $v\in V$ s.t. $v\neq 0$. Then, by [[Topological Vector Space with Seminorms|Hahn-Banach]], there exists $F\in V^{*}$ s.t. $F(v)\neq 0$. In other words, $$\|v\|_{F}=\left| F(v) \right| \neq 0$$
---
> [!lemma] Lemma 2
> Let $V$ be a topological vector space and $V^{*}$ its dual.
> 1. the $\sigma(V,V^{*})$-topology is the [[Initial Topology|initial topology]] for the family $\mathcal{F}:=\{ (f,\mathbb{K}) \}_{f\in V^{*}}$
> 2. the $\sigma(V^{*},V)$-topology is the initial topology for the family $\mathcal{G}:=\{ (J(v),\mathbb{K}) \}_{v\in V}$ where $$\begin{array}{cccc} {J(v):}&{V^{*}}&\to&{\mathbb{K}}\\&{f} &\mapsto & {f(v)} \end{array}{}$$

> [!proof]-
> We have that: 
> 1. Let $\mathcal{T}$ be the $\sigma(V,V^{*})$-topology. Let $v\in V$, $f\in V^{*}$ and $\varepsilon>0$. Then, $$\begin{align}N(v,\{\|\cdot \|_{f}\},\varepsilon)&=\{ w\in V:\|w-v\|_{f}<\varepsilon \}\\&=\{ w\in V:\left| f(w-v) \right| <\varepsilon \}\\&=\{ w\in V:\left| f(w)-f(v) \right| <\varepsilon \}\\&=f^{-1}[B_{<\varepsilon}(f(v))]\end{align}$$
>    Therefore, $f$ is continuous in the $\sigma(V,V^{*})$-topology. As $\mathcal{T_{\mathcal{F}}}$ is the smallest topology that makes $f$ continuous, $\mathcal{T}_{\mathcal{F}}\subseteq \mathcal{T}$.
>    
>    Similarly, $N(v,\{ \|\cdot\|_{f} \},\varepsilon)$ is open in $\mathcal{T}_{\mathcal{F}}$ as $f^{-1}[B_{<\varepsilon}(f(v))]\in\mathcal{O}_{1}$. Therefore, $\mathcal{T}\subseteq \mathcal{T}_{\mathcal{F}}$ and $\mathcal{T}=\mathcal{T}_{\mathcal{F}}$.
> 2. Let $\mathcal{T}$ be the $\sigma(V^{*},V)$-topology. Let $f\in V^{*}$, $v\in V$ and $\varepsilon>0$. Then, $$\begin{align}N(f,\{ \|\cdot \|_{v} \},\varepsilon)&=\{ g\in V^{*}:\|g-f\|_{v}<\varepsilon \}\\&=\{ g\in V^{*}:\left| g(v)-f(v) \right| <\varepsilon \}\\&=J(v)^{-1}[B_{<\varepsilon}(f(v))]\end{align}$$
>    Therefore, $J(v)$ is continuous in the $\sigma(V^{*},V)$-topology. As $\mathcal{T_{\mathcal{F}}}$ is the smallest topology that makes $J(v)$ continuous, $\mathcal{T}_{\mathcal{F}}\subseteq \mathcal{T}$.
>    
>    Similarly, $N(f,\{ \|\cdot\|_{v} \},\varepsilon)$ is open in $\mathcal{T}_{\mathcal{F}}$ as $J(v)^{-1}[B_{<\varepsilon}(f(v))]\in\mathcal{O}_{1}$. Therefore, $\mathcal{T}\subseteq \mathcal{T}_{\mathcal{F}}$ and $\mathcal{T}=\mathcal{T}_{\mathcal{F}}$. 
- **Corollary**: By [[Initial Topology|Lemma 2]], for a topological space $Z$, 
	1. $\psi:Z\to V$ is continuous for weak topology if and only if $f\circ\psi:Z \to \mathbb{K}$ is continuous for all $f\in V^{*}$.
	2. $\psi:Z\to V^{*}$ is continuous for weak* topology if and only if $z\mapsto \psi(z)(v)$ is continuous for all $v\in V$.
	3. A sequence $(v_{n})_{n}\subseteq V$ converges to $v$ weakly if and only if $f(v_{n})\to f(v)$ for all $f\in V^{*}$.
	4. A sequence $(f_{n})_{n}\subseteq V^{*}$ converges to $f$ weakly if  and only if $f_{n}(v)\to f(v)$ for all $v\in V$.
- **Corollary**: We have that a weakly-open set is strongly open, and a weakly closed set is strongly closed. 
---
> [!lemma] Proposition 3
> Let $T:V\to W$ be a [[Bounded Linear Map|bounded linear map]] between normed spaces $(V,\|\cdot\|_{V})$ and $(W,\|\cdot\|_{W})$ in the strong topologies. Then, 
> 1. $T$ is continuous for the weak topologies on $V,W$, i.e. for $(V,\sigma(V,V^{*}))$ and $(W,\sigma(W,W^{*}))$.
> 2. $T^{*}$ is continuous for the weak topologies on $V^{*},W^{*}$.

> [!proof]-
> We have: 
> 1. For all $f\in W^{*}$, weak topology of $W$ is defined by the inverse images of $f$. Further, as $f\circ T\in V^{*}$, $f\circ T$ is continuous in the initial topology of $V$, i.e. the weak topology. Therefore, $T$ is continuous for weak topology of $V$ and $W$.
> 
> 2. Similarly, for all $v\in V$, weak topology of $V^{*}$ is defined as by inverse images of $J(v)$. Further, as $J(v)\circ T^{*}:W^{*}\to \mathbb{K}$, $J(v)\circ T^{*}$ is continuous in the initial topology of $W^{*}$. This proves the statement.
---
> [!lemma] Proposition 4
> We have that: 
> 1. If $V$ is infinite-dimensional, $B^V_{<r}(0)$ is not weakly open. (also for $V^{*}$)
> 2. $B^V_{\leq r}(0)$ is weakly closed.
> 3.  $B^{V^{*}}_{\leq r}(0)$ is weakly\* closed.

> [!proof]-
> We have:
> 1. If $\Omega \subseteq V$ is weak-open s.t. $0\in \Omega$, then by definition there exists finite $F\subseteq V^{*}$ and $\varepsilon>0$ s.t. $$\bigcap_{f\in F}^{}\text{ker }f\subseteq N(0,F,\varepsilon)=\{ v\in V: \left| f(x) \right| <\varepsilon,\forall f\in F \}\subseteq \Omega$$However, $\bigcap_{f\in F}^{}\text{ker }f$ has a finite codimension in $V$ and if $\text{dim}V=+\infty$, then $N(0,F,\varepsilon)$ cannot be contained in $B_{<\delta}(0)$. Indeed, if there exists such $\delta>0$, for $0\neq v_{0}\in \bigcap_{f\in F}^{}\text{ker }f$, $0<\left\| v_{0} \right\|<\delta$. However, for any $n\geq 1$, $nv_{0}\in \bigcap_{f\in F}^{}\text{ker }f\subseteq B_{<\delta}(0)$, i.e. $$0<\left\| nv_{0} \right\| <\delta$$which is a contradiction.
> 2. For any $v\in V$, from Hahn-Banach $$\|v\|=\sup_{f\in B^{V^{*}}_{\leq 1}(0)}\left| f(v) \right| $$Therefore, $\|v\|\leq r$ if and only if $\left| f(v) \right|\leq r$ for all $f\in B_{\leq 1}^{V^{*}}(0)$.  We can rewrite this into: 
> 	$$B_{\leq r}^V(0)=\bigcap_{f\in B_{\leq 1}^{V^{*}}(0)}^{}\{ v\in V: \left| f(v) \right| \leq r \}$$As $f\in V^{*}$ is weakly continuous by definition, $\{ v\in V:\left| f(v) \right|\leq r \}$ is weakly closed. Therefore, $B^V_{\leq r}(0)$ is weakly closed.
> 3. For any $f\in V^{*}$, we have: $$\left\| f \right\| =\sup_{v\in B_{\leq 1}^V(0)}\left| f(v) \right| $$Therefore, similarly, we have: $$B^{V^{*}}_{\leq r}(0)=\bigcap_{v\in B^V_{\leq 1}(0)}^{}\{ f\in V^{*}:\left| f(v) \right| \leq r \}$$which is weakly\* closed.
---
> [!lemma] Theorem 5 (Banach-Alaoglu)
> For a [[normed space]] $V$, the unit closed ball $B_{\leq 1}^{V^{*}}(0)$ is weak\*-compact.

> [!proof]-
> For all $v\in V$, we define: $$D_{v}=\{ z\in \mathbb{K}:\left| z \right| \leq \|v\| \}$$
> Now consider $\prod_{v\in V}^{}D_{v}$ with product topology. From [[Tychonoff's theorem]], it is compact. We further define: $$\begin{array}{cccc} {I:}&{(B_{\leq 1}^{V^{*}}(0),\sigma(V^{*},V))}&\to&{\left( \prod_{v\in V}^{}D_{v},\mathcal{T_{\mathcal{F}}} \right)}\\&{f} &\mapsto & {(f(v))_{v\in V}} \end{array}{}$$where $\mathcal{F}:=\{ (\pi_{v},D_{v}):v\in V \}$. This is well-defined as $|f(v)|\leq\|v\|$ and $f(v)\in D_{v}$.
> 1. **$I$ is continuous w.r.t $\sigma(V^{*},V)$**: 
>    By definition, we know that $$\begin{array}{cccc} {\pi_{v}\circ I:}&{(B^{V^{*}}_{\leq 1}(0),\sigma(V^{*},V))}&\to&{(D_{v},\left| \cdot  \right| )}\\&{f} &\mapsto & {f(v)} \end{array}{}$$is continuous for all $v\in V$. Therefore, by [[Initial Topology|Lemma 2]], $I$ is continuous on the weak\*-topology.
> 1. **$I$ is [[Open and Closed Maps|open]]**: 
>    Let $f\in B_{\leq 1}^{V^{*}}(0)$, $F\subseteq V$ finite and $\varepsilon>0$. Then, $$N(f,F,\varepsilon)=\{ g\in V^{*}:|g(v)-f(v)|<\varepsilon,\forall v\in F \}$$Therefore, $$I[N(f,F,\varepsilon)]=\text{Im }I\cap\{ (z_{v})_{v\in V}:\left| z_{w}-f(w) \right|<\varepsilon,\forall w\in F  \}$$where $\{ (z_{v})_{v\in V}:\left| z_{w}-f(w) \right|<\varepsilon,\forall w\in F  \}$ is an open neighborhood of $(f(v))_{v\in V}$ in $\prod_{v\in V}^{}D_{v}$.
> 2. **$\text{Im }I\subseteq \prod_{v\in V}^{}D_{v}$ is a closed subset in the product topology**: We define for all $x,y\in V$ and $\lambda\in \mathbb{K}$, $$C_{x,y}:=\left\{  (z_{v})_{v\in V}\in \prod_{v\in V}^{}D_{v}: z_{x}+z_{y}=z_{x+y}  \right\}$$
> 	$$C_{\lambda,x}:=\left\{  (z_{v})_{v\in V}\in \prod_{v\in V}^{}D_{v}: \lambda z_{x}=z_{\lambda x}  \right\}$$which are all closed subsets of $\prod_{v\in V}^{}D_{v}$. Therefore, $$\text{Im }I=\left( \bigcap_{x,y\in V}^{}C_{x,y} \right) \cap \left( \bigcap_{\lambda\in \mathbb{K},x\in V}^{}C_{\lambda,x} \right)$$ is closed.
>
> As $I$ is a bijection by construction and both $I$ and $I^{-1}$ are continuous (as $I$ is open), $I$ is a [[homeomorphism]] between $B_{\leq 1}^{V^{*}}(0)$ and $\text{Im }I$. As $\text{Im }I$ is compact, we therefore have that $B_{\leq 1}^{V^{*}}(0)$ is compact.

- **Remark**: In general, it is not true that $B_{\leq 1}^V(0)$ is weak-compact.
---
> [!lemma] Proposition 6
> Let $(V,\|\cdot\|)$ be a $\mathbb{R}$-[[Normed Space|normed space]] and $C\subseteq V$ a [[Convex Set|convex set]]. Then, $C$ is closed if and only if $C$ is weak-closed. 

> [!proof]-
> <=: is always true.
> 
> =>: We want to show that $V \backslash C$ is weak-open. Let $x\notin C$. Then, by [[Topological Vector Space with Seminorms|the second geometric Hahn-Banach]], there exists $\alpha\in \mathbb{R}$ and $F\in V^{*}$ s.t. $$F(c)<\alpha<F(x)\quad \forall c\in C$$Then, $$x\in \{ w\in V:F(w)>\alpha \}=F^{-1}[V \backslash B_{\leq\alpha}(0)]\subseteq V\backslash C$$is a weak open set.

---
> [!lemma] Proposition 7
> Let $(V,\|\cdot\|)$ be a normed space and $C\subseteq V$ a convex set. Then, the closure $\overline{C}$ in the norm topology coincides with the closure $\overline{C}^w$ in the weak topology.

> [!proof]-
> We have that
> 1. $\overline{C}^w\supseteq \overline{C}$: As $\overline{C}^w$ is weak-closed, it is strongly closed. As $\overline{C}^w$ contains $C$, it holds that $\overline{C}^w \supseteq \overline{C}$.
> 2. $\overline{C}^w\subseteq \overline{C}$: We have that $\overline{C}$ is convex by [[Topological Vector Space with Seminorms|Lemma 10]] and closed. Therefore, from Proposition 6, it is weak-closed. Therefore, $\overline{C}^w\subseteq \overline{C}$.
---
> [!lemma] Corollary 8
> Let $(V,\|\cdot\|)$ be a normed space and $(v_{n})_{n}$ s.t. $v_{n}\to_{w}v\in V$. Then, there exists a sequence $(w_{n})_{n}\subseteq \text{co}(\{ v_{n} \}_{n})$ s.t. $w_{n}\to v$.

> [!proof]-
> By Proposition 7, we have that: $$\overline{\text{co}(\{ v_{n} \}_{n})}^w=\overline{\text{co}(\{ v_{n} \}_{n})}$$This proves the statement. 
---
