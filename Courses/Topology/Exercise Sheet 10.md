#Series #Topology 

> [!def] Problem 1
> Let $B:=\{ 1 / n:n\geq 1 \}\subseteq \mathbb{R}$. Define a topology $\mathcal{T^{*}}$ on $\mathbb{R}$ with basis $\mathcal{B}:=\mathcal{B}_{1}\cup \mathcal{B}_{2}$, where $$\mathcal{B}_{1}:=\{ (a,b):a<b,a,b\in \mathbb{R} \}$$$$\mathcal{B}_{2}:=\{ (a,b) \backslash B:a<b,a,b\in \mathbb{R} \}$$i.e., a set $U\subseteq \mathbb{R}$ is open for $\mathcal{T^{*}}$ if and only if it is an arbitrary union of sets in $\mathcal{B}$.
> 1. Show that $\mathcal{T}^{*}$ is indeed a topology, and that $\mathbb{R}$ is Hausdorff with this topology.
> 2. Let $A=\{ 0 \}$. Show that the sets $A$ and $B$ are closed in $(\mathbb{R},\mathcal{T}^{*})$.
> 
> We now suppose that $U,V$ are open sets with $0\in U$, $B\subseteq V$ and that $U\cap V=\varnothing$.
> 1. Show that there exist $a<b$ such that $a<0<b$ and $(a,b)\backslash B \subseteq U$.
> 2. Show that there exists an integer $n\geq 1$ such that $1/n\in (a,b)$.
> 3. Show that $1 / n\in V$ and that there exist $c < 1 / n < d$ such that $(c,d)\subseteq V$.
> 4. Show that there exists $x\in \mathbb{R}$ such that: $$\frac{1}{n+1}<x< \frac{1}{n}, \quad x>c$$
> 5. Show that $x\in U\cap V$.
> 6. Conclude that $(\mathbb{R},\mathcal{T^{*}})$ is not normal.

We have that: 
1. Firstly, one easily sees that $\mathbb{R}$ is open as $\bigcup_{n\geq 1}^{}(-n,n)$ and $\varnothing$ is open as an empty union. Then, it suffices to show that it is closed under finite intersection. It is clear that it is sufficient to show that every combination of intersection of two basis sets is open. We have:
	$$(a,b)\cap(c,d)=\begin{cases}(\max\{ a,c \},\min\{ b,d \})&\max\{ a,c \}<\min\{ b,d \}\\\varnothing&\text{otherwise}\end{cases}$$and as $(a,b)\backslash B=(a,b)\cap B^c$, $\mathcal{T}^{*}$ is indeed a topology. Further, as $\mathcal{B}_{1}$ is a basis for the euclidean topology, $\mathcal{T}^{*}$ is a refinement of the euclidean topology. This shows that $\mathbb{R}$ is Hausdorff w.r.t. $\mathcal{T}^{*}$.
2. For $U:=\bigcup_{n\geq 1}^{}(-n,0)\cup (0,n)$ is open. Therefore, $A=U^c$ is closed. Similarly, $$X \backslash B=\bigcup_{n\geq 1}^{}(-n,n) \backslash B$$which is open. 
3. As $U$ is an open neighborhood of $0$, there exists a basis set $W\subseteq \mathcal{B}$ s.t. $W\subseteq U$ and $0\in W$. If $W\in\mathcal{B}_{2}$we are done. Otherwise, $W\in \mathcal{B}_{1}$ and as $0\notin W$, $0\in W \backslash B\subseteq U$. This proves the statement.
4. There exists an integer $n\geq 1$ s.t. $\frac{1}{b}<n$. As $b>0$, $\frac{1}{n}<b$ and $\frac{1}{n}\in (a,b)$.
5. $1/n\in B\subseteq V$. As $V$ is open and $B\subseteq V$, $V$ is also open in euclidean topology and therefore, there exists $c<1/n<d$ s.t. $(c,d)\subseteq V$.
6. Take $\frac{1}{n}>x>\max\left\{   \frac{1}{n+1},c  \right\}$ which exists as $c <1 / n$. 
7. $x\in (c,d)\subseteq V$ and $x\in (0,1 /n)\subseteq(a,b)$. As $x\notin B$, $x\in (a,b)\backslash B\subseteq U$.
8. We have shown that $A$ and $B$ are disjoint closed, but for any open sets $U \supseteq A$ and $V\supseteq B$, $U\cap V\neq \varnothing$. Therefore, $(\mathbb{R},\mathcal{T}^{*})$ is not normal.
---
> [!def] Problem 2
> Let $X$ be a normal topological space. Let $\mathcal{F}:=C(X,[0,1])$. For $f\in \mathcal{F}$, let $X_{f}=[0,1]$ and let $$\begin{array}{cccc} {\varphi:}&{X}&\to&{\prod_{f\in \mathcal{F}}^{}X_{f}}\\&{x} &\mapsto & {(f(x))_{f\in \mathcal{F}}} \end{array}{}$$ We denote $Y=\varphi(X)$
> 1. Show that $\varphi$ is injective. 
> 2. Show that $\varphi$ is continuous when the product space has the product topology. 
> 3. Let $y=\varphi(x)$ be an element of $Y$. Show that a fundamental system of open neighborhoods of $y$ in $Y$ is given by the sets $$\{ \varphi(z):z\in X\text{ satisfies }\left| f_{j}(z)-f_{j}(x) \right| <\varepsilon_{j}, \forall j\in J \}$$where $f_{j}\in F$ for all $j\in J$, $J$ runs over finite sets and $\varepsilon_{j}$ runs over positive reals for all $j\in J$.
> 4. Let $U$ be open in $X$ and let $x_{0}\in U$. Show that there exists an open neighborhood $V$ of $x_{0}$ such that $V\subseteq \overline{V}\subseteq U$, and a function $g\in \mathcal{F}$ such that $$\{ z\in X:g(z)> 1/2 \}\subseteq U$$
> 5. Deduce that the map $\varphi:X\to Y$ is a homeomorphism. 
> 6. Deduce that $X$ is homeomorphic to a subspace of a compact space.

