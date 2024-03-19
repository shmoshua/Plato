#Series #Algebra 

> [!def] Problem 1
> Consider the following: 
> 1. Let $f$ and $g$ be polynomials over a field $F$. Show that $f$ and $g$ are relatively prime if and only if $f$ and $g$ have no common root in any extension of $F$.
> 2. If $f,g\in F[X]$ are distinct monic irreducible polynomials then show that they have no common roots in any extension of $F$.

We have: 
1. let $f,g\in F[X]$ be relatively prime. Then, there exists $a(x),b(x)\in F[X]$ s.t. $a(x)f(x)+b(x)g(x)=1$. Let $K:F$ and $\alpha\in K$ be a common root of $f,g$. Then, $$0=a(\alpha)f(\alpha)+b(\alpha)g(\alpha)=1$$which is a contradiction. Conversely, assume that $(f(x),g(x))=(h(x))$ for some $h(x)\in F[X]$. Without loss of generality, we can assume that $h$ is irreducible. Then, for $\alpha:=x+(h(x))$, $F(\alpha):F$ and $f$ and $g$ both have $\alpha$ as a root as $h(x)|f(x)$ and $h(x)|g(x)$ in $F[X]$. 
2. We will show that $f,g$ are relatively prime. If not, there exists similarly to above $h(x)\in F[X]$ s.t. $(f(x),g(x))=(h(x))$ and $h(x)|f(x)$ and $h(x)|g(x)$ in $F[X]$. We have that $\deg h=\deg f$, as $f$ is irreducible. However, then $\deg h=\deg g$ as well and $f(x)=a\cdot h(x)$ and $g(x)=b\cdot h(x)$ for $a,b\in F$. As $f,g$ are monic, this is a contradiction to the fact that $f\neq g$.
---
> [!def] Problem 2
> Let $\overline{\mathbb{Q}}:=\{ \alpha\in \mathbb{C} :\alpha \text{ is algebraic over }\mathbb{Q}\}$, the set of all algebraic numbers over $\mathbb{Q}$.
> 1. Show that $\overline{\mathbb{Q}}$ is a field.
> 2. Show that $\overline{\mathbb{Q}}:\mathbb{Q}$ is an infinite extension.

