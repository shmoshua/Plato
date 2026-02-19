#Definition #Optimization 

> [!definition]
> Let $A\in \mathbb{Z}^{m,n}$.
> 1. If $A$ has full row-rank, $A$ is ***unimodular*** if all $m\times m$ invertible submatrices of $A$ have $\det=\pm 1$.
> 2. $A$ is ***totally unimodular*** if the determinant of every square submatrix is in $\{ -1,0,1 \}$.
---
##### Properties
> [!lemma] Lemma 1
> Let $A\in \mathbb{Z}^{m,n}$. TFAE:
> 1. $A$ is totally unimodular.
> 2. $[A|I]$ is unimodular.
> 3. $\begin{bmatrix} A\\-A\\I\\-I\end{bmatrix}$ is totally unimodular 
> 4. $A^\top$ is totally unimodular.
> 5. every collection $J$ of columns or rows of $A$ can be partitioned s.t. the difference in the sum of the elements is of $\{ -1,0,1 \}$.

> [!proof]+
> We have that:
> - (1=>2): Firstly, the full row-rank is clear. Now, let $B\in {[n+m] \choose m}$ s.t. $[A|I]_{B}$ is invertible. Let $B':= B\cap [n]$. As the determinant is invariant under row swaps modulo sign, there is a block matrix $A'$ s.t. $$A'=\begin{bmatrix} C&0\\D&I_{m-\left| B' \right| }\end{bmatrix}$$and $\left| \det[A|I]_{B} \right|=\left| \det A' \right|=\left| \det C \right|$. However, $C$ is also a square submatrix of $A$ modulo row swaps. Hence, $\det([A|I]_{B})\in \{ \pm 1 \}$.
> - (2=>1): Conversely, let $k$ be the index and $I\in {[m] \choose k},J\in {[n] \choose k}$ be the row/column index sets respectively. Then, we aim to show that $\det A_{IJ}\in \{ -1,0,1 \}$. If $\det A_{IJ}=0$ we are done. Suppose $A_{IJ}$ is invertible. We construct a matrix $M$ where $$M:=$$
>   
>   Then, we have a block matrix of the form
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

- **Remark**: $\{ x\in \mathbb{R}^{2} : 2x_{1}+2x \leq b \}$ is integral for $b\in \mathbb{Z}$ is not totally unimodular.

---
##### Examples
> 