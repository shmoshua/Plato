#Definition #MeasureTheory #FunctionalAnalysis 
> [!definition]
> For a set $X$ and $\mathcal{B}\subseteq \mathcal{P}(X)$ a [[Sigma Algebra|$\sigma$-algebra]], a function $\mu:\Sigma\to \mathbb{C}$ is a ***complex measure*** if:
> 1. $\mu(\varnothing)=0$ and
> 2. $\mu$ is [[Additive Functions|$\sigma$-additive]].
- **Remark**: Notice that in contrast to [[Positive Measure|positive measures]], $\sum_{n=1}^{}\mu(A_{n})\in \mathbb{C}$, the series has to converge, especially for any permutation of indices. Hence, $\sum_{n=1}^{}\left| \mu(A_{n}) \right|<+\infty$, i.e. it absolutely converges by Riemann.
- **Related definition**: For a complex measure $\mu:\Sigma\to \mathbb{C}$, the ***total variation*** of $\mu$ is a positive measure $\left| \mu \right|:\Sigma\to [0,+\infty]$ s.t. $$\left| \mu \right| (E):=\sup \left\{ \left.  \sum_{i=1}^{\infty}\left| \mu(E_{i}) \right|    \right|E=\bigsqcup_{i=1}^{\infty}E_{i},E_{i}\in \Sigma \right\}$$and $\left\| \mu \right\|:=\left| \mu \right|(X)$.
- **Related definition**: A complex measure $\mu:\mathcal{B}\to \mathbb{C}$ is ***regular*** if $\left| \mu \right|$ is [[Borel Regular Measure|regular]].
- **Related definition**: A ***signed measure*** is a complex measure $\lambda$ s.t. $\lambda(\Sigma)\subseteq \mathbb{R}$.
- **Remark**: Any complex measure $\mu$ can be written as $\mu=\mu_{1}+i \mu_{2}$ where $\mu_{1},\mu_{2}$ are signed measures.
- **Related definition**: Given a signed measure $\lambda:\Sigma\to \mathbb{R}$, we define: $$\lambda^+  = \frac{1}{2}(\left| \lambda \right| +\lambda),\quad \lambda^-  = \frac{1}{2}(\left| \lambda \right| -\lambda)$$
- **Related definition**: For $f\in L^1(X,\left| \mu \right|)$ with $\mu=\mu_{1}+i \mu_{2}=(\mu_{1}^+ - \mu_{1}^-)+i(\mu_{2}^+ -\mu_{2}^-)$, we define: $$\int_{X}^{} f \, d\mu:=\left( \int_{X}^{} f \, d\mu^+_{1}-\int_{X}^{} f \, d\mu^-_{1}  \right) +i\left( \int_{X}^{} f \, d\mu^+_{2}-\int_{X}^{} f \, d\mu^-_{2}  \right)  $$
---
##### Properties
> [!lemma] Theorem 1
> Let $\mu:\Sigma\to \mathbb{C}$ be a complex measure. Then, 
> 1. $\left| \mu(E) \right|\leq \left| \mu \right|(E)$ for all $E\in \Sigma$.
> 1. $\left| \mu \right|$ is a positive measure on $\Sigma$.
> 2. $\|\mu \|=\left| \mu \right|(X)<+\infty$

