#Definition #LST #Analysis 
> [!definition]
> Let $(X,d)$ be a [[Metric Space|metric space]]. A sequence $(x_{n})_{n}\subseteq X$ ***converges*** to $a\in X$ if and only if for all $\varepsilon>0$ there exists $N\geq 0$ s.t. $$d(x_{n},a)<\varepsilon$$ for all $n\geq N$. Then, $a$ is the ***limit*** of our sequence and is written as $a=\lim_{ n \to \infty }x_{n}$.
- **Equivalent Definition**: $(x_{n})_{n}\subseteq X$ converges to $a$, if for every neighborhood $V$ of $a$, there exists $N\in \mathbb{N}$ s.t. $x_{n}\in V$ for $n\geq N$.
- **Remark**: $a=\lim_{ n \to \infty }x_{n}$ can be also written as $\lim_{ n \to \infty }d(x_{n},a)=0$.
---
##### Properties
> [!lemma] Proposition 1
> A sequence $(x_{n})_{n}$ can only have at most one limit.

> [!proof]-
> Suppose $\lim_{ n \to \infty }x_{n}=a$ and $\lim_{ n \to \infty }x_{n}=b$. Then, for each $\varepsilon>0$, there exists $N_{1}$ and $N_{2}$ s.t. 
> 1. $d(x_{n},a)<\varepsilon$ for $n\geq N_{1}$ and 
> 2. $d(x_{n},b)<\varepsilon$ for $n\geq N_{2}$
>    
> Now, if we take $n\geq N:=\max\{ N_{1},N_{2} \}$, we have: $$d(a,b)\leq d(a,x_{n})+d(x_{n},b)<2\varepsilon$$
> As $\varepsilon$ was arbitrary, $d(a,b)=0$ and $a=b$.
---
##### Examples
- [[Convergence of Sets]]