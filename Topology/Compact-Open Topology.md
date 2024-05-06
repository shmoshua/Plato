#Definition #Topology 

> [!definition]
> Let $X,Y$ be [[Topological Space|topological spaces]]. The ***compact-open topology*** on $C(X,Y)$ is a topology that has $$\mathcal{U}(K_{1}\dots,K_{n};U_{1},\dots,U_{n}):=\{ f\in C(X,Y):f(K_{i})\subseteq U_{i},\quad \forall i\in [n] \}$$where $K_{i}\subseteq X$ compact and $U_{i}\subseteq Y$ open as basis.
---
##### Properties
> [!lemma] Theorem (Arzela-Ascoli)
> Let $X$ be a [[topological space]] and $(Y,d)$ a [[metric space]]. A subset $F\subseteq C(X,Y)$ is ***relatively compact***, i.e. $\overline{F}$ is compact if
> 1. for all $x\in X$, $\overline{\{ f(x):f\in F \}}$ is compact.
> 2. $F$ is [[Equicontinuity|equicontinuous]], i.e. for every $x\in X$ and $\varepsilon>0$, there exists a neighborhood $U$ of $x$ s.t. $$d(f(x),f(y))<\varepsilon,\quad \forall f\in F,y\in U$$
> 
> where the converse holds if $X$ is [[Locally Compact Hausdorff Space|locally compact Hausdorff]].

^40ff33

> [!proof]+
> We have:
> 1. **$K:=\overline{F}$ is compact in $Y^X$**:
>    Let $K_{x}:=\overline{\{ f(x) :f\in F\}}$ in $Y$. Then, $K_{x}$ is compact by assumption and is closed as $Y$ is metric. Therefore, $\prod_{x\in X}^{}K_{x}$ is compact by [[Product Topology|Tychonoff]] in $Y^X$ and is closed as $Y^X$ is Hausdorff. Then, $$F\subseteq \prod_{x\in X}^{}\{ f(x):f\in F \}\subseteq \prod_{x\in X}^{}K_{x}$$and its closure $K$ is a compact subset of $\prod_{x\in X}^{}K_{x}\subseteq Y^X$.
>2. **The compact-open topology coincides with the [[Topology of Pointwise and Uniform Convergence|topology of pointwise convergence]] on $K$**:
>   

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