#Definition #Topology 

> [!definition]
> Let $X$ be a [[topological space]]. For a topological space $Y$, a continuous map $f:Y\to X$ is a ***covering space of $X$*** if for all $x\in X$, there exists an open neighborhood $U\ni x$, a non-empty discrete space $D$ and a homeomorphism $\Phi:f^{-1}(U)\to U\times D$ s.t. $$\begin{CD}f^{-1}(U)@>\Phi>> U\times D\\@VfVV@VV\text{pr}_{1}V\\U&=&U\end{CD}$$commutes, i.e. $f=\text{pr}_{1}\circ\Phi$ on $f^{-1}(U)$. 
- **Related definition**: If $D$ is the same for all $x\in X$, $f$ is called a ***$D$-covering***. If additionally $D$ is finite, then the ***degree*** of $f$ is given as $\text{deg}(f)=\left| D \right|$.
- **Remark**: if $X,Y$ are [[Connected Space|connected spaces]], $f:Y\to X$ is a covering space only if it is a homeomorphism.
- **Related definition**: for any $x\in X$, $f^{-1}(\{ x \})$ is called the ***fiber over $x$***, if the covering map $f$ identifies with $\text{pr}_{1}:U\times D\to U$ where $U\ni x$ is given as above, i.e. $f^{-1}(\{ x \})$ is in bijection with $D$.
- **Related definition**: For $f_{1}:Y_{1}\to X$, $f_{2}:Y_{2}\to X$ covering spaces, a ***covering space morphism*** if a continuous map $\varphi:Y_{1}\to Y_{2}$ s.t. $f_{2}\circ\varphi=f_{1}$. If $\varphi$ is a homeomorphism, $\varphi$ is an ***isomorphism***.
- **Related defintion**: $f:Y\to X$ is ***trivializable*** if there exists discrete $D\neq\varnothing$ s.t. $f$ is isomorphic to $X\times D\to X$.
---
##### Properties
> [!lemma] Theorem 1
> Let $X$ be a topological space and $G$ a [[Topological Group|discrete group]] with a continuous group action $G \curvearrowright X$. 
> 1. If for all $x\in X$ there exists an open neighborhood $U\ni x$ s.t. $gU\cap U= \varnothing$ for all $g\neq e$, the projection $p:X\to X/G$ is a $G$-covering space.

> [!proof]-
> Let $\overline{x}\in X /G$ and $x\in X$ s.t. $p(x)=\overline{x}$. Let $U$ be the open neighborhood of $x$ in the assumption. Then, let $V=p(U)\subseteq X / G$. It follows that$$p ^{-1}(V)=\bigcup_{g\in G}^{}gU$$which is a disjoint union of open sets and is therefore $p ^{-1}(V)$ is open. This shows that $V$ is an open neighborhood of $\overline{x}$. Furthermore, there is a bijection: $$U\times G\to p ^{-1}(V),\quad (x,g)\mapsto gx$$which is surjective as $p ^{-1}(V)=\bigcup_{g\in G}^{}gU$, injective as it is disjoint. Moreover, it is continuous as the restriction of the group action. Therefore, it is left to show that the inverse is continuous, which is immediate as for $W\subseteq U$ open and $g\in G$, $gW$ is open. 
---
> [!lemma] Lemma 2
> Let $f:Y\to X$ be a covering space. Then, 
> 1. $f_{*}:\pi_{1}(Y,y_{0})\to \pi_{1}(X,f(y_{0}))$ is injective for all $y_{0}\in Y$.
> 2. if $X$ is connected and $f^{-1}(\{ x \})$ is finite for all $x\in X$, then there exists $d\geq 1$ s.t. for all $x\in X$ we have $f^{-1}(\{ x \})=d$.

