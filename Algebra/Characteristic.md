#Definition #Algebra 

> [!definition]
> Let $R$ be a [[ring]]. The ***characteristic*** of $R$ is the smallest positive integer $n$ for which: $$\underbrace{ 1_{R}+\dots+1_{R} }_{ n\text{ times} }=0$$If such $n$ does not exist, $\text{char}(R)=0$.
---
##### Properties
> [!lemma] Theorem 1
> If $F$ is a finite [[field]], 
> 1. $\text{char}(F)=p$ and 
> 2. $\left| F \right|=p^n$ for some $n\geq 1$ with $n=[F:\mathbb{F}_{p}]$

> [!proof]
> For any ring $R$, there exists a ring homomorphism: $$\begin{array}{cccc} {\varphi:}&{\mathbb{Z}}&\to&{R}\\&{n} &\mapsto & {n\cdot 1_{R}} \end{array}{}$$If $R=F$, as $\mathbb{Z}$ is infinite, $\text{ker }\varphi=m\mathbb{Z}$. Further, as $\mathbb{Z} / m\mathbb{Z}\cong K\subseteq F$,  $\mathbb{Z} / m\mathbb{Z}$ is a domain and $m=p$ for a prime $p$. Therefore, there exists an embedding: $\mathbb{Z} / p\mathbb{Z}\hookrightarrow F$. 
> 
> Viewing $F$ as a vector space over $\mathbb{F}_{p}:=\mathbb{Z} / p\mathbb{Z}$, since $F$ is finite, $\text{dim}_{\mathbb{F}_{p}}F=n<+\infty$.
> 
> Let $\{ x_{1},\dots,x_{n} \}$ be a basis of $F$. 