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
> [!def] Problem 3
> Consider the ring $R:=\mathbb{Z}[\sqrt{ -2 }]$.
> 1. Show that $R$ is a Euclidean domain with the norm function: $$\begin{array}{cccc} {N:}&{R}&\to&{\mathbb{Z}_{\geq 0}}\\&{a+ b\sqrt{ -2 }} &\mapsto & {a^{2}+2 b ^{2}} \end{array}{}$$
> 2. Show that the norm $N$ is multiplicative and hence if $r|s$ in $\mathbb{Z}[\sqrt{ -2 }]$, then $N(r)$ divides $N(s)$.
> 3. Show that the only units in $\mathbb{Z}[\sqrt{ -2 }]$ are $\pm 1$.

We have:
1. Let $a,b\in R$ non-zero. Then, in $\mathbb{Q}[\sqrt{ -2 }]$, we have $p_{1},p_{2}\in \mathbb{Q}$ s.t.  $$\frac{a}{b}=p_{1}+p_{2}\sqrt{ 2 }$$Now, let $q_{1},q_{2}\in \mathbb{Z}$ be integers closest to $p_{1}$ and $p_{2}$, respectively. Then, we define $q:=q_{1}+q_{2}\sqrt{ -2 }$ and $\theta:= \frac{a}{b}-q$. Therefore, we get: $$a=qb+b\theta$$We are left to show that if $b\theta\neq0$ then $N(b\theta)<N(b)$. Notice that from the definition of $q$, $$N(\theta)\leq \frac{1}{4}+\frac{2}{4}=\frac{3}{4}$$From the multiplicativity of $N$ (shown in part b), we have $N(b\theta)\leq \frac{3}{4}N(b)<N(b)$.
2. Let $a:=a_{1}+a_{2}\sqrt{ -2 }$ and $b:=b_{1}+b_{2}\sqrt{ -2 }$ for $a,b\in \mathbb{Z}[\sqrt{ -2 }]$. Then, $$\begin{align}N(ab)&=(a_{1}b_{1}-2a_{2}b_{2})^{2}+2(a_{1}b_{2}+b_{1}a_{2})^{2}\\&=a_{1}^{2}b_{1}^{2}\cancel{ -4a_{1}a_{2}b_{1}b_{2} }+4a_{2}^{2}b_{2}^{2}+2a_{1}^{2}b_{2}^{2}+\cancel{ 4a_{1}a_{2}b_{1}b_{2} }+2a_{2}^{2}b_{1}^{2}\\&=(a_{1}^{2}+2a^{2}_{2})(b_{1}^{2}+2b_{2}^{2})\\&=N(a)N(b)\end{align}$$Let $r|s$ then there exists $x\in \mathbb{Z}[\sqrt{ -2 }]$ s.t. $rx=s$. Therefore, $N(r)N(x)=N(s)$ and $N(r)|N(s)$.
3. Let $a$ be a unit. Then, there exists $b\in \mathbb{R}$ s.t. $N(a)N(b)=1$. As $N(R)\subseteq\mathbb{Z}_{\geq 0}$, $N(a)=1$.  This is equivalent to $a=\pm 1$.
---
> [!def] Problem 4
> The goal of this exercise is to show that the only integral solutions of the diophantine equation $y^{2}=x^{3}-2$ are $(x,y)=(3,5)$ and $(3,-5)$.
> 1. Show that if $x,y\in \mathbb{Z}$ satisfy $y^{2}=x^{3}-2$ then $x$ is odd.
> 2. Show that if $x,y\in \mathbb{Z}$ satisfy $y^{2}=x^{3}-2$ then $y+\sqrt{ -2 }$ and $y-\sqrt{ -2 }$ are relatively prime over $\mathbb{Z}[\sqrt{ -2 }]$.
> 3. Write $x^3=y^{2}+2=(y+\sqrt{ -2 })(y-\sqrt{ -2 })$ to write $(y+\sqrt{ -2 })=(a+b \sqrt{ -2 })^3$ and conclude that only solutions are $(x,y)=(3,5)$ and $(3,-5)$.

We have:
1. Assume $x=2k$ is even with $k\in\mathbb{Z}$. Then, $y^{2}=2(4k^{3} -1)$ and $2|y$. Indeed, it follows that $4|y^{2}$ which is a contradiction as $2\nmid (4k^3-1)$ (as it is odd).
2. Let $y+\sqrt{ -2 }$ and $y-\sqrt{ -2 }$ not be relatively prime. Then, for any $a_{1},a_{2},b_{1},b_{2}\in \mathbb{Z}$: $$\begin{align}(a_{1}+a_{2}\sqrt{ -2 })(y+\sqrt{ -2 })+(b_{1}+b_{2}\sqrt{ -2 })(y-\sqrt{ -2 })&\neq 1\\((a_{1}+b_{1})y-2(a_{2}-b_{2}))+((a_{1}-b_{1})+(a_{2}+b_{2})y)\sqrt{ -2 }&\neq 1\\(a_{1}+b_{1})^{2}y^{2}-4(a_{1}+b_{1})(a_{2}-b_{2})+4(a_{2}-b_{2})^{2}+2(a_{1}+b_{1})^{2}-8a_{1}b_{1}+4(a_{1}-b_{1})(a_{2}+b_{2})y+2(a_{2}+b_{2})^{2}y^{2}\sqrt{ -2 }&\neq 1\end{align}$$
