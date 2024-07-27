#Definition #Algebra 

> [!definition]
> For a [[field]] $K$, A monic [[Polynomial Ring|polynomial]] $f(x)=x^n+a_{n-1}x^{n-1}+\dots+a_{0}\in K[x]$ is called ***reduced***
> 1.  if $a_{n-1}=0$.
- **Remark:** for $f\in K[X]$, the corr. reduced polynomial is given by $\tilde{f}(x):=f\left( x- \frac{a_{n-1}}{n} \right)$.
---
##### Properties
> [!lemma] Theorem 1
> For a monic polynomial $f\in K[X]$ of degree $n$, 
> 1. $\tilde{f}(x)$ is reduced.
> 2. $D_{f}=D_{\tilde{f}}$, where $D$ denotes the [[discriminant]].

> [!proof]-
> We have that:
> 1. $$\begin{align}\tilde{f}(x)&=\left( x-\frac{a_{n-1}}{n} \right)^n+a_{n-1}\left( x-\frac{a_{n-1}}{n} \right)^{n-1} +\dots+a_{0}\end{align}$$Then, the second term in $\tilde{f}$ is $-n\cdot \frac{a_{n-1}}{n}+a_{n-1}=0$.
> 2. 
---
