#Definition #LinearAlgebra 

> [!definition]
> Let $M\in \mathbb{R}^{n,n}$ be a matrix. 
> 1. the ***determinant*** is given by: $$\det M:=\sum_{\sigma\in S_{n}}\text{sgn}(\sigma)m_{1,\sigma(1)}\dots m_{n,\sigma(n)}$$
---
##### Properties
> [!lemma] Theorem (Cauchy-Binet)
> For $P\in \mathbb{R}^{r,s}$ and $Q\in \mathbb{R}^{s,r}$ where $r\leq s$, we have: $$\det(PQ)=\sum_{Z}^{}\det P_{Z}\det Q_{Z}$$where $Z\in {[s] \choose r}$ and $P_{Z},Q_{Z}$ is the $r\times r$-submatrix with column and row $Z$ respectively.