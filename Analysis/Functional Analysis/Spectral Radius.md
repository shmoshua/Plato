#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a [[Banach algebra]]. Then, for $x\in A$, the ***spectral radius*** of $x$ is defined as: $$r_{A}(x):=\inf_{n\geq 1}\left\| x^n \right\|^{1/n} $$
---
##### Properties
> [!lemma] Proposition 1 (Spectral Radius Formula)
> For $x\in A$, we have that:
> 1. $r_{A}(x)$ is well-defined
> 2. $\lim_{ n \to \infty }\left\| x^n \right\|^{1/n}=r_{A}(x)$

> [!proof]-
> Let $f:\mathbb{N}^{*}\to \mathbb{R}_{>0}$ s.t. $f(n+m)\leq f(n)f(m)$ for all $n,m\geq 1$. Then, $\lim_{ n \to \infty }f(n)^{1/n}$ exists and equals $\inf\{ f(n)^{1/n}:n\geq 1 \}$.
> 
> We can assume that $f(1)>0$. Otherwise, $f(1)=0$ then $f(n)=0$ for all $n\geq 1$. 
> 
> Let $r:=\text{inf}\{ f(n)^{1/n} :n\geq 1\}\geq 0$. Let $\varepsilon>0$. Let $k\geq 1$ s.t. $f(k)^{1/k}<r+\varepsilon$. We will show that: $$\limsup_{ n \to \infty } f(n)^{1/n}<r$$Now, let $n>k$ and $n:=ak+b$ where $a\geq 1$ and $0\leq b<k$. Then, $$f(n)^{1/n}=f(ak+{b})^{1/n}\leq f(ak)^{1/n}f(b)^{1/n}\leq f(k)^{a/n}f(1)^{b/n}=(f(k)^{1/k})^{1-b/n}f(1)^{b/n}\to f(k)^{1/k}$$Therefore, $$\limsup_{ n \to \infty } f(n)^{1/n}\leq f(k)^{1/k}<r+\varepsilon$$As $\varepsilon$ was arbitrary, this concludes the proof.
---
> [!lemma] Lemma 2
> Let $A$ be a unital [[Banach algebra]] and $x\in A$ with $r_{A}(x)<1$. Then, 
> 1. $e-x$ is invertible and
> 2. $(e-x)^{-1}=\sum_{n=1}^{\infty}x^n$ where $x^0=e$.

> [!proof]+
> We have:
> 1. $\sum_{n=0}^{\infty}a_{n}$ in a Banach space is convergent if $S_{N}:=\sum_{n=0}^{N}a_{n}$ converges.
> 2. $\sum_{n=0}^{\infty}a_{n}$ in a Banach space is absolutely convergent if $\sum_{n=0}^{\infty}\left\| a_{n} \right\|$ converges.
> 3. absolute convergence => convergent.
