#Definition #Optimization

> [!definition]
> Let $X$ be a [[topological space]]. An ***optimization problem*** over $X$ is a problem in the form: $$\begin{array}{rl}\underset{ x\in X }{ \min/\max }&f(x)\\\text{s.t.}&g_{1}(x)\leq b_{1}\\&\vdots\\&g_{m}(x)\leq b_{m}\end{array}$$
> 1. the ***feasible set*** is given by $\mathcal{F}:=\{ x\in X:g_{i}(x)\leq b_{i}, \forall i\in[m] \}$.
> 2. A point $x\in X$ is ***feasible*** if $x\in \mathcal{F}$ and ***infeasible*** if otherwise.
> 3. $x^{*}\in \mathcal{F}$ is an ***optimal solution*** if $f(x^{*})\leq f(x)$ /$f(x^{*})\geq f(x)$ for all $x\in \mathcal{F}$.

^228705

- **Related definition**:  The optimization problem is ***infeasible*** if $\mathcal{F}=\varnothing$. ^72e4bb

---
