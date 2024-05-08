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
4. As $\{ x_{0} \}\subseteq U\subseteq X$, we have an open set $V\ni x_{0}$ s.t. $V\subseteq \overline{V}\subseteq U$.