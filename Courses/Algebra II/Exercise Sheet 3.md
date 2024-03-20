x#Series #Algebra 

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
2. Let $(p_{i})_{i}\subseteq \mathbb{Z}$ be the enumeration of primes. Then, $\sqrt{ p_{i} }$ is algebraic over $\mathbb{Q}$ with $X^{2}-p$ as the minimal polynomial. We will show that for any $n\geq 1$, $[\mathbb{Q}(\sqrt{ p_{1} },\dots,\sqrt{ p_{n} }):\mathbb{Q}]=2^n$ by induction. Firstly, one can easily see that this holds for $n=1,2$. Let $K_{n}:=\mathbb{Q}(\sqrt{ p_{1} },\dots,\sqrt{ p_{n} })$ for all $n$. 

   We will show that for all $n\geq 1$, $\sqrt{ p_{n} }\notin K_{n-1}$. For $n=1$, $\sqrt{ p_{1} }\notin \mathbb{Q}$. 
   
   Now, assume $\sqrt{ p_{n} }\in K_{n-1}$. Let $m\geq 1$ be the smallest integer s.t. $\sqrt{ p_{n} }\in K_{m}=K_{m-1}(\sqrt{ p_{m} })$. Then, $\sqrt{ p_{n} }=a+b \sqrt{ p_{m} }$ for $a,b\in K_{m-1}$. By squaring, we get: $$p_{n}=a^{2}+p_{m}b ^{2}+2ab \sqrt{ p_{m} }$$If $ab\neq 0$, then $\sqrt{ p_{m} }\in K_{m-1}$ which is a contradiction. If $b=0$, then $\sqrt{ p_{n} }=a\in K_{m-1}$ which is a contradiction to the minimality of $m$. Finally, if $a=0$, then $p_{n}=p_{m}b ^{2}$
   
   We have $\sqrt{ p_{n} }=a+b \sqrt{ p_{n-1} }$ for $a,b\in K_{n-2}$. By squaring, we get: $$p_{n}=a^{2}+p_{n-1}b ^{2}+2ab \sqrt{ p_{n-1} }$$If $ab\neq 0$, then $\sqrt{ p_{n-1} }=(p_{n}-a^{2}-p_{n-1}b ^{2}) / 2ab\in K_{n-2}$ which is a contradiction. If $a=0$, then $p_{n}=p_{n-1} b ^{2}$
   
   
   We will show that $[K_{n-2}(\sqrt{p_{n-1}  },\sqrt{ p_{n} }):K_{n-2}]=4$. 
   
   Consider $K_{n-1}(\sqrt{ p_{n} }):K_{n-1}$. As $X^{2}-p_{n}\in K_{n-1}[X]$, we have that $[K_{n-1}(\sqrt{ p_{n} }):K_{n-1}]\leq 2$. Suppose that $[K_{n-1}(\sqrt{ p_{n} }):K_{n-1}]= 1$. Then, $\sqrt{ p_{n} }\in K$ and 
3. 
4. Assume that $\overline{\mathbb{Q}}:\mathbb{Q}$ is finite with degree $n$. Then, $\{ \sqrt{ p_{i} } \}_{i=1}^{n+1}$ is linearly dependent, i.e. there exists $a_{1},\dots,a_{n+1}\in \mathbb{Q}$ s.t. $$a_{1}\sqrt{ p_{1} }+a_{2}\sqrt{ p_{2} }+\dots+a_{n+1}\sqrt{ p_{n+1} }=0$$
   