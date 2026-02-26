#Definition #Optimization 

> [!definition]
> Let $A\in \mathbb{Z}^{m,n}$.
> 1. If $A$ has full row-rank, $A$ is ***unimodular*** if all $m\times m$ invertible submatrices of $A$ have $\det=\pm 1$.
> 2. $A$ is ***totally unimodular*** if the determinant of every square submatrix is in $\{ -1,0,1 \}$.
---
##### Properties
> [!lemma] Theorem 1
> Let $A\in \mathbb{Z}^{m,n}$. TFAE:
> 1. $A$ is totally unimodular.
> 2. $[A|I]$ is unimodular.
> 3. $\begin{bmatrix} A\\-A\\I\\-I\end{bmatrix}$ is totally unimodular 
> 4. $A^\top$ is totally unimodular.
> 5. every collection $J$ of columns or rows of $A$ can be partitioned s.t. the difference in the sum of the elements is of $\{ -1,0,1 \}$.
> 6. **(Integer Decomposition Property)** 

> [!proof]-
> We have that:
> - (1=>2): Firstly, the full row-rank is clear. Now, let $B\in {[n+m] \choose m}$ s.t. $[A|I]_{B}$ is invertible. Let $B':= B\cap [n]$. As the determinant is invariant under row swaps modulo sign, there is a block matrix $A'$ s.t. $$A'=\begin{bmatrix} C&0\\D&I_{m-\left| B' \right| }\end{bmatrix}$$and $\left| \det[A|I]_{B} \right|=\left| \det A' \right|=\left| \det C \right|$. However, $C$ is also a square submatrix of $A$ modulo row swaps. Hence, $\det([A|I]_{B})\in \{ \pm 1 \}$.
> - (2=>1): Conversely, let $k$ be the index and $I\in {[m] \choose k},J\in {[n] \choose k}$ be the row/column index sets respectively. Then, we aim to show that $\det A_{IJ}\in \{ -1,0,1 \}$. If $\det A_{IJ}=0$ we are done. Suppose $A_{IJ}$ is invertible. We construct a matrix $M$ where $$M:=[A_{J}|I_{[m] \backslash I}]$$Then, similarly as above $\left| \det A_{IJ} \right|=\left| \det M \right|\in \{ \pm 1 \}$.
> - (1=>3): Suppose $A$ is totally unimodular. Let $k\leq \min\{ 4m,n \}$ be the index and $I$ and $J$ be index sets of size $k$. Then, for $M:=\begin{bmatrix} A\\-A\\I\\-I\end{bmatrix}$, we want to show that $M_{IJ}$ has determinant in $\{ -1, 0 , 1 \}$.If $M_{IJ}$ has linearly dependent rows, the determinant is zero. Hence, with the same logic as above, it suffices to consider the case where $I\subseteq [m]$. However, then $\det M_{IJ}\in \{ -1,0,1 \}$ from the total unimodularity of $A$.
> - (3=>1): Trivial as any square submatrix in $A$ is also a square submatrix in $M$.
> - (1<=>4): Holds by the invariance of determinant under transposition.
> - (1=>5): Wlog we may assume that $J$ is a collection of columns as $A$ is TU iff $A^\top$ is TU. For a vector $f$, let $\left\lfloor f\right\rfloor$ and $\left\lceil f\right\rceil$ denote the vector with componentwise rounding. 
>   
>   Let $P:=\left\{  x\in \mathbb{R}^n : 0 \leq x \leq \mathbb{1}_{J},  \left\lfloor \frac{A\mathbb{1}_{J}}{2}\right\rfloor \leq Ax\leq  \left\lceil \frac{A\mathbb{1}_{J}}{2}\right\rceil\right\}$ be a [[polyhedron]]. Then, $P$ is non-empty and bounded, hence has a vertex $x$. From Lemma 1.3 and Theorem 2, we have that $P$ is an integral polytope and $x$ is integral, i.e. $x\in \{ 0,1 \}^n$.
>   
>   Now, consider $y:= \mathbb{1}_{J} - 2x$. Then, for $i\notin J$, $y_{i}=0$. If $i\in J$, then $y_{i}\in\{ -1,+1 \}$. Therefore, if $(A\mathbb{1}_{J})_{j}=2k$ for some $k$, $(Ax)_{j}=k$. Hence, $(Ay)_{j}=0$. Similarly, if $(A\mathbb{1}_{J})_{j}=2k+1$, then $(Ax)_{j}\in \{ k,k+1 \}$ and $(Ay)_{j}\in\{ +1,-1 \}$. This concludes the proof.
> - (5=>1): Let $B$ be a $k\times k$ invertible submatrix of $A$. Then, $r:= \det(B)$. We proceed via induction over $k$.
> 	1. if $k=1$, then it is clear as we can just take the corresponding column and we have that the sum has to be in $\{ 0,\pm 1 \}$.
> 	2. Suppose $k\geq 2$. Consider $B$ and $B^{-1}$. Then, by [[Determinant|Cramer]] as we have $B^{-1}_{ij}=[B^{-1} e_{j}]_{i}$. Hence, we have: $$B^{-1}_{ij}=\frac{\det B[i \gets  e_{j}]}{r}$$Then, by Laplace dev of determinant, $\det B[i\gets e_{j}]\in \{ -1,0,1 \}$. Let $A$ now be the $k\times k$-matrix s.t. $A_{ij}:= \det B[i\gets e_{j}]$. We have that $rB^{-1}=A$.
> 	   
> 	   We know that $A\in\{ -1,0,1 \}^{k,k}$. Now, let $J:=\{ i:A_{i 1} \ne 0 \}$. Then, $J_{1}':=\{  i : A_{i 1}=1 \}$. Then, $$(BA_{\cdot ,1})_{i}=\sum_{j\in J_{1}'}^{}B_{ij}-\sum_{j\in J \backslash J_{1}'}^{}B_{ij} = 0,\quad \forall i=2,\dots,k$$This means for $i\geq 2$, $\left| \{ j\in J: B_{ij} \neq 0 \} \right|$ is even. Let $J_{1},J_{2}$ be the partition given of $J$ s.t. the difference in the sum of the elements is in $\{ -1,0,1 \}$. Then, for $i\geq 2$, we have that the difference has to be $0$. In other words, there exists $z\in \{ -1,0,1 \}^k$ s.t. $Bz = \lambda e_{1}$ for some $\lambda\in \{ \pm 1 \}$. However, as $B$ is invertible, $$\frac{r}{\lambda}\cdot z=\frac{r}{\lambda} B^{-1}B z=A e_{1}=A_{:,1}\in\{-1, 0,1 \}^k$$Hence, $r\in \{ \pm 1 \}$.

---
> [!lemma] Theorem 2
> Let $A\in \mathbb{Z}^{m,n}$.
> 1. If $A$ has full row rank, $A$ is unimodular iff $P(b):=\{ x \in \mathbb{R}^n_{+}: Ax = b \}$ is integral for all $b\in \mathbb{Z}^m$ s.t. $P(b)\ne \varnothing$.
> 2. $A$ is totally unimodular iff $P(b):=\{ x \in \mathbb{R}^n_{+}: Ax \leq b \}$ is integral for all $b\in \mathbb{Z}^m$ s.t. $P(b)\ne \varnothing$.
> 3. if $A$ is totally unimodular then $Q(b):=\{  x\in \mathbb{R}^n : Ax \leq b \}$ is integral for all $b\in \mathbb{Z}^m$ s.t. $Q(b) \ne \varnothing$.

> [!proof]-
> We have that:
> 1. Assume $A$ is unimodular. Let $b\in \mathbb{Z}^m$ s.t. $P(b)\ne \varnothing$. Let $x^{\sharp}$ be the vertex of $P(b)$. Then, $x^{\sharp} = (x^{\sharp}_{B},0)$ for $B\in {[n] \choose m}$ where $A_{B}$ is invertible, $x^{\sharp}_{B}=A_{B}^{-1}b\geq 0$. Then, by unimodularity, $\det A_{B}\in \{ \pm 1 \}$ and by [[Determinant|Cramer]] $x^{\sharp}$ is integral.
>    
>    Conversely, if $P(b)$ is integral for all feasible $b\in \mathbb{Z}^m$, let $B\in {[n] \choose m}$ and $A_{B}$ invertible. Define $b:= A_{B}z+e_{i}$ where $z\in \mathbb{Z}^m_{+}$ s.t. $A_{B}^{-1}e_{i}+z\geq 0$. Hence, $b\in \mathbb{Z}^m$. Then, $$x^{\sharp}_{B}:= A_{B}^{-1}b=z + A_{B}^{-1}e_{i}\geq 0$$Therefore, $x^{\sharp}:= (x^{\sharp}_{B},0)$ is a vertex of $P(b)$ and therefore $x^{\sharp}\in \mathbb{Z}^n$ and $x^{\sharp}_{B}\in \mathbb{Z}^m$. It follows that $A_{B}^{-1}e_{i}\in \mathbb{Z}^m$ and $A_{B}^{-1}\in \mathbb{Z}^{m,m}$. Therefore, $\det(A^{-1}_{B})\in \mathbb{Z}$. However, as $\det(A_{B})\in \mathbb{Z}$, we have that $\det(A_{B})\in \{ \pm 1 \}$.  
> 1. As $A$ being totally unimodular is equivalent to $[A|I]$ being unimodular, by 1, it suffices to show that for any $b\in \mathbb{Z}^m$ we have that $P(b):=\{  x\in \mathbb{R}^n_{+}:Ax \leq b \}$ is nonempty and integral if and only if $P_{AI}(b):=\{ x\in \mathbb{R}^n_{+},y\in \mathbb{R}^m_{+}:Ax+y= b \}$ is nonempty and integral. This is however easy to see by considering $y$ as the slack variables.
> 2. We have from Lemma 1 that $A^\top$ is totally unimodular. Hence, $[A |-A|I | -I]$ is totally unimodular and $[A|-A]$ is totally unimodular. Then, $$Q(b)=\{ x\in \mathbb{R}^n : Ax \leq b \}=\{ x,y\in \mathbb{R}^n_{+}:Ax-Ay\leq b \}=P(b)$$This concludes the statement.

- **Remark**: $\{ x\in \mathbb{R}^{2} : 2x_{1}+2x \leq b \}$ is integral for $b\in \mathbb{Z}$ is not totally unimodular.

---
##### Examples
> [!h] Example 1 (Vertex-Edge Matrix of a Directed Graph)
> Let $G$ be a [[Graph|digraph]] and $B\in \{ -1,0,+1 \}^{|V|\times|E|}$ its vertex-edge matrix.
> 1. Then, $B$ is totally unimodular.
> 2. The integer [[Maximum Flow|max flow]] problem: $$\begin{array}{r\ll}\max &\sum_{e\in \text{out}(s)}^{}x_{e}-\sum_{e\in \text{in}(s)}^{}x_{e}\\ \text{s.t.}& \sum_{ e\in  \text{out}(v)}^{}x_{e}-\sum_{ e\in  \text{in}(v)}^{}x_{e}= 0&\forall v\in V \backslash \{ s,t \}\\&0\leq x_{e}\leq c_{e}&\forall e\in E\end{array}$$and the integral min cost max flow problem: 
>    $$\begin{array}{r\ll}\min &\sum_{e\in E}^{}\text{cost}_{e}x_{e}\\ \text{s.t.}& \sum_{ e\in  \text{out}(v)}^{}x_{e}-\sum_{ e\in  \text{in}(v)}^{}x_{e}= 0&\forall v\in V \backslash \{ s,t \}\\&\sum_{e\in \text{out}(s)}^{}x_{e}-\sum_{e\in \text{in}(s)}^{}x_{e}=f\\&0\leq x_{e}\leq c_{e}&\forall e\in E\end{array}$$
>    can be solved as LP.

> [!proof]-
> We have that:
> 3. Let $Q$ be a collection of rows. Let $Q_{1}:= Q$ and $Q_{2}:= \varnothing$. Then, $$\sum_{k\in Q_{1}}^{}B_{k,e}-\sum_{k\in Q_{2}}^{}B_{k,e}=\sum_{k\in Q_{1}}^{}B_{k,e}\in\{ -1,0,+1 \}$$Hence, $B$ is TU.
> 4. One can see from the [[Maximum Flow|LP formulations]] that the constraint matrix $A$ is totally unimodular from Lemma 1.3 and Example 1.

---
> [!h] Example 2 (Vertex-Edge Matrix of Bipartite Graphs)
> Let $G:=(V,E)$ be a [[graph]] and $A\in \{ 0,1 \}^{\left| V \right|\times \left| E \right|}$ its node-edge incidence matrix.
> 1. if $G$ is bipartite, then $A$ is totally unimodular.
> 2. The maximum weight matching problem in a bipartite graph: $$\begin{array}{rll}\max & \sum_{e\in E}^{}w_{e}x_{e}\\ \text{s.t.}&\sum_{e\in E}\mathbb{1}_{v\in e}x_{e}\leq 1&\forall v\in V\\&x_{e}\in\{ 0,1 \}&\forall e\in E\end{array}$$can be solved as LP.
> 3. The maximum weight independent set in a bipartite graph: $$\begin{array}{rll}\max& \sum_{v\in V}^{}w_{v}x_{v}\\ \text{s.t.}& x_{i}+x_{j}\leq 1&\forall \{ i,j \}\in E\\&x_{v}\in \{ 0,1 \}&\forall v\in V\end{array}$$can be solved as LP.

> [!proof]+
> We have that: 
> 1. If $G$ is bipartite, then $V:= V_{1}\sqcup V_{2}$. Now, for every collection of rows $J$ of $A$, then let $J_{1}:= J\cap V_{1}$ and $J_{2}:= J\cap V_{2}$. Then, for any edge $e\in E$, $$\sum_{j\in J_{1}} A_{je}-\sum_{j\in J_{2}} A_{je} \in \{ -1,0,1 \}$$Hence, by Lemma 1, it is TU.
> 2. From Theorem 2, the polytopes are integral.