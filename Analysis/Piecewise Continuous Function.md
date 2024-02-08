#Definition #Analysis 

> [!definition]
> A function $u:\mathbb{R} \to \mathbb{R}^m$ is ***piecewise continuous*** if and only if it is continuous at all $t\in \mathbb{R}$ except those in a set of ***discontinuity points*** $D\subseteq \mathbb{R}$ s.t.:
> 1. for all $d\in D$: $\lim_{ t \to d^+ }u(t)$ and $\lim_{ t \to d^- }u(t)$ exist and are finite.
> 2. for all $d\in D$: $u(d)=\lim_{ t \to d^+ }u(t)$
> 3. for all $t_{0},t_{1}\in \mathbb{R}$, $D \cap[t_{0},t_{1}]$ contains a finite number of points.
> 
> We use $PC(U,\mathbb{R}^m)$ to denote the set of piecewise continuous functions $u:U \to \mathbb{R}^m$.
---