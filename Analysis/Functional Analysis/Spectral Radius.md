#Definition #FunctionalAnalysis 
> [!definition]
> Let $A$ be a [[Banach algebra]]. Then, for $x\in A$, the ***spectral radius*** of $x$ is defined as: $$r_{A}(x):=\inf_{n\geq 1}\left\| x^n \right\|^{1/n} $$
> For $x\in A$, the ***spectral radius*** is defined as:$$\|x\|_{\text{sp}}:=\max\{ \left| \lambda \right| :\lambda\in \text{Sp}_{A}(x) \}$$
---
##### Properties
> [!lemma] Proposition 1 
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

> [!proof]- Proof (incomplete)
> We have:
> 1. $\sum_{n=0}^{\infty}a_{n}$ in a Banach space is convergent if $S_{N}:=\sum_{n=0}^{N}a_{n}$ converges.
> 2. $\sum_{n=0}^{\infty}a_{n}$ in a Banach space is absolutely convergent if $\sum_{n=0}^{\infty}\left\| a_{n} \right\|$ converges.
> 3. absolute convergence => convergent.
---
> [!lemma] Lemma 3
> Let $A$ be a unital Banach algebra. 
> 1. Then, the map $G(A)\to G(A), y\mapsto y^{-1}$ is Lipschitz continuous in some neighborhood of every $x\in G(A)$.
> 2. More precisely, if $\left\| y-x \right\| \leq \frac{1}{2}\left\|x ^{-1} \right\| ^{-1}$, then: $$\left\| y^{-1}-x ^{-1} \right\| \leq 2\left\|  x ^{-1} \right\|^2 \left\| y-x \right\| $$
> 3. Let $x\in G(A)$. If $y\in A$ satisfies $\left\| y-x \right\|<\left\| x ^{-1} \right\|^{-1}$. Then, $y\in G(A)$, in particular $G(A)$ is open in $A$.

> [!proof]-
> We have
> 1. $(y^{-1}-x ^{-1})=y^{-1}(x-y) x ^{-1}$ and: $$\left\| y^{-1} \right\| -\left\| x ^{-1} \right\|\leq \left\| y^{-1}-x ^{-1} \right\| \leq \left\| y^{-1} \right\|\left\| x-y \right\| \left\| x ^{-1} \right\| \leq \frac{1}{2}\left\| y^{-1} \right\|  $$Therefore, $\left\| y^{-1} \right\|\leq 2\left\| x ^{-1} \right\|$ and $\left\| y^{-1}-x ^{-1} \right\|\leq 2\left\| x ^{-1} \right\|^2\left\| x-y \right\|$
> 2. We have: $e-x ^{-1}y=x ^{-1}(x-y)$. Therefore, $$\left\| e-x^{-1}y \right\| \leq \left\| x^{-1} \right\| \left\| x-y \right\| <1$$Therefore, from Lemma 2, $e-(e-x^{-1}y)=x^{-1}y\in G(A)$. Therefore, $y\in G(A)$. 
- **Remark**: $G(A)$ is an open subset of $A$ and multiplication and inversion are continuous on $G(A)$.
---