We have that:
1. Let $x\neq y\in X$. Then, as $X$ is normal, there exists $f\in \mathcal{F}$ s.t. $f(x)=0$ and $f(y)=1$. Therefore, $\varphi(x)\neq\varphi(y)$ and $\varphi$ is injective.
2. Let $f\in \mathcal{F}$. Then, $\pi_{f}\circ\varphi=f$ and is continuous. Therefore, $\varphi$ is continuous.
3. Let $U$ be an open neighborhood of $y$. Therefore, there exists finite $J$, $(f_{j})_{j\in J}\subseteq \mathcal{F}$ and $U_{j}\subseteq [0,1]$ open neighborhood of $f_{j}(x)$ s.t. $$\{ (f(z))_{f\in \mathcal{F}}: f_{j}(z)\subseteq U_{j}, \forall j\in J\}\subseteq U$$Therefore, there exists $\varepsilon_{j}$ s.t. $B_{j}:=(f_{j}(x)-\varepsilon_{j},f_{j}(x)+\varepsilon_{j})\subseteq U_{j}$ for all $j\in J$. This proves the statement.
4. As $\{ x_{0} \}\subseteq U\subseteq X$, we have an open set $V\ni x_{0}$ s.t. $V\subseteq \overline{V}\subseteq U$. Then, we have a continuous function $g\in \mathcal{F}$ s.t. $g|_{\overline{V}}=1$ and $g|_{X \backslash U}=0$. Then, $X\backslash U\subseteq g^{-1}([0,1 /2])$. This proves the statement.
5. $\varphi:X\to\varphi(X)$ is a continuous bijection from above. Then, for non-empty $U\subseteq X$, let $x_{0}\in U$ and for $\varphi(x_{0})\in \varphi(U)$, there exists $g\in \mathcal{F}$ s.t. $V:=\{ z\in X:g(z)> 1/2 \}\subseteq U$ and $g(x_{0})=1$. Then, $$\varphi(V)=\{ \varphi(z): z\in X, \left| g(z)-g(x_{0}) \right| < 1/2 \}$$is open and contained in $\varphi(U)$. Therefore, $\varphi ^{-1}:\varphi(X)\to X$ is continuous and $\varphi$ is a homeomorphism.
6. $X_{f}$ is compact for all $f\in \mathcal{F}$ and by Tychonoff, $\prod_{f\in \mathcal{F}}^{}X_{f}$ is compact.
---
> [!def] Problem 3
> Let $X$ be a normal space. Given a finite family $(U_{i})_{i\in[k]}$ of open subsets of $X$ whose union is $X$, a partition of unity subordinate to this covering is a finite family $(f_{i})_{i\in[k]}$ of continuous functions $f_{i}:X\to[0,1]$ s.t. we have:
> 1. $\text{supp}(f_{i})\subseteq U_{i}$ for all $i\in[k]$
> 2. we have for all $x\in X$: $\sum_{i=1}^{k}f_{i}(x)=1$.
> 
> Then, 
> 1. Show that given a finite open covering $(U_{i})_{i\in[k]}$ we can find $V_{i}\subseteq U_{i}$ open with $\overline{V_{i}}\subseteq U_{i}$ s.t. $(V_{i})_{i\in [k]}$ is a covering of $X$.
> 2. Show that there are coverings $(W_{i})_{i\in[k]}$ and $(V_{i})_{i\in [k]}$ and continuous functions $g_{i}:X\to[0,1]$ s.t. $\overline{W_{i}}\subseteq V_{i}\subseteq \overline{V_{i}}\subseteq U_{i}$, and $g_{i}|_{W_{i}}=1$ and $g_{i}|_{X \backslash V_{i}}=0$.
> 3. Show that $\text{supp}(g_{i})\subseteq U_{i}$ and that $\sum_{i=1}^{k}g_{i}(x)>0$ for all $x\in X$.
> 4. Deduce the existence of a partition of unity subordinate to $(U_{i})$.