> [!proof]-
> We have:
> 1. Let $\tilde{\gamma}$ be a loop at $y_{0}$ s.t. $f\circ \tilde{\gamma} \sim_{p}\varepsilon_{x_{0}}$ for $x_{0}:=f(y_{0})$. Let $h$ be its path homotopy. By [[Lift|homotopy lifting property]] there exists a lift $\tilde{h}:[0,1]\times[0,1]\to Y$ with $\tilde{h}_{0}=\tilde{\gamma}$. 
>    
>    Since $f\circ\tilde{h}_{1}=h_{1}=\varepsilon_{x_{0}}$ is constant and $\varepsilon_{x_{0}}$ has $f\circ \varepsilon_{y_{0}}=\varepsilon_{x_{0}}$, by the uniqueness of the lift, we have $\tilde{h}_{1}=\varepsilon_{y_{0}}$. Further, since $f(\tilde{h}(t,0))=h(t,0)=x_{0}$ for all $t$, $\tilde{h}(t,0)=y_{0}$ for all $t$. Analogous for $\tilde{h}(t,1)$. 
>    
>    Therefore, $\tilde{h}$ is a path homotopy from $\tilde{\gamma}$ to $\varepsilon_{y_{0}}$ and $\tilde{\gamma}$ is trivial in $\pi_{1}(Y,y_{0})$.
> 2. We define: $$F_{d}:=\{ x\in X:f^{-1}(\{ x \})=d \}\subseteq X$$We claim that $F_{d}$ is open. For $x\in F_{d}$, let $U\ni x$ open neighborhood s.t. $U\times D\cong f^{-1}(U)$. Then, every point in $U$ has a fiber in bijection with $D$. Therefore, $U\subseteq F_{d}$ and $F_{d}$ is open. 
>    
>    Then, one sees that $X=\bigcup_{d\geq 1}^{}F_{d}$ and we have that $F_{d}=\varnothing$ or $F_{d}=X$. As these sets are disjoint, there exists a $d\geq 1$ s.t. $F_{d}=X$. 
---
> [!lemma] Theorem 3
> Let $X$ be [[Path-Connected Space|path-connected]], locally path-connected, [[Semi-Locally Simply Connected Space|semi-locally simply connected]] and $x_{0}\in X$. Further, let $f:Y\to X$ be a [[universal cover]] of $X$ by [[Universal Cover|universal cover theorem]]. Then,
> 1. for any $G\leq \pi_{1}(X,x_{0})$, $Y / G\to X$ is a $\pi_{1}(X,x_{0}) /G$-covering.
> 2. if $g:Z\to X$ is a path-connected covering, then there exists $G\leq \pi_{1}(X,x_{0})$ s.t. $g$ is isomorphic to $Y /G\to X$ as a covering space. In this case, $G=g_{*}(\pi_{1}(Z,z_{0}))$ where $f(z_{0})=x_{0}$.
---
##### Covering Spaces and Galois Correspondence
There exists a close analogy between the two areas: 
$$\begin{array}{c|c}\text{Galois}&\text{Covering Spaces}\\ \hline K&X\\L:K&f:Y\to X\\\overline{K}\text{ algebraic closure}&f:Y\to X\text{ universal cover}\\\text{Gal}(L:K)&\pi_{1}(X,x_{0})\\H\leq \text{Gal}(L:K)\iff L^H\subseteq L&H\leq \pi_{1}(X,x_{0}) \iff f:Y/H\to X\end{array}$$

---
##### Examples
> [!h] Example 1
> We have:
> 1. $S^1\to S^1,z\mapsto z^n$ is a covering space with $D=\{ 1,\dots,n \}$.
> 2. $\mathbb{R}\to S^1,t\mapsto \exp(2\pi i t)$ is a $\mathbb{Z}$-covering space.

