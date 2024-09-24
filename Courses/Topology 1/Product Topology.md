#Definition #Topology 

> [!definition]
> For any family $\{ X_{i} \}_{i\in I}$ of [[Topological Space|topological spaces]], $X:=\prod_{i\in I}^{}X_{i}$ is endowed with a ***product topology***, which is the [[Initial Topology]] of the projections $\pi_{i}:X\to X_{i}$. 
- **Remark**: By [[Initial Topology|Lemma 2]], for any topological space $Y$, a map $f:Y\to X$ is continuous if and only if $\pi_{i}\circ f:Y\to X_{i}$ is continuous for all $i\in I$.
- **Remark**: The local base for $x\in X$ is given by $\{ y\in X:y_{i}\in U_{i},\forall i\in J \}$ for $J\subseteq I$ finite and $U_{i}\subseteq X_{i}$ an open neighborhood of $x_{i}$. 
---
##### Properties
> [!lemma] Lemma 1
> For a topological space $Y$ and $f:Y\to X$, TFAE:
> 1. $f$ is continuous.
> 2. $p_{i}\circ f$ is continuous for all $i\in I$.

> [!proof]-
> [[Initial Topology|Lemma 2]]
---
> [!lemma] Theorem 2
> Let $X:=\prod_{i\in I}^{}X_{i}$. 
> 1. if $X_{i}$ is [[Hausdorff Space|Hausdorff]] for all $i\in I$, so is $X$.
> 2. if $X_{i}$ is [[Connected Space|connected]] for all $i\in I$, so is $X$.
> 3. if all $X_{i}$ are [[Locally Compact Space|locally compact]] and all except finitely many are [[Compact Space|compact]], then $X$ is locally compact.

> [!proof]-
> We have:
> 1. If $x\neq y\in X$, there exists $i\in I$ s.t. $x_{i}\neq y_{i}$ and therefore there exists $U_{i},V_{i}\subseteq X_{i}$ disjoint open neighborhoods of $x_{i},y_{i}$. Then, $U_{i}\times\prod_{j\neq i}^{}X_{j}$ and $V_{i}\times\prod_{j\neq i}^{}X_{j}$ are disjoint open neighborhoods of $x,y$.
> 2. Let $f: X\to \{ 0,1 \}$ be continuous. If $X= \varnothing$ we are done. Otherwise, let $a=(a_{i})\in X$. For any $j$ and $y\in X_{j}$, we define the injection: $$i_{j}:X_{j}\to X,\quad y\mapsto y\cdot \mathbb{1}_{j}+a\cdot \mathbb{1}_{i\neq j}$$Then, $i_{j}$ is continuous as $p_{k}\circ i_{j}=\begin{cases}\text{id}&j=k\\a_{k}&j\neq k\end{cases}$.  By Lemma 1, $f\circ i_{j}:X_{j}\to \{ 0,1 \}$ is continous and hence constant. Therefore, is equal to $f\circ i_{j}\equiv f(a)$. 
>    
>    Inductively, we have that $f(x)=f(a)$ if $x=a$ besides in finitely many coordinates. Let: $$Y:=\{ x\in X:f(x)=f(a) \}$$ we claim that $Y\subseteq X$ is dense. Let $x=(x_{i})\in X$ and $U$ an open neighborhood of $x$. Then, for $J\subseteq I$ finite and $U_{j}\subseteq X_{j}$ open neighborhood of $x_{j}$, we have: $$W:=\{ y\in X: y_{j}\in U_{j},\forall j\in J \}\subseteq U$$Then, $(y_{i})_{i}\in Y$ with $y_{j}=x_{j}$ for $j\in J$ and $y_{j}=a_{j}$ for $j\notin J$ is in $W\subseteq U$. Therefore, $Y\cap U\neq \varnothing$ and $Y$ is dense. Hence, by [[Continuous Function|Lemma 4.2]], $f=f(a)$ and $f$ is constant. 
---
![[Compact Space#^be969b]]
![[Compact Space#^478057|p]]

---
##### Examples
> [!h] Example 1
> $\mathbb{R}^n$ with the euclidean topology coincides with the product topology from $\mathbb{R}$ with the euclidean topology.
---
> [!h] Example 2
> The [[Cantor Space]] $C$ has the topology equivalent to the product topology of $\{ 0,1 \}^\infty$ with the discrete topology on each.
---
> [!h] Example 3
> For a set $A$, consider the space of all functions $\mathcal{F}(A,\mathbb{C})$. Then, the space of pointwise convergence coincides with the product topology on $\prod_{a\in A}\mathbb{C}$.
---
