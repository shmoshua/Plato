#Definition #LinearAlgebra 

> [!definition]
> Let $M\in \mathbb{R}^{n,n}$ be a matrix. 
> 1. the ***determinant*** is given by: $$\det M:=\sum_{\sigma\in S_{n}}\text{sgn}(\sigma)m_{1,\sigma(1)}\dots m_{n,\sigma(n)}$$
---
##### Properties
> [!lemma] Theorem (Cauchy-Binet)
> For $P\in \mathbb{R}^{r,s}$ and $Q\in \mathbb{R}^{s,r}$ where $r\leq s$, we have: $$\det(PQ)=\sum_{Z}^{}\det P_{Z}\det Q_{Z}$$where $Z\in {[s] \choose r}$ and $P_{Z},Q_{Z}$ is the $r\times r$-submatrix with column and row $Z$ respectively.

^cdfa8e

> [!proof]-
> Let $A:=\{ a_{1},\dots,a_{r} \}$, $B:=\{ b_{1},\dots,b_{s} \}$ and $C:=\{ c_{1},\dots,c_{r} \}$. We define a DAG $G=(A\sqcup B\sqcup C,E)$ where:
> 1. $a_{i}\to b_{j}\in E$ with $w(a_{i}\to b_{j})=P_{ij}$ for any $i\in[r],j\in[s]$, and
> 2. $b_{j}\to c_{k}\in E$ with $w(b_{j}\to c_{k})=Q_{jk}$ for any $j\in[s],k\in[r]$.
> 
> Then, from the [[Directed Acyclic Graph (DAG)|Gessel-Viennot theorem]], the path matrix $M$ w.r.t. $A$ and $C$ is given by: $$M_{ik}=\sum_{P:a_{i}\to c_{k}}^{}w(P)=\sum_{j\in[s]}P_{ij}Q_{jk}$$and $M=PQ$. Therefore, $$\begin{aligned}\text{det}(PQ)&=\sum_{\begin{array}\ \mathcal{P}\text{ vertex-disjoint}\\\text{path system}\end{array}}^{}\text{sgn}(\mathcal{P})w(\mathcal{P})\\&=\sum_{Z}\left( \sum_{\mathcal{P}_{1}:A\to Z}\text{sgn}(\mathcal{P}_{1})w(\mathcal{P}_{1}) \right)\left( \sum_{\mathcal{P}_{2}:Z\to B}\text{sgn}(\mathcal{P}_{2})w(\mathcal{P}_{2}) \right)\\&=\sum_{Z}^{}\det P_{Z}\det Q_{Z}\end{aligned}$$

^23ad94

---
> [!lemma] Theorem (Cramer's Rule)
> Let $A\in \mathbb{R}^{n,n}$ be invertible and $b\in \mathbb{R}^n$. TFAE:
> 1. $Ax= b$
> 2. $x_{i}=\frac{\det(A[i])}{\det(A)}$ where $A[i]=[A_{:,1}|\dots|A_{:,i-1}|b|A_{:,i+1}|\dots|A_{:,n}]$ for all $i\in[n]$.

---
> [!lemma] Lemma (Farkas-Lemma)
> Let $A\in \mathbb{R}^{m,n},b\in \mathbb{R}^m$. Then, 
> 1. either $Ax\leq b$ is feasible or $y^\top A = 0,y^\top b < 0, y\geq 0$ is feasible.

> [!proof]-
> Assume both are feasible. Then, we have: $$0=0^\top x = y^\top Ax \leq y^\top b< 0$$which is a contradiction. 
> 
> It suffices to show that at least one of them is feasible.
---