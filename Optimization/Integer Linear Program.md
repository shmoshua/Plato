#Definition #Optimization 

> [!definition]
> An ***Integer Linear program (ILP)*** is given in standard form as follows: $$\begin{array}{rl l} \max & c^\top x\\ \text{s.t.}& Ax = b\\&x\in \mathbb{Z}^n_{+}\end{array}$$where $A\in \mathbb{Z}^{m,n},b\in \mathbb{Z}^m$ and $A$ has a full row rank.

---
##### Properties
> [!lemma] Theorem 1
> For an ILP, there exists an optimal solution $z^{*}$ s.t. $$\left| \text{supp}(z^{*}) \right| \leq 2m\log (4m\left\| A \right\| _{\infty})$$ 