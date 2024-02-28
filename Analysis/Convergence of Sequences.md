#Definition #Analysis  #LST
> [!definition]
> Let $X$ be a [[topological space]]. A sequence $(x_{n})_{n}\subseteq X$ ***converges to $x\in X$*** if for any (open) neighborhood $U$ of $x$, there exists $N\geq 0$ s.t. $x_{n}\in U$ for all $n\geq N$. Then, Then, $x$ is the ***limit*** of our sequence and is written as $x=\lim_{ n \to \infty }x_{n}$.
- **Remark**: If $X$ is a [[metric space]], this is equivalent to: for all $\varepsilon>0$, there exists $N\geq 0$ s.t. $d(x_{n},x)<\varepsilon$ for all $n\geq N$. Furthermore, $x=\lim_{ n \to \infty }x_{n}$ if and only if $\lim_{ n \to \infty }d(x_{n},x)=0$.

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