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

> [!proof]-
> Let $\tilde{\gamma}$ be a loop at $y_{0}$ s.t. $f\circ \tilde{\gamma} \sim_{p}\varepsilon_{x_{0}}$ for $x_{0}:=f(y_{0})$. Let $h$ be its path homotopy. By [[Lift|homotopy lifting property]] there exists a lift $\tilde{h}:[0,1]\times[0,1]\to Y$ with $\tilde{h}_{0}=\tilde{\gamma}$. 
> 
> Since $f\circ\tilde{h}_{1}=h_{1}=\varepsilon_{x_{0}}$ is constant and $\varepsilon_{x_{0}}$ has $f\circ \varepsilon_{y_{0}}=\varepsilon_{x_{0}}$, by the uniqueness of the lift, we have $\tilde{h}_{1}=\varepsilon_{y_{0}}$. Further, since $f(\tilde{h}(t,0))=h(t,0)=x_{0}$ for all $t$, $\tilde{h}(t,0)=y_{0}$ for all $t$. Analogous for $\tilde{h}(t,1)$. 
> 
> Therefore, $\tilde{h}$ is a path homotopy from $\tilde{\gamma}$ to $\varepsilon_{y_{0}}$ and $\tilde{\gamma}$ is trivial in $\pi_{1}(Y,y_{0})$.
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
