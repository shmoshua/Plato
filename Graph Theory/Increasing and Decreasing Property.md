#Definition #ProbabilisticMethods 

> [!definition]
> Let $\Omega:=\{ 0,1 \}^N$ with $\mathcal{A}:=2^\Omega$ and there exists $p_{1},\dots,p_{N}$ s.t. $\mathbb{P}(\omega)=\prod_{i:\omega_{i}=1}^{}p_{i}\prod_{j:\omega_{j}=0}(1-p_{j})$.
> 1. An event $A\subseteq \Omega$ is ***increasing*** if for every $x\leq y\in \Omega$,  if $x\in A$ then $y\in A$.
> 2. An event $A\subseteq \Omega$ is ***decreasing*** if for every $x\leq y\in \Omega$,  if $y\in A$ then $x\in A$.
---
##### Properties
> [!lemma] Theorem 1 (Correlation Inequality)
> Let $A,B\subseteq \Omega$. 
> 1. If $A,B$ are both increasing or both decreasing, then: $\mathbb{P}(A\cap B)\geq \mathbb{P}(A)\mathbb{P}(B)$
> 2. If $A$ is increasing but $B$ decreasing or vice versa, then: $\mathbb{P}(A\cap B)\leq \mathbb{P}(A)\mathbb{P}(B)$

> [!proof]+
> We prove it by induction on $N$. 
> 1. If $N=1$, then 