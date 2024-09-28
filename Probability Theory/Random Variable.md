#Definition #ProbabilityTheory 

> [!definition]
> Let $(\Omega,\mathcal{A},\mathbb{P})$ be a [[probability space]]. For a [[Measure Space|measurable space]]  $(E,\mathcal{E})$, 
> 1. a ***random variable*** with values in $E$ is a [[measurable function]] $X:\Omega\to E$.

^4b9e44

- **Related definition**: The ***distribution*** $\mathbb{P}_{X}$ is the pushforward probability measure on $(E,\mathcal{E})$, i.e. $$\mathbb{P}_{X}(B):=\mathbb{P}(X ^{-1}(B)),\quad \forall B\in \mathcal{E}$$ ^a13060
- **Related definition**: $\sigma(X)$ denotes the smallest [[Sigma Algebra|$\sigma$-algebra]] on $\Omega$ s.t. $X$ becomes measurable, i.e. $\sigma(X):=\{ X ^{-1}(B):B\in \mathcal{E} \}$. This can be extended to a group of random variables, e.g. $\sigma(X_{1},\dots,X_{n})$.
---
##### Properties
> [!lemma] Proposition 1 
> Let $X:\Omega\to(E,\mathcal{E})$ be a random variable and $Y:\Omega\to \mathbb{R}$ real random variable. Then, TFAE:
> 1. $Y$ is $\sigma(X)$-measurable.
> 2. there exists a measurable function $f: E\to \mathbb{R}$ s.t. $Y=f(X)$.

> [!proof]-
> We have:
> 1. Assume that $Y$ is $\sigma(X)$-measurable. If $Y$ is simple, then we can write $Y=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{A_{i}}$ where $\lambda_{i}$ are distinct reals and $A_{i}:=Y^{-1}(\lambda_{i})\in \sigma(X)$ for all $i\in[n]$. Then, for any $i\in[n]$, we can find $B_{i}\in\mathcal{E}$ s.t. $A_{i}=X ^{-1}(B_{i})$. We have that: $$Y=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{A_{i}}=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{X ^{-1}(B_{i})}=\sum_{i=1}^{n}\lambda_{i}\mathbb{1}_{B_{i}}\circ X=f\circ X$$
>    In the general case, $Y$ is the pointwise limit of simple random variables $(Y_{n})_{n}$ that are $\sigma(X)$-measurable. Write $Y_{n}=f_{n}\circ X$. Then, $f_{n}: E\to \mathbb{R}$ are measurable functions. We define: $$f(x):=\begin{cases}\lim_{ n \to \infty } f_{n}(x)&\text{if it exists}\\0&\text{otherwise}\end{cases}$$Then, $f$ is measurable and for every $\omega\in \Omega$, $X(\omega)$ belongs to the set of $x\in E$ s.t. $\lim_{ n \to \infty }f_{n}(x)$ exists, because $\lim_{ n \to \infty }f_{n}(X(\omega))=\lim_{ n \to \infty }Y_{n}(\omega)=Y(\omega)$, which exists. 
>    
>    Moreover, $$f(X(\omega))=\lim_{ n \to \infty } f_{n}(X(\omega))=Y(\omega)$$which proves the statement.
>    
> 2. the composition of measurable functions is measurable.
---
