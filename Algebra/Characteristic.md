#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]]. The ***characteristic*** of $R$ is the smallest positive integer $n$ for which: $$\underbrace{ 1_{R}+\dots+1_{R} }_{ n\text{ times} }=0$$If such $n$ does not exist, $\text{char}(R)=0$.
---
##### Properties
> [!lemma] Theorem 1
> If $F$ is a finite [[field]], 
> 1. $\text{char}(F)=p$ and 
> 2. $\left| F \right|=p^n$ for some $n\geq 1$ with $n=[F:\mathbb{F}_{p}]$

> [!proof]-
> For any ring $R$, there exists a ring homomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{Z}}&\to&{R}\\&{n} &\mapsto & {n\cdot 1_{R}} \end{array}{}$$If $R=F$, as $\mathbb{Z}$ is infinite, $\text{ker }\varphi=m\mathbb{Z}$. Further, as $\mathbb{Z} / m\mathbb{Z}\cong K\subseteq F$,  $\mathbb{Z} / m\mathbb{Z}$ is a domain and $m=p$ for a prime $p$. Therefore, there exists an embedding: $\mathbb{Z} / p\mathbb{Z}\hookrightarrow F$. 
> 
> Viewing $F$ as a vector space over $\mathbb{F}_{p}:=\mathbb{Z} / p\mathbb{Z}$, since $F$ is finite, $\text{dim}_{\mathbb{F}_{p}}F=n<+\infty$.
> 
> Let $\{ x_{1},\dots,x_{n} \}$ be a basis of $F$ over $\mathbb{F}_{p}$. Then, every element of $F$ has a unique representation w.r.t the basis. One easily sees that $\left| F \right|=p^n$.
- **Remark**: There exists $n\geq 1$ s.t. there exists no field of order $n$.
---
> [!lemma] Theorem 2
> Let $p$ be a prime and $q=p^n$ for some $n\geq 1$. A field $F$ has $q$ elements if and only if it is a [[splitting field]] of $x^q-x\in \mathbb{F}_{p}[X]$. 

> [!proof]-
> Suppose $F$ is a finite field with $q$ elements. Then, $F^{*}$ is a multiplicative group of order $q-1$. So for any $c\in F^{*}$, $c^{q-1}=1$ and $c^q=c$. Therefore, $c$ is a root of $x^q-x$. Therefore, for any $c\in F$, $c^q-c=0$. This shows that $F$ is a splitting field of $x^q-x$. 
> 
> Conversely, assume $K$ is a splitting field of $f(x):=x^q-x\in \mathbb{F}_{p}[X]$. Then, $f'(x)=qx^{q-1}-1=-1$ and $f$ is separable by [[Separable Extension|Corollary]]. Then, $f$ has distinct roots and has exactly $q$ roots in $K$. 
>  
> Let $\alpha,\beta$ be two roots of $f$. Then, $\alpha^q=\alpha$ and $\beta^q=\beta$ and therefore, $$(\alpha \beta)^q=\alpha^q\beta^q=\alpha\beta$$$$\left( \frac{1}{\alpha} \right)^q=\frac{1}{\alpha^q}=\frac{1}{\alpha}$$$$(\alpha\pm\beta)^p=\alpha^p\pm\beta^p=\alpha\pm\beta$$Therefore, the roots of $f$ in $K$ form a field. Hence, it must be the whole field $K$, as $K$ is the splitting field. This shows that $K$ has $q$ elements.
---
