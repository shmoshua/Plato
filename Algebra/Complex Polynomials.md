#Definition #Algebra 

> [!definition]
> ***Complex polynomials*** are elements in the [[polynomial ring]] $\mathbb{C}[X]$ on the field $\mathbb{C}$.
---
##### Properties
> [!lemma] Theorem 1 (Fundamental Theorem of Algebra)
> A polynomial $f\in \mathbb{C}[X]$ with $\deg(f)\geq 1$ has at least one root.

> [!proof] Proof (Topology)
> Wlog assume that $f$ is monic. Assume that $f$ has no root. Then, we can define: $$h:[0,1]\times \mathbb{R}\to S^1,\quad (s,t)\mapsto \frac{f(t\exp(2\pi is)) /f(t)}{\left| f(t\exp(2\pi is)) /f(t) \right| }$$which is well-defined as $f$ admits no roots. Then, 
> 1. $h(1,t)=1$ for all $t\in \mathbb{R}$.
> 2. $h(0,t)=1$ for all $t\in \mathbb{R}$.
> 3. $h()$