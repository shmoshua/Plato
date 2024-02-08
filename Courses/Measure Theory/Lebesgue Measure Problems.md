#MeasureTheory 

> [!problem] Problem 1
> For a $\mathcal{L}^n$-measurable set $E\subseteq \mathbb{R}^n$, prove or disprove:
> 1. If $\mathcal{L}^n(E)=0$, then $\mathcal{L}^n(\overline{E})=0$.
> 2. If $\mathcal{L}^n(\overline{E})=0$, then $\mathcal{L}^n(E)=0$.

> [!proof]- Answer
> We have:
> 1. False. Cantor set has measure 0 but the closure is $[0,1]$.
> 2. True, $0\leq\mathcal{L}^n(E)\leq \mathcal{L}^n(\overline{E})=0$.
---
> [!problem] Problem 2
> Let $\{ r_{n} \}_{n}$ be the enumeration of all rational numbers in $\mathbb{R}$.
> 1. Show that $\mathbb{R} \backslash\bigcup_{n=1}^{\infty}\left( r_{n}-\frac{1}{n^2},r_{n}+\frac{1}{n^2} \right)$ is never empty.
> 2. Show that $\mathbb{R} \backslash\bigcup_{n=1}^{\infty}\left( r_{n}-\frac{1}{n},r_{n}+\frac{1}{n} \right)$ can be empty or non-empty, depending on how the rationals are enumerated.

> [!proof]- Answer
> We have: 
> 1. By sub-additivity: $$\mathcal{L}^1\left(\bigcup_{n=1}^{\infty}\left( r_{n}-\frac{1}{n^2},r_{n}+\frac{1}{n^2} \right) \right)\leq \sum_{n=1}^{\infty} \frac{2}{n^2}=\frac{\pi^{2}}{3}$$
---
> [!probelm] Problem 3
> True or False: there exists a measure space $(X,\Sigma,\mu)$ s.t. there is no countable collection of $(X_{n})_{n}\subseteq\Sigma$ s.t. $\mu(X_{n})<+\infty$ and $X=\bigcup_{n=1}^{\infty}X_{n}$.

> [!proof]- Answer
> $\mu$ is the counting measure.
---
> [!problem] Problem 4
> Does there exist a open dense subset $A\subseteq[0,1]^{2}$ s.t. the complement $\mathcal{L}^2([0,1]^{2} \backslash A)>0$?

> [!proof]+
---
