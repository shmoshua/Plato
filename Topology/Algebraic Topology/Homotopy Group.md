#Definition #AlgebraicTopology 

> [!definition]
> Let $k\geq 1$. For a [[topological space]] $X$ and a base point $x_{0}\in X$, 
> 1. the ***$n$-th homotopy group*** is a group $\pi_{n}(X,x_{0}):=[(I^n,\partial I^n),(X,x_{0})]$ where $I^n:=[0,1]^n$ and $[(X,A),(Y,B)]$ denotes the set of homotopy classes $f:X\to Y$ where $f(A)\subseteq B$.

^0f2b58

- **Remark**: Using $I^n / \partial I^n \sim S^n$, we have that $\pi_{n}(X,x_{0}):=[(S^n,*),(X,x_{0})]$ where $*\in S^n$ is a distinct base point. ^405010
- **Remark**: If $n=1$, we have the [[fundamental group]]. ^fab5de
- **Remark**: For $n\geq 2$, $\pi_{n}(X,x_{0})$ is [[Abelian Group|abelian]]. ^bef566
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\pi_{n}(X,x_{0})$ is a group with concatenation.

^8bcc93

> [!proof]-
> Let $f,g:(I^n,\partial I^n)\to(X,x_{0})$. Then, we define the concatenation as: $$f*g:(I^n,\partial I^n)\to(X,x_{0}),\quad (t_{1},\dots,t_{n})\mapsto \begin{cases}f(t_{1},\dots,t_{n-1},2t_{n})&0\leq t_{n}\leq 1 / 2\\g(t_{1},\dots,t_{n-1},2t_{n}-1)&1 / 2 \leq t_{n} \leq 1\end{cases}$$Then, for $a,b\in \pi_{n}(X,x_{0})$, with $f,g:(I^n,\partial I^n)\to(X,x_{0})$ s.t. $[f]=a$ and $[g]=b$, we have that $a\cdot b:=[f*g]$.
> 
> The rest follows analogous to $\pi_{1}(X,x_{0})$. [[Fundamental Group|proof]].

^f5a464

---
##### Examples
> [!h] Example 1
> We have that:
> 1. $\pi_{n}(S^k,*)=\{ 0 \}$ for $n\leq k$.
> 2. $\pi_{n}(S^n,*)\cong \mathbb{Z}$
> 3. $\pi_{3}(S^2,*)\cong \mathbb{Z}$
> 4. $\pi_{n+2}(S^n,*)\cong \mathbb{Z}_{2}$ for all $n\geq 2$
> 5. $\pi_{n+3}(S^n,*)\cong \mathbb{Z}_{24}$ for all $n\geq 5$
> 6. $\pi_{7}(S^4,*)\cong \mathbb{Z}\oplus \mathbb{Z}_{12}$

^6de056