> [!proof]-
>  We have:
>  1. Consider $X=S^1$ and $G:=\{ z\in S^1:z^n=1 \}$ as a discrete group. Then, we acquire the continuous action: $$G\times X\to X,\quad (z,x)\mapsto zx$$Then, for any $x\in X$, we easily have $U\ni x$ with $gU\cap U=\varnothing$ for all $g\neq e$. Therefore, the projection $p:S^1\to S^1  / G$ is a covering space with degree $n$. Further, we have a homeomorphism: $$\Phi:S^1 / G\to S^1,\quad xG\mapsto x^n$$
>  2. As $\mathbb{Z}\times \mathbb{R}\to \mathbb{R},(n,x)\mapsto x+n$ is a continuous group action, we only need to verify a small condition. For $x\in X$, consider $U:=\left( x-\frac{1}{2},x+\frac{1}{2} \right)$. Then, $gU\cap U=\varnothing$ for all $g\neq e$. Hence, $p:\mathbb{R}\to \mathbb{R} / \mathbb{Z}$ is a $\mathbb{Z}$-covering space. This proves the statement.
---
> [!h] Example 2 (Symmetry Group Action)
> Consider $\mathbb{C}^n$ and $S_{n}$, the [[symmetry group]]. Consider the action: $$\sigma(x_{1},\dots,x_{n})=(x_{\sigma(1)},\dots,x_{\sigma(n)})$$Then,
> 1. $p:\mathbb{C}\to \mathbb{C}/S_{1}$ is a covering space as $p=\text{id}_{\mathbb{C}}$.
> 2. $p:\mathbb{C}^n\to \mathbb{C}^n / S_{n}$ is not a covering space for $n\geq 2$.
> 3. Let $U_{n}:=\{ (x_{1},\dots,x_{n})\in \mathbb{C}^n:x_{i}\neq x_{j}\text{ if }i\neq j \}$. Then, $\sigma \cdot U_{n}=U_{n}$ for all $\sigma\in S_{n}$, and the projection map $q:U_{n}\to U_{n} / S_{n}$ is a covering space.

> [!proof]-
> We have that:
> 1. For $n\geq 2$, assume $p$ is a covering space. As $\mathbb{C}^n$ is connected, $\mathbb{C}^n / S_{n}$ is connected as a continuous image. Further, as any element $x\in \mathbb{C}^n / S_{n}$ is a $S_{n}$-orbit and has at most $n!$ elements, hence finite. 
>    
>    However, $(0,0,\dots,0)$ has only one element in the orbit but $(1,2,0\dots,0)$ has more than 1. This is a contradiction to Lemma 2.2. Hence, $p$ is not a covering space.
> 2. $\sigma U_{n}=U_{n}$ is obvious as $\sigma$ permutes the pairwisely different elements. Then, let $x\in U_{n} / S_{n}$ and $y_{1},\dots,y_{n!}$ its $n!$ distinct preimages. As $\mathbb{C}^n$ is Hausdorff, there exists disjoint open neighborhoods $V_{i}$ of $y_{i}$ in $\mathbb{C}^n$. Therefore, $$U:=\bigcap_{i=1}^{n!}q(V_{i})$$whose image is isomorphic to $U\times [n!]$ given by the action.
---
> [!h] Example 3 (Critical Values)
> Let $f\in \mathbb{C}[X]$ be a polynomial of $\deg(f)\geq 1$. Let $Z_{f}$ denote the set of zeros of $f'$, and $C_{f}:=f(Z_{f})$ the set of critical values of $f$. 
> 1. if $\deg(f)\geq 2$, then $f$ is not a covering space. 
> 2. Let $U_{f}:=\{ z\in \mathbb{C}:f'(z)\neq 0 \}$. Then, for any $z\in U_{f}$, there exists an open neighborhood $V_{z}$ of $z$ such that $f|_{V_{z}}$ defines a homeomorphism $V_{z}\to f(V_{z})$. 
> 3. the map $f$ defines a covering space $U_{f}\to \mathbb{C} \backslash C_{f}$.

> [!proof]+
> We have:
> 1. Assume that $f$ is a covering space. Then, we claim that $f$ is unbounded. Otherwise, by Liouville's theorem, $f$ is constant, which is a contradiction as $\deg(f)\geq 2$. Therefore, $f$ is unbounded and $f^{-1}(\{ x \})$ is finite for all $x\in \mathbb{C}$. Hence, by Lemma 2.2 there exists $d\geq 1$ s.t. $f^{-1}(\{ x \})=d$ for all $x\in \mathbb{C}$.
>    
>    Let $d=\deg(f)$ and consider $f'$ with roots $\alpha_{1},\dots,\alpha_{d-1}$. Then, $\alpha_{i}$ is the root of $f-f(\alpha_{i})$ and the root of $(f-f(\alpha_{i}))'=f'$. Therefore, $f-f(\alpha_{i})$ doesn't have $d$ distinct roots and  $\left| f^{-1}(\{ f(\alpha_{i}) \}) \right|< d$. As this is finite, there exists a $\beta\in \mathbb{C}$ for which this is not the case. This shows that $f$ is not a covering space.
> 2. By the previous point, for any $z\in U_{f}$, 
>    