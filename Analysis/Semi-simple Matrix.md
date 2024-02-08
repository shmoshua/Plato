#Definition #Analysis #LST 

> [!definition]
> A matrix $A\in \mathbb{R}^{n,n}$ is ***semi-simple***, if there is a collection of right eigenvectors $\{ v_{i} \}_{i=1}^n\subseteq \mathbb{C}^n$ that are linearly independent in $\mathbb{C}^n$.
- **Remark**: Semi-simple matrices are dense in $\mathbb{R}^{n,n}$.
---
##### Properties
> [!lemma] Theorem 1
> A matrix $A\in \mathbb{R}^{n,n}$ is semi-simple if and only if it is diagonalizable, i.e. there exists an invertible matrix $T\in \mathbb{C}^{n,n}$ and a diagonal matrix $\Lambda\in \mathbb{C}^{n,n}$ such that: $$A = T^{-1}\Lambda T$$

>[!proof]-
> (=>): Assume that $A$ is semi-simple. Then, the matrix $T:=[v_{1}|\dots|v_{n}]^{-1}\in \mathbb{C}^{n,n}$ is invertible. Then, $$AT^{-1}=[Av_{1}|\dots|Av_{n}]=[\lambda_{1} v_{1}|\dots|\lambda_{n} v_{n}]=T^{-1}\Lambda$$Therefore, $$A=T^{-1}\Lambda T$$
> (<=): Assume there exists $T$ s.t. $AT^{-1}=T^{-1}\Lambda$.
---
> [!lemma] Fact 2
> If $A$ is semi-simple, $$e^{ At }=T^{-1}e^{ \Lambda t }T=T^{-1}\text{diag}(e^{\lambda_{1}t},\dots,e^{ \lambda_{n}t })T$$

> [!Proof]-
> Firstly, $A^n=T^{-1}\Lambda^nT$. We show this by induction: for $n=1$, $A=T^{-1}\Lambda T$. Then, we have: $$A^n=T^{-1}\Lambda^{n-1}TT^{-1}\Lambda T=T^{-1}\Lambda^{n-1}\Lambda T=T^{-1}\Lambda^{n}T$$
> We have that: $$\begin{align}e^{ At }=\sum_{n=0}^{\infty} \frac{A^nt^n}{n!}=\sum_{n=0}^{\infty} \frac{T^{-1}\Lambda^nTt^n}{n!}=T^{-1}\sum_{n=0}^{\infty} \frac{\Lambda^nt^n}{n!}T=T^{-1}e^{ \Lambda t }T\end{align}$$
---
> [!lemma] Theorem 3
> If $A$ is [[Simple Matrix|simple]], $A$ is semi-simple.

> [!Proof]-
> Assume $A$ is simple but not semi-simple. Then, there exists $a_{1},\dots,a_{n}\in \mathbb{C}$ not all zero, s.t. $$\sum_{i=1}^{n}a_{i}v_{i}=0$$
> Wlog assume that $a_{1}\neq0$. Then, 
> $$\begin{align}0&=\sum_{i=1}^{n}a_{i}(A-\lambda_{2}I)\dots(A-\lambda_{n}I)v_{i}\\&=\sum_{i=1}^{n}a_{i}(\lambda _{i}-\lambda_{2})\dots(\lambda_{i}-\lambda_{n})v_{i}\\&=a_{1}(\lambda _{1}-\lambda_{2})\dots(\lambda_{1}-\lambda_{n})v_{1}\end{align}$$
> As $a_{1}\neq 0$ and $v_{1}\neq 0$, there exists $2\leq j\leq n$ s.t. $\lambda_{j}=\lambda_{1}$, which is a contradiction.
---
