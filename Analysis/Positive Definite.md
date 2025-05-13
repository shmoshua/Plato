#Definition #Analysis 

> [!definition]
> Let $A\in \mathbb{R}^{n,n}$ be a symmetric matrix. $A$ is:
> 1. ***positive definite*** if $x^\top Ax > 0$ for all $x\neq 0$.
> 2. ***positive semidefinite*** if $x^\top Ax\geq 0$ for all $x\in \mathbb{R}^n$. 
> 3. ***indefinite*** if neither $A$ nor $-A$ is positive semidefinite.

^fd40d2

---
##### Properties
> [!lemma] Theorem 1
> Let $A$ be a symmetric matrix. 
> 1. $A$ is positive definite if and only if $\lambda_{i}(A)> 0$ for all $i\in[n]$.
> 2. $A$ is positive semidefinite if and only if $\lambda_{i}(A)\geq 0$ for all $i\in[n]$.

^39de24

> [!proof]-
> Follows from [[Spectral Theorem|Courant-Fischer]].

^a74f2b

---
> [!lemma] Proposition 2
> Let $A$ be a symmetric matrix.
> 1. $\|A\|=\|\lambda(A)\|_{\infty}$. 

^0e2d57

---
> [!lemma] Theorem SPD.1
> For a finite-dimensional vector space $V$, $\braket{ \cdot , \cdot }:V\times V \to \mathbb{R}$ is an [[Inner Product Space|inner product]] if and only if there exists a symmetric, positive definite matrix $A\in \mathbb{R}^{n,n}$ s.t. $$\braket{ x , y } =x^\top A y$$for all $x,y\in \mathbb{R}^n$.

^ad9fcb