> [!proof]-
> > [!lemma] 
> > Let $z_{1},\dots,z_{n}\in \mathbb{C}$. Then, there exists a subset $S\subseteq[n]$ s.t. $$\left| \sum_{k\in S}^{}z_{i} \right| \geq \frac{1}{\pi}\sum_{k=1}^{n}\left| z_{k} \right| $$
> 
> > [!proof]-
> > Let $z_{k}=\left| z_{k} \right|e^{i\alpha_{k}}$ for all $k\in [n]$ s.t. $-\pi<\alpha_{k}\leq \pi$. Then, for $-\pi\leq\theta\leq \pi$, we define: $$S(\theta):=\{ k\in [n]:\cos(\alpha_{k}-\theta)>0 \}$$Then,
> > $$\begin{align}\left| \sum_{k\in S(\theta)}^{}z_{k} \right|&=\left| \sum_{k\in S(\theta)}^{}z_{k}e^{-i\theta} \right| \\&\geq \text{Re}\left( \sum_{k\in S(\theta)}^{}z_{k}e^{-i\theta} \right) \\&=\sum_{k\in S(\theta)}^{}\left| z_{k} \right| \cos(\alpha_{k}-\theta)\\& =\sum_{k=1}^{n}\left| z_{k} \right| \max\{ 0,\cos(\alpha_{k}-\theta) \}\\&=: f(\theta)\end{align}$$Then, $f:[-\pi,\pi]\to[0,+\infty)$ is continuous and there exists $\theta_{0}$ s.t. $f(\theta_{0})\geq f(\theta)$ for all $\theta\in [-\pi,\pi]$. Indeed, $$\begin{align}f(\theta_{0})\geq \frac{1}{2\pi}\int_{-\pi}^{\pi}f(\theta)  \, d\theta&=\sum_{k=1}^{n}\left| z_{k} \right| \frac{1}{2\pi}\int_{-\pi}^{\pi}\max\{ 0,\cos(\alpha_{k}-\theta) \}  \, d\theta \\&=\frac{1}{\pi}\sum_{k=1}^{n}\left| z_{k} \right|\end{align} $$ By choosing $S:=S(\theta_{0})$, we prove the statement.
> 
> 1. By definition of total variation.
> 2. Let $E=\bigsqcup_{i=1}^{\infty}E_{i}$ where $E_{i}\in \Sigma$. Then, one easily sees that $\left| \mu  \right|$ is $\sigma$-additive.
> 
> 3. We will show that for any $E\in \Sigma$ with $\left| \mu \right|(E)=+\infty$, there exists $A,B\in \Sigma$ s.t. $E=A\sqcup B$ and $\left| \mu(A) \right|,\left| \mu(B) \right|>1$. 
>    
>    Let $t:=\pi(1+\left| \mu(E) \right|)$. Since $\left| \mu \right|(E)>t$, there is a partition $E=\bigsqcup_{k=1}^{\infty}E_{k}$ with $E_{k}\in \Sigma$ with $$\sum_{k=1}^{\infty}\left| \mu(E_{k}) \right| >t$$and hence there exists $n\geq 1$ with $\sum_{k=1}^{n}\left| \mu(E_{k}) \right|>t$. Applying the above lemma to $z_{k}:=\mu(E_{k})$, there exists $S\in [n]$ s.t. $$\left| \sum_{k\in S}^{}\mu(E_{k}) \right| \geq \frac{1}{\pi}\sum_{k=1}^{n}\left| \mu(E_{k}) \right| > \frac{t}{\pi}$$Let $A:=\bigsqcup_{k\in S}^{}E_{k}$. Then, $\left| \mu(A) \right|> \frac{t}{\pi}=1+\left| \mu(E) \right|$ and set $B:= E \backslash A$. Then, $$\left| \mu(B) \right| =\left| \mu(E)-\mu(A) \right| \geq \left| \mu(A) \right| -\left| \mu(E) \right| >1$$
>    
>    Therefore, assume that $\left| \mu \right|(X)=\infty$. Then, $X=A_{1}\sqcup B_{1}$ with $\left| \mu(A_{1}) \right|,\left| \mu(B_{1}) \right|>1$.  Wlog, $\left| \mu \right|(B_{1})=+\infty$. Then, $B_{1}=A_{2}\sqcup B_{2}$ with $\left| \mu(A_{2}) \right|,\left| \mu(B_{2}) \right|>1$ and wlog $\left| \mu \right|(B_{2})=+\infty$. Therefore, we construct: $(A_{n})_{n}\subseteq \Sigma$ which are pairwise disjoint. This is a contradiction to $\sum_{n=1}^{}\left| \mu(A_{n}) \right|\in \mathbb{C}$. 

---
> [!lemma] Theorem 3 (Riesz-Markov-Kakutani Representaton)
> Let $X$ be a separable locally compact metric space and let $\Lambda: C_{00}(X)\to \mathbb{C}$ be a positive linear functional, i.e. if $f\geq 0$ then $\Lambda(f)\geq 0$. Then, 
> 1. there exists a unique [[Radon measure]] $\lambda$ on $(X,\mathcal{B}_{X})$ s.t. $$\Lambda(f)=\int_{X}^{} f \, d\lambda,\quad \forall f\in C_{00}(X) $$with the following properties:
> 	- for every $E\in \mathcal{B}_{X}$, $$\lambda(E)=\inf\{ \lambda (V): E \subseteq V, V\text{ open} \}=\sup\{ \lambda(K): K\subseteq E, K\text{ compact} \}$$
> 	- for every open $E\subseteq X$, $$\lambda(E)=\sup\{ \Lambda(f):f\in C_{00}(X), 0\leq f\leq \chi_{E} \}$$

---

> [!lemma] Theorem 4 (Riesz Representation)
> Let $X$ be [[Locally Compact Hausdorff Space|locally compact Hausdorff]] and $\mathcal{B}$ a [[Borel Sigma-Algebra|Borel $\sigma$-algebra]]. For every $\Phi\in C_{0}(X)^{*}$, there exists a unique complex regular measure $\mu:\mathcal{B}\to \mathbb{C}$ s.t. $$\Phi(f)=\int_{X}^{} f \, d\mu,\quad \forall f\in C_{0}(X) $$and $\left\| \Phi \right\|=\left| \mu \right|(X)$.
---

> [!lemma] Theorem 1 (Radon-Nykodym)
> Let $(X,\Sigma)$ be a measure space, $\mu:\Sigma\to[0,+\infty]$ a non-negative finite measure and $\nu:\Sigma\to \mathbb{C}$ a complex measure s.t. $$\left| \nu(A) \right|\leq \mu(A)\quad \forall A\in \Sigma$$
> Then, $d\nu=\rho d\mu$ where $\left| \rho \right|\leq 1$. Moreover, if $\nu$ is positive, then $0\leq\rho\leq 1$

> [!proof]-
> Let $f=\sum_{a\in\mathbb{C}}^{}a\chi_{f^{-1}[\{ a \}]}$ be a [[simple function]]. Then, $$\left| \int_{X}^{} f \, d\nu  \right| \leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \left| \nu(f^{-1}[\{ a \}]) \right|\leq \sum_{a\in \mathbb{C}}^{}\left| a \right| \mu(f^{-1}[\{ a \}])=\int_{X}\left| f \right|  \, d\mu  $$
---
> [!lemma] Theorem
> Let $\lambda:\Sigma\to \mathbb{R}$ be a signed measure. Then, $X=A \sqcup B$ with $A,B\in \Sigma$ s.t. for all $E\in \Sigma$:
> 1. $\lambda^+(E)=\lambda(E\cap A)$ and
> 2. $\lambda^-(E)=-\lambda(E\cap B)$
---