We have:
1. We show by induction on $1\leq j\leq k$. For $j=1$, let $A_{1}:=X \backslash\bigcup_{i=2}^{k}U_{i}$. Then, $A_{1}$ is closed and $A_{1}\subseteq U_{1}$. As $X$ is normal, there exists $V_{1}\subseteq X$ open s.t. $A_{1}\subseteq V_{1}\subseteq \overline{V_{1}}\subseteq U_{1}$ and $V_{1}\cup \bigcup_{i=2}^{k}U_{i}=X$.
   
   Let now $j>1$. Then, similarly, let $A_{j}:=X \backslash \bigcup_{i\neq j}^{}U_{i}$ and there exists $V_{j}\subseteq X$ open s.t. $A_{j}\subseteq V_{j}\subseteq \overline{V_{j}}\subseteq U_{j}$. Indeed,
   $$\bigcup_{i\leq j}^{}V_{i}=V_{j}\cup\bigcup_{i\leq j-1}^{}V_{i}\supseteq A_{j}\cup X\backslash \bigcup_{i\geq j}^{}U_{i}=X\backslash \bigcup_{i>j}^{}U_{i}$$This proves the statement.
2. Repeating the process in 1 on $(V_{i})_{i\in[k]}$, we get $(W_{i})_{i\in[k]}$ s.t. $W_{i}\subseteq\overline{W_{i}}\subseteq V_{i}\subseteq \overline{V_{i}}\subseteq U_{i}$. Then, $\overline{W_{i}}$ and $X \backslash V_{i}$ are two disjoint closed sets and by normality of $X$, there exist such continuous functions $g_{i}$.
3. We have that $\text{supp}(g_{i})\subseteq \overline{V_{i}}\subseteq U_{i}$. Further, assume if there exists $x\in X$ where $\sum_{i=1}^{k}g_{i}(x)=0$, then $g_{i}(x)=0$ for all $i\in[k]$, which contradicts that $(W_{i})_{i\in[k]}$ is a covering.
4. We define: $f_{i}=g_{i}/\sum_{i=1}^{k}g_{i}$, which is well-defined, continuous and $\text{Im }f_{i}\subseteq[0,1]$. Therefore, $$\sum_{i=1}^{k}f_{i}=1$$
---
> [!def] Problem 4
> Let $X$ be a compact Hausdorff topological manifold of dimension $d\geq 1$. The goal of this exercise is to show that there exists some integer $m\geq 1$ and a compact subset $C\subseteq \mathbb{R}^m$ homeomorphic to $X$.
> 1. Show that there exist a finite covering $(U_{i})_{i\in[k]}$ of $X$ by open sets s.t. for every $i$, there is an homeomorphism $\varphi_{i}:U_{i}\to W_{i}$ where $W_{i}\subseteq \mathbb{R}^d$ is open. 
> 2. Explain why there exists a partition of unity $(f_{i})_{i\in[k]}$ subordinate to $(U_{i})$. Show that the functions $g_{i}:X\to \mathbb{R}^d$ defined by: $$g_{i}(x):=\begin{cases}f_{i}(x)\varphi_{i}(x)&x\in U_{i}\\0&x\in X\backslash \text{supp}(f_{i})\end{cases}$$ are continuous. 
> 3. Show that the map $\varphi:X\to \mathbb{R}^k\times \mathbb{R}^{dk}$ defined by $$\varphi(x):=(f_{1}(x),\dots,f_{k}(x),g_{1}(x),\dots,g_{k}(x))$$ is injective. 
> 4. Show that $\varphi$ is continuous and that it defines a homeomorphism $\varphi:X\to\varphi(X)\subseteq \mathbb{R}^{k+dk}$.

We have that:
1. for each $p\in X$, let $U_{p}\subseteq X$ be the open neighborhood of $p$ with homeomorphism $\varphi_{p}$. Then, as $X$ is compact, there exists $U_{1},\dots,U_{k}$ that covers $X$ with $\varphi_{i}:U_{i}\to W_{i}$ as corresponding homeomorphisms.
2. $X$ is compact Hausdorff and thereby normal. Therefore, there exists a partition of unity $(f_{i})_{i}$ subordinate to $(U_{i})_{i}$. To see the continuity, $g_{i}$ is continuous in $U_{i}$ by definition. Notice that $f_{i}(x)=0$ for all $x\in X \backslash \text{supp}(f_{i})$. As $\text{supp}(f_{i})\subseteq U_{i}$ and the support is closed and $U_{i}$ open, the function can be continuously extended to the whole space $X$ with zero.
3. Let $\varphi(x)=\varphi(y)$ for $x,y\$