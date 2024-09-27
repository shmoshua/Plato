#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]]. For a [[Measure Space|measurable space]]  $(E,\mathcal{E})$, 
> 1. a ***random variable*** with values in $E$ is a [[measurable function]] $X:\Omega\to E$.
- **Related definition**: The ***distribution*** $\mathbb{P}_{X}$ is the pushforward probability measure on $(E,\mathcal{E})$, i.e. $$\mathbb{P}_{X}(B):=\mathbb{P}(X ^{-1}(B)),\quad \forall B\in \mathcal{E}$$
- **Related definition**: $\sigma(X)$ denotes the smallest [[Sigma Algebra|$\sigma$-algebra]] on $\Omega$ s.t. $X$ becomes measurable, i.e. $\sigma(X):=\{ X ^{-1}(B):B\in \mathcal{E} \}$. This can be extended to a group of random variables, e.g. $\sigma(X_{1},\dots,X_{n})$.
---
##### Properties
> [!lemma] Proposition 1
> Let $X:\Omega\to(E,\mathcal{E})$ be a random variable and $Y:\Omega\to \mathbb{R}$ real random variable. Then, TFAE:
> 1. $Y$ is $\sigma(X)$-measurable.
> 2. there exists a measurable function $f\varepsilon-$