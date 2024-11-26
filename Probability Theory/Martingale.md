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

---
> [!lemma] Theorem 3 (Azuma-Hoeffding)
> Let $(X_{n})_{n}$ be a martingale w.r.t $(\mathcal{A}_{n})_{n}$. Let $(A_{n})_{n},(B_{n})_{n}$ are predictable w.r.t. $(\mathcal{A}_{n})_{n}$. Further, let $c_{n}>0$ s.t. 
> 1. $A_{n}\leq X_{n}-X_{n-1}\leq B_{n}$ almost surely for all $n\geq 1$
> 2. $B_{n}-A_{n}\leq c_{n}$ almost surely for all $n\geq 1$
> 
> Then, for all $\lambda\geq 0$, $$\mathbb{P}(X_{n}\geq X_{0}+\lambda)\leq \exp \left( -\frac{2\lambda^{2}}{\sum_{i\leq n}c_{i}^{2}} \right) $$

> [!proof]-
> By [[Expected Value|Markov]], we have that for any $s>0$: $$\mathbb{P}(X_{n}-X_{0}\geq \lambda)=\mathbb{P}(e^{s(X_{n}-X_{0})}\geq e^{s\lambda})\leq \frac{\mathbb{E}[e^{s(X_{n}-X_{0})}]}{e^{s\lambda}}=\frac{\mathbb{E}\left[ e^{s\sum_{i=1}^{n}(X_{i}-X_{i-1})} \right]}{e^{s\lambda}}$$Then, $e^{s\sum_{i=1}^{n-1}(X_{i}-X_{i-1})}$ is a bounded $\mathcal{A}_{n-1}$-measurable random variable and by [[Conditional Expectation|Theorem 1.2]], $$\mathbb{E}\left[ e^{s\sum_{i=1}^{n}(X_{i}-X_{i-1})} \right]=\mathbb{E}[\mathbb{E}[e^{s(X_{n}-X_{n-1})}|\mathcal{A}_{n-1}]e^{s\sum_{i=1}^{n-1}(X_{i}-X_{i-1})}]$$However, as $A_{n}\leq X_{n}-X_{n-1}\leq B_{n}$ almost surely where $B_{n}-A_{n}\leq c_{n}$, we have by [[Expected Value|Hoeffding's Lemma]], $$\mathbb{E}[e^{s(X_{n}-X_{n-1})}|\mathcal{A}_{n-1}]\leq \exp \left( s\underbrace{ \mathbb{E}[X_{n}-X_{n-1}] }_{ =\mathbb{E}[X_{n}]-\mathbb{E}[X_{n-1}]=0 }+\frac{s^{2} c_{n}^{2}}{8}\right) =\exp \left( \frac{s^2 c_{n}^{2}}{8} \right)  $$where $\mathbb{E}[X_{n}]=\mathbb{E}[X_{n-1}]$ by Theorem 2. Therefore, by induction, we have that: $$\mathbb{E}\left[ e^{s\sum_{i=1}^{n}(X_{i}-X_{i-1})} \right]\leq \exp \left( \frac{s^{2}\sum_{i=1}^{n}c_{i}^{2}}{8} \right) $$Then, $\mathbb{P}(X_{n}-X_{0} \geq \lambda)\leq  \exp \left( \frac{s^{2}\sum_{i=1}^{n}c_{i}^{2}}{8}-s\lambda \right)$. By choosing $s=\frac{4\lambda}{\sum_{i=1}^{n}c_{i}^{2}}$ gives us: $$\mathbb{P}(X_{n}-X_{0}\geq \lambda)\leq \exp \left( -\frac{2\lambda^{2}}{\sum_{i=1}^{n}c_{i}^{2}} \right) $$

---
> [!lemma] Theorem 4 (McDiarmid's Inequality)
> Let $X_{1},\dots,X_{n}$ be [[Independence|independent random variables]] where $X_{i}$ is $\mathcal{X}_{i}$ valued for all $i\in[n]$. For $X:=(X_{1},\dots,X_{n})$ and a measurable function $f:\mathcal{X}_{1}\times\dots \times \mathcal{X}_{n}\to \mathbb{R}$ s.t. 
> 1. $\|D_{i}f\|_{\infty}<+\infty$ for all $i\in[n]$ where $D_{i}f:\mathcal{X}_{1}\times\dots \times \mathcal{X}_{n}\to \mathbb{R}$ $$D_{i}f(x):=\sup_{y\in \mathcal{X}_{i}}f(x_{1},\dots,x_{i-1},y,x_{i+1},\dots,x_{n})-\inf_{z\in \mathcal{X}_{i}}f(x_{1},\dots,x_{i-1},z,x_{i+1},\dots,x_{n})$$
>
>Then, for all $\lambda\geq 0$: $$\mathbb{P}(f(X)\geq \mathbb{E}[f(X)]+\lambda)\leq \exp \left( -\frac{\lambda^{2}}{2\sum_{i=1}^{n}\left\| D_{i}f \right\| ^2_{\infty}} \right) $$

> [!proof]+
> Let $Z_{n}:=\mathbb{E}[f(X)| \mathcal{A}_{n}]$ where $\mathcal{A}_{n}:= \sigma(X_{1},\dots,X_{i})$. We show that $(Z_{n})_{n}$ is a martingale. We have that $(Z_{n})_{n}$ is $(\mathcal{A}_{n})_{n}$-adapted by definition. Then, by [[Conditional Expectation|Proposition 4]], $$\mathbb{E}[Z_{n+1}|\mathcal{A}_{n}]=\mathbb{E}[\mathbb{E}[f(X)|\mathcal{A}_{n+1}]|\mathcal{A}_{n}]=\mathbb{E}[f(X)|\mathcal{A}_{n}]=Z_{n}$$Let $X'_{i}$ be independent of $X_{i}$. Consider $X^{(i)}:=(X_{1},\dots,X_{i-1},X_{i}',\dots,X_{n})$. Then, $$\mathbb{E}[f(X^{(i)})|\mathcal{A}_{i-1}]=$$
> 
$$\begin{align}Z_{i}-Z_{i-1}&=\mathbb{E}[f(X)|\mathcal{A}_{i}]-\mathbb{E}[f(X)|\mathcal{A}_{i-1}]\end{align}$$
