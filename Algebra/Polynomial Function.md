#Definition #Algebra 

> [!definition]
> Let $X\subseteq \mathbb{A}^n_{K}$ be an [[Variety|affine variety]].
> 1. a ***polynomial function*** on $X$ is a map $X\to K$ of the form $x\mapsto f(x)$ for some $f\in K[x_{1},\dots,x_{n}]$.
> 2. the ***ring of polynomial functions/coordinate ring*** is given by $A(X):=K[x_{1},\dots,x_{n}] / I(X)$.

^56793e

- **Remark**: $A(X)$ is more often regarded as a $K$-algebra.

---
##### Properties
![[Variety#^4ec3ba]]
![[Variety#^89aa91|p]]


---
##### Examples
> [!h] Example 1
> Let $a=(a_{1},\dots,a_{n})\in \mathbb{A}_{K}^n$. Then, 
> 1. $I(a)=(x_{1}-a_{1},\dots,x_{n}-a_{n})$
> 2. $A(a)=K[x_{1},\dots,x_{n}] / I(a)\cong K$

^4b2402

> [!proof]-
> We have:
> 1. $\subseteq$: if $f(a)=0$, then $f=0\mod (x_{1}-a_{1},\dots,x_{n}-a_{n})$.
> 2. $\supseteq$: if $f\in (x_{1}-a_{1},\dots,x_{n}-a_{n})$, then $f=\sum_{i}^{}(x_{i}-a_{i})f_{i}$ and $f(a)=0$.

^39a3bf

---