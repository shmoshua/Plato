#Definition #Algebra 
> [!definition]
> A ***finite field*** is a [[field]] that is finite.
---
##### Properties

> [!lemma] Theorem 1
> Let $\mathbb{F}$ be a finite field. Then, 
> 1. $\text{char }\mathbb{F}=p$ for some prime $p$ and 
> 2. $\left| \mathbb{F} \right|=p^n$ for $n:=[\mathbb{F}:\mathbb{F}_{p}]$

> [!proof]-
> We have:
> 1. For any commutative ring $R$, there exists a ring homomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{Z}}&\to&{R}\\&{n} &\mapsto & {n\cdot 1_{R}} \end{array}{}$$If $R=\mathbb{F}$, as $\mathbb{Z}$ is infinite, $\text{ker }\varphi=m\mathbb{Z}$. Further, as $\mathbb{Z} / m\mathbb{Z}\cong K\subseteq \mathbb{F}$,  $\mathbb{Z} / m\mathbb{Z}$ is a domain and $m=p$ for a prime $p$. Therefore, there exists an embedding: $\mathbb{F}_{p}\hookrightarrow \mathbb{F}$. 
> 
> 2. Viewing $\mathbb{F}$ as a vector space over $\mathbb{F}_{p}$, since $\mathbb{F}$ is finite, $\text{dim}_{\mathbb{F}_{p}}\mathbb{F}=:n<+\infty$ for some $n$.
> 
> 	Let $\{ x_{1},\dots,x_{n} \}$ be a basis of $\mathbb{F}$ over $\mathbb{F}_{p}$. Then, every element of $F$ has a unique representation w.r.t the basis. One easily sees that $\left| F \right|=p^n$.
- **Remark**: There exists $n\geq 1$ s.t. there exists no field of order $n$.
---
> [!lemma] Theorem 2
> Let $p$ be a prime and $q=p^n$ for some $n\geq 1$. For a field $\mathbb{F}$, TFAE:
> 1. $\mathbb{F}$ has $q$ elements 
> 2. $\mathbb{F}$ is a [[splitting field]] of $x^q-x\in \mathbb{F}_{p}[X]$. 

> [!proof]-
> We have:
> 1. (1=>2): Suppose $\mathbb{F}$ is finite with $q$ elements. Then, $\mathbb{F}^\times$ is a multiplicative group of order $q-1$. So for any $c\in \mathbb{F}^\times$, $c^{q-1}=1$ and $c^q=c$. Therefore, $c$ is a root of $x^q-x$. Hence, for any $c\in \mathbb{F}$,  $\mathbb{F}$ is the smallest field that contains all roots of $x^q-x$.
> 2. (2=>1): Assume $\mathbb{F}$ is a splitting field of $f(x):=x^q-x\in \mathbb{F}_{p}[X]$. Then in $\mathbb{F}_{p}[X]$,  $$f'(x)=qx^{q-1}-1=-1$$Hence, $\gcd(f',f)=1$ and by [[Separable Extension|Theorem 3 Corollary]], $f$ is separable, i.e. $f$ has distinct roots and has exactly $q$ roots in $\mathbb{F}$. 
>    
>    Let $\alpha,\beta$ be two roots of $f$. Then, $\alpha^q=\alpha$ and $\beta^q=\beta$ and therefore: 
>    1. $(\alpha\beta)^q=\alpha^q\beta^q=\alpha\beta$ and $\alpha\beta$ is a root of $f$. 
>    2. $(1 / \alpha)^q=1 / \alpha^q=1 / \alpha$ and $1 / \alpha$ is a root of $f$.
>    3. $(\alpha\pm\beta)^q=\alpha^q\pm\beta^q=\alpha\pm\beta$
>  
>    Hence, the roots of $f$ in $\mathbb{F}$ form a field. However, as $\mathbb{F}$ is the splitting field of $f$, it must be the whole field. This shows that $\left| \mathbb{F} \right|=q$.
---
> [!lemma] Theorem 3 (Properties of finite fields)
> For a finite field $\mathbb{F}$, 
> 1. $\mathbb{F}^{\times}$ is cyclic.
> 2. $\mathbb{F}$ is isomorphic to $\mathbb{F}_{p}[X] / (f(x))$ for some prime $p$ and irreducible monic $f\in \mathbb{F}_{p}[X]$.
> 3. every irreducible $f\in \mathbb{F}_{p}[X]$ with $\deg(f)=n$ divides $f(x)|x^{p^n}-x$.
> 4. every irreducible $f\in \mathbb{F}_{p}[X]$ with $\deg(f)=n$ is separable.


> [!proof]+
> We have:
> 1. Follows directly from [[Field|Theorem 5]].
> 2. Let $\text{char } \mathbb{F}=p$ and $\left| \mathbb{F} \right|=p^n$. Let $\alpha$ be the generator of $\mathbb{F}^\times$. We will consider: $$E_{\alpha}:\mathbb{F}_{p}[X]\to \mathbb{F},\quad g\mapsto g(\alpha)$$
> 	Then, $E_{\alpha}$ is of course a ring homomorphism. Since every element of $\mathbb{F}$ is either zero or a power of $\alpha^r$, we have that $E_{\alpha}(x^r)=\alpha^r$. Therefore, $E_{\alpha}$ is surjective and we have $\mathbb{F}_{p}[X] / \text{ker }E_{\alpha}\cong \mathbb{F}$.
> 	
> 	As $\mathbb{F}$ is a field, $\text{ker }E_{\alpha}$ is a maximal ideal. As $\mathbb{F}_{p}[X]$ is a PID, $\text{ker }E_{\alpha}=(f(x))$ where $f$ is irreducible. Modulo multiplying by a unit, $f$ is monic. 
> 3. Let $f$ be irreducible 
- **Corollary**: If $L:K$ is an extension of finite fields, then $L:K$ is [[Field Extension|simple]], since if $\braket{ \alpha  }=L^{\times}$, then $L=K(\alpha)$.
---
> [!lemma] Theorem 4
> A subfield of $\mathbb{F}_{p^n}$has order $p^d$ where $d|n$ and there exists one such field for every divisor $d|n$.
---