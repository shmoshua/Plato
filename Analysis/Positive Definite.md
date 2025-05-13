#Definition #Analysis 

> [!definition]
> Let $A\in \mathbb{R}^{n,n}$ be a symmetric matrix. $A$ is:
> 1. ***positive definite*** if $x^\top Ax > 0$ for all $x\neq 0$.
> 2. ***positive semidefinite*** if $x^\top Ax\geq 0$ for all $x\in \mathbb{R}^n$. 
> 3. ***indefinite*** if neither $A$ nor $-A$ is positive semidefinite.

---
##### Properties
> [!lemma] Theorem SPD.1
> For a finite-dimensional vector space $V$, $\braket{ \cdot , \cdot }:V\times V \to \mathbb{R}$ is an [[Inner Product Space|inner product]] if and only if there exists a symmetric, positive definite matrix $A\in \mathbb{R}^{n,n}$ s.t. $$\braket{ x , y } =x^\top A y$$for all $x,y\in \mathbb{R}^n$.