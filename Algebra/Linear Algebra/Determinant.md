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
