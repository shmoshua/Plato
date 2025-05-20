#Definition #Analysis 

> [!definition]
> Let $A\in \mathbb{R}^{n,n}$ be a symmetric matrix. $A$ is:
> 1. ***positive definite*** if $x^\top Ax > 0$ for all $x\neq 0$.
> 2. ***positive semidefinite*** if $x^\top Ax\geq 0$ for all $x\in \mathbb{R}^n$. 
> 3. ***indefinite*** if neither $A$ nor $-A$ is positive semidefinite.

^fd40d2

- **Related notation**: For symmetric matrices $A,B\in \mathbb{R}^{n,n}$, $A\leq B$ if $B-A$ is positive semidefinite.

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
> [!lemma] Proposition 3 (Loewner Order)
> Let $A,B,C,D\in \mathbb{R}^{n,n}$ be symmetric.
> 1. The Loewner order $\leq$ is a partial order.
> 2. if $A\leq B$ then $A+C\leq B+C$.
> 3. if $A\leq B$ and $C\leq D$ then $A+C\leq B+D$.
> 4. if $0\leq A$ and $1\leq \alpha$, then $\frac{1}{\alpha}A\leq A\leq \alpha A$.
> 5. if $A\leq B$ then for all $i$, $\lambda_{i}(A)\leq \lambda_{i}(B)$.

> [!proof]+
> We have that:
> 1. $0$ is positive definite hence $A\leq A$. For antisymmetry, let $A\leq B$ and $B\leq A$. Then, for all $x\in \mathbb{R}^n$, $x^\top (B-A)x\geq 0$ and $x^\top(A-B)x\geq 0$. Hence, $x^\top (B-A)x=0$ and $B=A$. Lastly, for transitivity, $$x^\top(C-A)x=x^\top(C-B)x+x^\top(B-A)x\geq 0$$
> 2. $B+C-A-C=B-A$.
> 3. $A+C\leq B+C\leq B+D$ by transitivity.
> 4. We have that $\left( 1-\frac{1}{\alpha} \right)A\geq 0$ and $(\alpha-1)A\geq 0$.
> 5. By [[Spectral Theorem#^9514ed|Courant Fischer]], $$\lambda_{i}(A)=\min_{W\leq \mathbb{R}^n:\text{dim}(W)=i}\max_{0\neq x \in W}\frac{x^\top Ax}{x^\top x}\leq \min_{W\leq \mathbb{R}^n:\text{dim}(W)=i}\max_{0\neq x \in W}\frac{x^\top Bx}{x^\top x}=\lambda_{i}(B)$$
---
> [!lemma] Theorem SPD.1
> For a finite-dimensional vector space $V$, $\braket{ \cdot , \cdot }:V\times V \to \mathbb{R}$ is an [[Inner Product Space|inner product]] if and only if there exists a symmetric, positive definite matrix $A\in \mathbb{R}^{n,n}$ s.t. $$\braket{ x , y } =x^\top A y$$for all $x,y\in \mathbb{R}^n$.

^ad9fcb
