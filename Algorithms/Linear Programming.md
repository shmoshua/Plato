#Definition #Algorithms 

> [!definition]
> A ***linear program (LP)*** is an constrained optimization problem in the following form: 
> $$\begin{array}{rll}\underset{ x\in \mathbb{R}^n }{ \max }&c^\top x\\\text{subject to}&Ax\leq b\\&x\geq 0\end{array}$$
> where we have ***variables*** $x\in \mathbb{R}^n$ and ***objective function*** $c\in \mathbb{R}^n$, a ***constraint*** $(A,b)\in \text{Mat}_{m,n}(\mathbb{R})\times \mathbb{R}^m$. 
- **Related definition**: For any primal (left) below, the dual (right) is defined as: $$\begin{array}{rll}\underset{ x\in \mathbb{R}^n }{ \max }&c^\top x\\\text{subject to}&Ax\leq b\\&x\geq 0\end{array},\quad \quad \quad \quad \quad \quad \begin{array}{rll}\underset{ x\in \mathbb{R}^n }{ \max }&c^\top x\\\text{subject to}&Ax\leq b\\&x\geq 0\end{array}$$

- **Related definition**: For an ILP problem and its relaxed LP, the ***integrality gap*** is defined as: $$\text{IG}:= \sup_{I \text{ instance}}\frac{\text{OPT}_{\text{ILP}}(I)}{\text{OPT}_{\text{LP}}(I)}$$ ^4d8220
---
