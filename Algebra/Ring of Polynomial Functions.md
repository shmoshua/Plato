#Definition #Algebra 

> [!definition]
> Let $K$ be a [[field]], $\mathbb{A}_{K}^n$ an [[affine space]] over $K$. For a [[variety]] $X\subseteq \mathbb{A}_{K}^n$, the ***ring of polynomial functions*** or ***coordinate ring*** of $X$ is defined as: $$A(X):=K[x_{1},\dots,x_{n}] / I(X)$$

^56793e

- **Remark**: $f,g\in K[x_{1},\dots,x_{n}]$ are equal if and only if they equal on $X$. So $\overline{f}\in A(X)$ is equivalent to a function $X\to K,x\mapsto f(x)$.  ^ca999a
---
##### Properties
> [!lemma] Proposition 1
> 
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