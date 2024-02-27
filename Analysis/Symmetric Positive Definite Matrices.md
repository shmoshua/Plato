#Definition #Analysis 

> [!definition]
> A symmetric matrix $A\in \mathbb{R}^{n,n}$ is called a ***symmetric, positive definite (SPD) matrix*** if and only if it holds that for all non-zero $x\in \mathbb{R}^n$: $$x^\top Ax >0$$
> If it's just $\geq$, then it is called ***symmetric, positive semidefinite (SPsD)***.
---
##### Properties
> [!lemma] Theorem SPD.1
> For a finite-dimensional vector space $V$, $\braket{ \cdot , \cdot }:V\times V \to \mathbb{R}$ is an [[Inner Product Space|inner product]] if and only if there exists a symmetric, positive definite matrix $A\in \mathbb{R}^{n,n}$ s.t. $$\braket{ x , y } =x^\top A y$$for all $x,y\in \mathbb{R}^n$.