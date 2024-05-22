#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. The ***compact-open topology*** on $C(X,Y)$ is a topology whose basis is composed of $$\mathcal{U}(K_{1}\dots,K_{n};U_{1},\dots,U_{n}):=\{ f\in C(X,Y):f(K_{i})\subseteq U_{i},\quad \forall i\in [n] \}$$where $K_{i}\subseteq X$ compact and $U_{i}\subseteq Y$ open.
---
##### Properties
> [!lemma] Theorem 1
> Let $X$ be a topological space and $Y$ a metric space. On $C(X,Y)$, the compact open topology coincides with the [[topology of compact convergence]].

^02c41c

> [!proof]-
> For a subset $A\subseteq Y$ and $\varepsilon>0$, let $U(A,\varepsilon)$ be the $\varepsilon$-neighborhood of $A$. If $A$ is compact and $V$ is an open set, there exists $\varepsilon>0$ s.t. $U(A,\varepsilon)\subseteq V$. 
> 
> Let $f\in\mathcal{U}(K;U)$. As $f$ is continuous, $f(K)$ is compact and we have $\varepsilon>0$ s.t. $f(K)\subseteq U$. Therefore, $$\mathcal{U}(f,K,\varepsilon)=\{ g\in C(X,Y):d(f(x),g(x))<\varepsilon,\forall x\in K \}\subseteq \mathcal{U}(K;U)$$Conversely, let $f\in C(X,Y)$ and $\mathcal{U}(f,K,\varepsilon)$. For each $x\in X$, there exists a neighborhood $V_{x}\ni x$ s.t. $f(V_{x})\subseteq B_{< \varepsilon / 4}(f(x))$. Then, $f(\overline{V_{x}})\subseteq B_{< \varepsilon / 3}(f(x))$ and let $U_{x}:=B_{<\varepsilon}(f(x))$. Cover $K$ with finitely many $V_{x}$. Then, we have $K_{i}:=\overline{V_{x_{i}}}\cap K$ and: $$\mathcal{U}(K_{1},\dots,K_{n};U_{1},\dots,U_{n})\subseteq \mathcal{U}(f,K,\varepsilon)$$

^4ac295

---
> [!lemma] Theorem 2 (Arzela-Ascoli)
> Let $X$ be a [[topological space]] and $(Y,d)$ a [[metric space]]. A subset $F\subseteq C(X,Y)$ is ***relatively compact***, i.e. $\overline{F}$ is compact, w.r.t. the compact-open topology if
> 1. for all $x\in X$, $\overline{\{ f(x):f\in F \}}$ is compact.
> 2. $F$ is [[Equicontinuity|equicontinuous]], i.e. for every $x\in X$ and $\varepsilon>0$, there exists a neighborhood $U$ of $x$ s.t. $$d(f(x),f(y))<\varepsilon,\quad \forall f\in F,y\in U$$
> 
> where the converse holds if $X$ is [[Locally Compact Hausdorff Space|locally compact Hausdorff]].

^40ff33

