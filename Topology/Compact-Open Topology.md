#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. The ***compact-open topology*** on $C(X,Y)$ is a topology that has $$\mathcal{U}(K_{1}\dots,K_{n};U_{1},\dots,U_{n}):=\{ f\in C(X,Y):f(K_{i})\subseteq U_{i},\quad \forall i\in [n] \}$$where $K_{i}\subseteq X$ compact and $U_{i}\subseteq Y$ open as basis.
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
> [!lemma] Theorem (Arzela-Ascoli)
> Let $X$ be a [[topological space]] and $(Y,d)$ a [[metric space]]. A subset $F\subseteq C(X,Y)$ is ***relatively compact***, i.e. $\overline{F}$ is compact if
> 1. for all $x\in X$, $\overline{\{ f(x):f\in F \}}$ is compact.
> 2. $F$ is [[Equicontinuity|equicontinuous]], i.e. for every $x\in X$ and $\varepsilon>0$, there exists a neighborhood $U$ of $x$ s.t. $$d(f(x),f(y))<\varepsilon,\quad \forall f\in F,y\in U$$
> 
> where the converse holds if $X$ is [[Locally Compact Hausdorff Space|locally compact Hausdorff]].

^40ff33

> [!proof]+
> We have:
> 1. **$\mathcal{K}:=\overline{F}$ is compact in $Y^X$**:
>    Let $K_{x}:=\overline{\{ f(x) :f\in F\}}$ in $Y$. Then, $K_{x}$ is compact by assumption and is closed as $Y$ is metric. Therefore, $\prod_{x\in X}^{}K_{x}$ is compact by [[Product Topology|Tychonoff]] in $Y^X$ and is closed as $Y^X$ is Hausdorff. Then, $$F\subseteq \prod_{x\in X}^{}\{ f(x):f\in F \}\subseteq \prod_{x\in X}^{}K_{x}$$and its closure $\mathcal{K}$ is a compact subset of $\prod_{x\in X}^{}K_{x}\subseteq Y^X$.
> 2. **The [[Topology of Compact Convergence|compact-convergence topology]] coincides with the [[Topology of Pointwise and Uniform Convergence|topology of pointwise convergence]] on $K$**:
>    Let $U\subseteq C(X,Y)$ be open in $\mathcal{T}_{p}$. Then, for all $f_{0}\in U$, there exists $x_{1},\dots,x_{n}\subseteq X$ and $\varepsilon_{1},\dots,\varepsilon_{n}>0$ with $$V:=\{ f\in C(X,Y):d(f_{0}(x_{i}),f(x_{i}))<\varepsilon_{i}, \forall i\in [n] \}\subseteq U$$Then, $$\mathcal{U}\left( f_{0};\{ x_{1},\dots,x_{n} \};\min_{i\in[n]}\varepsilon_{i} \right)\subseteq V$$
>    
>    Now, let $g\in \mathcal{K}$ and $\mathcal{U}(g;K;\varepsilon)\subseteq C(X,Y)$. Then, we need an open set $U\subseteq Y^X$ with $g\in U$ s.t. $$U\cap \mathcal{K}\subseteq \mathcal{U}$$
> 
> Assume that conditions 1 and 2 hold. Then: 
> 1. 

^e1d408

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