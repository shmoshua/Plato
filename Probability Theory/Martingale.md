#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]] and $\{ \mathcal{A_{n}} \}_{n\geq 1}$ be an increasing sequence of sub-$\sigma$-algebras, i.e. $\mathcal{A}_{n}\subseteq \mathcal{A}_{n+1}$. Let $\{ X_{n} \}_{n}$ be a sequence of [[Random Variable|random variables]].
> 1. $\{ X_{n} \}_{n}$ is $\{ \mathcal{A}_{n} \}_{n}$-***adapted*** if $X_{n}$ is $\mathcal{A}_{n}$-measurable for all $n\geq 1$.
> 2. $\{ X_{n} \}_{n}$ is ***adapted*** if $X_{n}$ is $\mathcal{A}_{n}$-measurable for all $n\geq 1$ and $\mathcal{A}_{n}:=\sigma(X_{1},\dots,X_{n})$.
> 3. $\{ X_{n} \}_{n}$ is $\{ \mathcal{A}_{n} \}_{n}$-***predictable*** if $X_{n}$ is $\mathcal{A}_{n-1}$-measurable for all $n> 1$.
> 2. $\{ X_{n} \}_{n}$ is ***predictable*** if $X_{n}$ is $\mathcal{A}_{n-1}$-measurable for all $n> 1$ and $\mathcal{A}_{n}:=\sigma(X_{1},\dots,X_{n})$.
> 3. An $\{ \mathcal{A}_{n} \}_{n}$ adapted sequence $\{ X_{n} \}_{n}$ is a ***martingale*** if: $$\mathbb{E}[X_{n+1}|\mathcal{A}_{n}]=X_{n},\quad \forall n\geq 1$$

- **Related definition**: If $\mathbb{E}[X_{n+1}|\mathcal{A}_{n}]\leq X_{n}$ for all $n\geq 1$ it is called a ***submartingale***. If $\mathbb{E}[X_{n+1}|\mathcal{A}_{n}]\geq X_{n}$ it is called a ***supermartingale***.
- **Related definition**: A martingale is $L^p$ if $\mathbb{E}[\left|X_{n}  \right|^p]<+\infty$ for all $n$.
---
##### Properties
> [!lemma] Theorem 1
> Let $\{ X_{n} \}_{n}$ be an $\{ \mathcal{A}_{n} \}_{n}$ adapted sequence. Then, TFAE
> 1. $\{ X_{n} \}_{n}$ is a martingale.
> 2. $\mathbb{E}[X_{n}|\mathcal{A}_{m}]=X_{m}$ for all $1\leq m\leq n$. 

> [!proof]-
> We have that:
> 1. (1=>2): By [[Conditional Expectation|Proposition 4]], we have that: $$\mathbb{E}[X_{n}|\mathcal{A}_{m}]=\mathbb{E}[\mathbb{E}[X_{n}|\mathcal{A}_{n-1}]|\mathcal{A}_{m}]=\mathbb{E}[X_{n-1}|\mathcal{A}_{m}]=\dots=\mathbb{E}[X_{m+1}|\mathcal{A}_{m}]=X_{m}$$
> 2. (2=>1): Let $m:=n-1$. 
---
> [!lemma] Theorem 2
> Let $\{ X_{n} \}_{n}$ be a martingale. Then, 
> 1. $\mathbb{E}[X_{n}]=\mathbb{E}[X_{1}]$ for all $n$.

> [!proof]-
> We have that by [[Conditional Expectation|Proposition 4]]: $$\mathbb{E}[X_{n}]=\mathbb{E}[\mathbb{E}[X_{n}|\mathcal{A}_{1}]]=\mathbb{E}[X_{1}]$$