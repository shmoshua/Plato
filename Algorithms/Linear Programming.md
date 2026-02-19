#Definition #Algorithms 

> [!definition]
> A ***linear program (LP)*** is an constrained optimization problem in the following form: 
> $$\begin{array}{rll}\underset{ x\in \mathbb{R}^n }{ \max }&c^\top x\\\text{subject to}&Ax\leq b\\&x\geq 0\end{array}$$
> where we have ***variables*** $x\in \mathbb{R}^n$ and ***objective function*** $c\in \mathbb{R}^n$, a ***constraint*** $(A,b)\in \text{Mat}_{m,n}(\mathbb{R})\times \mathbb{R}^m$. 
- **Related definition**: For any primal LP (left) below, the ***dual LP*** (right) is defined as: $$\begin{array}{rll}\underset{ x\in \mathbb{R}^n }{ \max }&c^\top x\\\text{subject to}&Ax\leq b\\&x\geq 0\end{array},\quad \quad \quad \quad \quad \quad \begin{array}{rll}\underset{ y\in \mathbb{R}^m }{ \min }&b^\top y\\\text{subject to}&A^\top y\geq c\\&y\geq 0\end{array}$$

- **Related definition**: For an ILP problem and its relaxed LP, the ***integrality gap*** is defined as: $$\text{IG}:= \sup_{I \text{ instance}}\frac{\text{OPT}_{\text{ILP}}(I)}{\text{OPT}_{\text{LP}}(I)}$$ ^4d8220
---
##### Properties
> [!lemma] Theorem 1 
> Let $(A,b,c)$ define a standard form LP. Then,
> 1. the [[polyhedron]] $P:=\{ x\in \mathbb{R}^n_{+}:Ax = b \}$ has a vertex if it's non-empty.
> 2. If $x^{\sharp}$ is a vertex of $P$, then there exists $B\in {[n]\choose m}$ s.t. 
> 	- $A_{B}$ is invertible.
> 	- $\text{supp}(x^{\sharp}) = B$
> 	- $x^{\sharp}_{B}=A_{B}^{-1}b$
---
> [!lemma] Theorem 1 (Weak Duality)
> For any feasible $x\in \mathbb{R}^n$ in primal LP and feasible $y\in \mathbb{R}^m$ in dual LP, $$c^\top x\leq b^\top y$$

> [!proof]-
> We have that: $$c^\top x=\sum_{i=1}^{n}c_{i}x_{i}\leq \sum_{i=1}^{n}(A^\top y)_{i}x_{i}=x_{i}^\top A^\top y=\sum_{j=1}^{m}(Ax)_{j} y_{j}\leq \sum_{j=1}^{m}b_{j}y_{j}=b^\top y$$

---
> [!lemma] Theorem 2 (Von-Neunmann)
> Let $P:=\{ x\in \mathbb{R}^n: Ax \leq b \}$ and $Q:= \{  y\in \mathbb{R}^m  : y^\top A = c^\top , y \geq 0 \}$ are non-empty, then: $$\max_{x\in P} c^\top x = \min_{y\in Q} y^\top b$$