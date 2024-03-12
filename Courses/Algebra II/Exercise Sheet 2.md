#Series #Algebra 

> [!def] Problem 1
> Decide whether the following polynomials are irreducible in $\mathbb{Q}[X]$.
> 1. $X^{3}-3X^{2}-8$
> 2. $2X^{10}-25X^3+10X+30$
> 3. $2X^3+X^2+2X+2$
> 4. $X^4+X^2+1$

We have that:
1. Using $x\mapsto x-1$: $$(x-1)^{3}-3(x-1)^{2}-8=x^{3}-3x^{2}+3x-1-3x^{2}+6x-3-8=x^{3}-6x^{2}+9x-12$$Therefore it is irreducible with Eisenstein with $p=3$.
2. Irreducible by Eisenstein with $p=5$.
3. Reduce to $\mathbb{Z} /3\mathbb{Z}[X]$. As $f(\overline{0})=\overline{2}$, $f(\overline{1})=\overline{2}$ and $f(\overline{2})=\overline{2}$. Therefore, $f$ is irreducible in $\mathbb{Z}[X]$ and $\mathbb{Q}[X]$.
4. Reduce to $\mathbb{Z} /2\mathbb{Z}[X]$. As $f(\overline{0})=\overline{1}$ and $f(\overline{1})=\overline{1}$. Therefore, $f$ is irreducible in $\mathbb{Z}[X]$ and $\mathbb{Q}[X]$.
---
> [!def] Problem 2
> Consider the ring $R:=\mathbb{Z}[X] / (X^{2}+5)$.
> 1. Show that $R$ is an integral domain.
> 2. Show that $R$ is not a unique factorization domain.

Notice that:
1. $X^{2}+5$ is irreducible in $\mathbb{Q}[X]$ by Eisenstein. As $X^{2}+5$ is also primitive, it is irreducible in $\mathbb{Z}[X]$. As $\mathbb{Z}[X]$ is a UFD, $(X^{2}+5)$ is prime and $R$ is an integral domain.
2. We have: $(X+1)(X-1)=6=2\cdot{3}$.
---
