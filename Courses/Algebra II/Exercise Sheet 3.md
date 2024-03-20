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

We have: 
1. We trivially have $0,1\in \overline{\mathbb{Q}}$. Now, consider $\alpha,\beta\in \overline{\mathbb{Q}}$. As $\alpha,\beta$ are algebraic over $\mathbb{Q}$, $\mathbb{Q}(\alpha,\beta):\mathbb{Q}$ is finite and algebraic. Therefore, $\alpha-\beta$ is algebraic over $\mathbb{Q}$ and $\alpha-\beta\in \overline{\mathbb{Q}}$. 
   
   Now it suffices to show that for every non-zero $\alpha\in \overline{\mathbb{Q}}$, there exists an multiplicative inverse. Then, we can proceed analogously to addition to show that the non-zero elements form a multiplicative group. Let $0\neq\alpha\in \overline{\mathbb{Q}}$. Then, there exists a non-zero polynomial $p(x):=a_{0}+a_{1}x+\dots +a_{n}x^n\in \mathbb{Q}[X]$ s.t. $p(\alpha)=0$. We define a new polynomial: $q(x):=a_{n}+a_{n-1}x+\dots+a_{0}x^n$. Then, $$q\left( \frac{1}{\alpha} \right)=a_{n}+\frac{a_{n-1}}{\alpha}+\dots+\frac{a_{0}}{\alpha^n}=\alpha^n\cdot p(\alpha)=0$$Therefore, $\frac{1}{\alpha}\in \overline{\mathbb{Q}}$. This proves that $\overline{\mathbb{Q}}$ is a field.
2. Consider $(2^{2^{-k}})_{k}$. Then, $2^{2^{-k}}$ is algebraic over $\mathbb{Q}$ with $X^{2^k}-2$ as the minimal polynomial which is irreducible by Eisenstein. Then, for any $n\geq 1$, $2^{2^{-k}}\in \mathbb{Q}(2^{2^{-n}})$ for all $k\leq n$. Therefore, $$[\mathbb{Q}(2^{2^{-1}},\dots,2^{2^{-n}}):\mathbb{Q}]=[\mathbb{Q}(2^{2^{-n}}):\mathbb{Q}]=2^n$$ This shows that $\overline{\mathbb{Q}}:\mathbb{Q}$ is an infinite extension.
---
> [!def] Problem 3
> Let $\mathbb{A}:=\mathbb{R}\cap  \overline{\mathbb{Q}}$. Show that $\mathbb{A}$ is countable, and conclude that there are real numbers which are transcendental.

Firstly, notice that the set $\mathbb{Q}[X]$ is countable as $\mathbb{Q}$ is countable. As each polynomial in $\mathbb{Q}[X]$ admit finitely many roots, it follows that $\mathbb{A}$ is a countable set. However, as $\mathbb{R}$ is uncountable, there exist real numbers that are not algebraic over $\mathbb{Q}$, i.e. they are transcendental.

---
> [!def] Problem 4
> Let $L:K$ be an algebraic field extension. Let $K_{1},K_{2}$ be two fields with $K\subseteq K_{1},K_{2}\subseteq L$, such that the field extensions $K_{1}:K$ and $K_{2}:K$ are finite. The composite of $K_{1}$ and $K_{2}$ is defined as $K_{1}K_{2}:=K(K_{1}\cup K_{2})$. Show:
> 1. $[K_{1}K_{2}:K_{2}]\leq [K_{1}:K]$
> 2. $[K_{1}K_{2}:K]\leq[K_{1}:K][K_{2}:K]$
> 3. if $\gcd([K_{1}:K],[K_{2}:K])=1$, then equality holds in 2.

We have that:
1. Let $[K_{1}:K]=:n$ and assume $\alpha_{1},\dots,\alpha_{n}\in K_{1}$ is a basis of $K_{1}$ over $K$. Therefore, $K_{1}=K(\alpha_{1},\dots,\alpha_{n})$ and $K_{1}K_{2}=K_{2}(\alpha_{1},\dots,\alpha_{n})$. However, as $\alpha_{1},\dots,\alpha_{n}$ are algebraic over $K$ and therefore over $K_{2}$, we have $K_{1}K_{2}=K_{2}[\alpha_{1},\dots,\alpha_{n}]$. It follows that $\alpha_{1},\dots,\alpha_{n}$ generate $K_{1}K_{2}$ over $K_{2}$ and this proves the statement.
2. We have: $$[K_{1}K_{2}:K]=[K_{1}K_{2}:K_{2}][K_{2}:K]\leq[K_{1}:K][K_{2}:K]$$
3. We have that $[K_{1}:K]|[K_{1}K_{2}:K]$ and by symmetry $[K_{2}:K]|[K_{1}K_{2}:K]$. However, as they are coprime, $[K_{1}:K][K_{2}:K]|[K_{1}K_{2}:K]$. This shows that $[K_{1}:K][K_{2}:K]\leq[K_{1}K_{2}:K]$.
---