> [!proof]-
> Let $\mathcal{K}:=\overline{F}^{\text{p.c.}}$, i.e. the closure w.r.t. the topology of pointwise convergence. Then, 
> 1. **$\mathcal{K}$ is equicontinuous**. 
> 	   For $x\in X$ and $\varepsilon>0$, let $U$ be the open neighborhood of $x$ s.t. $$d(f(x),f(y))<\varepsilon /3, \quad \forall f\in F,y\in U$$Let $g\in \mathcal{K}$ and $y\in U$. Then, $$V:=\{ h\in Y^X:d(h(x),g(x)< \varepsilon /3), d(h(y),g(y))<\varepsilon /3 \}$$Then, $V$ is a open neighborhood of $g$ in $Y^X$. Therefore, $V\cap \mathcal{F}\neq \varnothing$ and there exists $f\in V\cap \mathcal{F}$ s.t. $$d(g(x),g(y))\leq d(g(x),f(x))+d(f(x),f(y))+d(f(y),g(y))<\varepsilon$$
> 2. **$\mathcal{K}$ is compact w.r.t. the topology of pointwise convergence**:
>    Let $K_{x}:=\overline{\{ f(x) :f\in F\}}$ in $Y$. Then, $K_{x}$ is compact by assumption and is closed as $Y$ is metric. Therefore, $\prod_{x\in X}^{}K_{x}$ is compact by [[Product Topology|Tychonoff]] in $Y^X$ and is closed as $Y^X$ is Hausdorff. Then, $$F\subseteq \prod_{x\in X}^{}\{ f(x):f\in F \}\subseteq \prod_{x\in X}^{}K_{x}$$and its closure $\mathcal{K}$ is a compact subset of $\prod_{x\in X}^{}K_{x}\subseteq Y^X$.
> 3. **The [[Topology of Compact Convergence|compact-convergence topology]] coincides with the [[Topology of Pointwise and Uniform Convergence|topology of pointwise convergence]] on $\mathcal{K}$**:
>    Let $U\subseteq C(X,Y)$ be open in $\mathcal{T}_{p}$. Then, for all $f_{0}\in U$, there exists $x_{1},\dots,x_{n}\subseteq X$ and $\varepsilon_{1},\dots,\varepsilon_{n}>0$ with $$V:=\{ f\in C(X,Y):d(f_{0}(x_{i}),f(x_{i}))<\varepsilon_{i}, \forall i\in [n] \}\subseteq U$$Then, $$\mathcal{U}\left( f_{0};\{ x_{1},\dots,x_{n} \};\min_{i\in[n]}\varepsilon_{i} \right)\subseteq V$$
>    
>    Now, let $g\in \mathcal{K}$ and $\mathcal{U}(g;K;\varepsilon)\subseteq C(X,Y)$. Then, we need an open set $U\subseteq Y^X$ with $g\in U$ s.t. $$U\cap \mathcal{K}\subseteq \mathcal{U}(g;K;\varepsilon)\cap \mathcal{K}$$As $\mathcal{K}$ is equicontinuous and $K$ compact, there exists $x_{1},\dots,x_{n}\in X$ and open sets $V_{1},..,V_{n}$ s.t. $K\subseteq \bigcup_{i}^{}V_{i}$ and: $$d(h(x),h(x_{i}))< \varepsilon /3,\quad \forall x\in V_{i}, h\in\mathcal{K}$$Let $$U:=\{ h\in Y^X:d(h(x_{i}),g(x_{i})) < \varepsilon /3, \forall i\in[n] \}$$and $h\in U\cap \mathcal{K}$. For any $x\in K$, let $V_{i}\ni x$. Then, $$d(h(x),g(x))\leq d(h(x),h(x_{i}))+d(h(x_{i}),g(x_{i}))+d(g(x_{i}),g(x))< \varepsilon$$and $h\in\mathcal{U}(g; K;\varepsilon)\cap \mathcal{K}$.
> 
> As $Y$ is metric, the topology of compact convergence coincides with the compact-open topology. Therefore, $\mathcal{K}$ is compact in compact-open topology.
> 
> Further, assume that $X$ is locally compact Hausdorff and $\mathcal{K}$ is compact. It suffices to show that $\mathcal{K}$ is equicontinuous and pointwise compact. Let $x\in X$ and consider the following map: $$\begin{array}{cccc} {}&{C(X,Y)}&\to &Y\\&{f} &\mapsto&f(x) \end{array}{}$$which is continuous. Then, $\mathcal{K}_{x}$ is the continuous image of a compact set and is compact. 
> 
> To show the equicontinuity, let $x\in X$ and $\varepsilon>0$. Let further $A\subseteq X$ be the compact neighborhood of $x$. We define: $\mathcal{K}_{A}:=\{ f|_{A}:f\in \mathcal{K} \}$ which is compact in $C(A,Y)$ as a continuous image of a compact set.  Since $A$ is compact, the compact convergence topology coincides with the uniform convergence topology. Therefore, $\mathcal{K}_{A}$ is totally bounded on $C(A,Y)$. By [[Equicontinuity|Proposition 1]], $\mathcal{F}$ is equicontinuous. Therefore, $\mathcal{K}$ is equicontinuous. 

^e1d408

---
> [!lemma] Theorem 3
> Let $X,Y,Z$ be topological spaces. Let $X$ further be locally compact.
> 1. $\text{ev}:C(X,Y)\times X\to Y, (f,x)\mapsto f(x)$ is continuous.
> 2. A map $f:X\times Z\to Y$ is continuous if and only if the map $$\widehat{f}:Z\to C(X,Y),z\mapsto (x\mapsto f(x,z))$$ is continuous.

> [!proof]+
> We have:
> 1. Let $U$ be open in $Y$ and $(f,x)\in \text{ev}^{-1}(U)$. Then, as $X$ is locally compact, let $K$ be a compact neighborhood of $x$ in $f^{-1}(U)$. Then, there exists $V\subseteq K$ open and for any $g\in S(K,U)$ and $y\in V$ we have: $g(y)\in U$. Therefore, $S(K,U)\times V$ is an open neighborhood of $(f,x)$ contained in the preimage, proving that $\text{ev}$ is open.
> 2. If $f$ is continuous, for any $S(K,U)\subseteq C(X,Y)$, let $z\in \widehat{f}^{-1}(S(K,U))$. Then, let $V\times W$ be the open neighborhood of $$
---
> [!lemma] Lemma 2
> Let $X,Y,Z$ be Hausdorff spaces and $h:Z \to X$ continuous. Then, $$h^{*}:C(X,Y)\to C(Z,Y)$$is continuous w.r.t compact-open topologies.

> [!proof]-
> For $g\in C(X,Y)$, $K\subseteq Z$ compact and $U\subseteq Y$ open, s.t. $h^{*}(g)=g \circ h\in S(K,U)$. Then, $h(K)$ is compact and $h^{*}(S(h(K),U))\subseteq S(K,U)$.
---
> [!lemma] Proposition 1
> Let $(X,d)$ be a [[metric space]]. Then, the compact-open topology on $C(X)$ is equivalent to the topology of uniform convergence on compact subsets of $X$. 
---
##### Examples
> [!h] Example 1
> If $X$ is discrete, then the compact-open topology on $C(X,Y)=Y^X$ is the product topology. 