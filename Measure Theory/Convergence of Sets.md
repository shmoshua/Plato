#Definition #MeasureTheory 

> [!definition]
> The limit of supremum of sets are defined as follows: 
> $$\limsup_{ n \to \infty } A_{n}=\bigcap_{n=1}^{\infty}\bigcup_{m=n}^{\infty}A_{m}$$
> Similarly, for infimum, we have:
> $$\liminf_{ n \to \infty } A_{n}=\bigcup_{n=1}^{\infty}\bigcap_{m=n}^{\infty}A_{m}$$
> If $\limsup_{ n \to \infty }A_{n}=\liminf_{ n \to \infty }A_{n}=L$, then we say $\lim_{ n \to \infty }A_{n}=L$ and that $(A_{n})_{n}$ converges to $L$.
---
##### Properties
> [!lemma] Proposition 1
> We have that:
> 1. $\liminf_{ n \to \infty }A_{n} \subseteq\limsup_{ n \to \infty }A_{n}$
> 2. If $(A_{n})_{n}$ is increasing, then we have: $$\lim_{ n \to \infty } A_{n}=\bigcup_{n=1}^{\infty}A_{n}$$
> 3.  If $(A_{n})_{n}$ is decreasing, then we have: $$\lim_{ n \to \infty } A_{n}=\bigcap_{n=1}^{\infty}A_{n}$$

>[!proof]-
>Note that:
>1. Follows from the definition
>2. As $(A_{n})_{n}$ is increasing, we have $\bigcup_{m=1}^{\infty}A_{m}\subseteq \bigcup_{m=n}^{\infty}A_{m}$ for all $n$. Therefore, $$\limsup_{ n \to \infty } A_{n}=\bigcap_{n=1}^{\infty}\bigcup_{m=n}^{\infty}A_{m}=\bigcup_{m=1}^{\infty}A_{m}$$ On the other hand, $$\liminf_{ n \to \infty } A_{n}=\bigcup_{n=1}^{\infty}\left(\bigcap_{m=n}^{\infty}A_{m}\right)=\bigcup_{n=1}^{\infty}A_{n}$$
>3. As $(A^c_{n})_{n}$ is increasing, it follows from 2. 
---
> [!lemma] Proposition 2
> Let $X$ be a set and $\{ A_{n} \}_{n=1}^\infty \subseteq \mathcal{P}(X)$. We have: $$\begin{align}\limsup_{ n \to \infty } A_{n}&=\{\left.  x\in X \right| \forall N\geq 1,\exists n\geq N: x\in A_{n} \}\\\liminf_{ n \to \infty } A_{n}&=\{\left.  x\in X \right| \exists N\geq 1,\forall  n\geq N: x\in A_{n} \}\end{align}$$

> [!proof]-
> Let $x\in \limsup_{n\to \infty} A_n=\bigcap ^\infty_{N=1}\bigcup^\infty _{n=N}A_n$. Then for all $N\ge 1$, $x\in\bigcup _{n=N}^\infty A_n$. Therefore, there exists $n\ge N$ s.t. $x\in A_n$. Consequently, $x\in\{x\in X\ |\ \forall N\ge 1, \exists n\ge N:x\in A_n\}$.
> 
> Conversely, let $x\in \{x\in X\ |\ \forall N\ge 1, \exists n\ge N:x\in A_n\}$. Then, for any $N\ge 1$, $x\in \bigcup _{n=N}^\infty A_n$. Therefore, $x\in \bigcap ^\infty_{N=1}\bigcup^\infty _{n=N}A_n=\limsup_{n\to \infty} A_n$.
> 
> For $\liminf_{n\to \infty }A_n=\{x\in X\ |\ \exists N\ge 1, \forall n\ge N:x\in A_n\}$, consider $\{A^c\}^\infty _{n=1}$. Then,$$ \liminf_{n\to\infty}A_n=\bigcup _{N=1}^\infty \bigcap^\infty _{n=N}A_n=\left(\bigcap ^\infty_{N=1}\bigcup^\infty _{n=N}A_n^c\right)^c=(\limsup _{n\to \infty}A^c_n)^c $$
> Therefore, it is equivalent to $\{x\in X\ |\ \forall N\ge 1, \exists n\ge N:x\in A^c_n\}^c$, which could be also written as: $\{x\in X\ |\ \exists N\ge 1, \forall n\ge N:x\in A_n\}$.
---
> [!lemma] Corollary 3
> We have that: $$\liminf_{ n \to \infty } A_{n}\subseteq \limsup_{ n \to \infty } A_{n}$$

> [!proof]-
> By Proposition 2, for any $x\in \{x\in X\ |\ \exists N\ge 1, \forall n\ge N:x\in A_n\}$, we know that $x\in A_n$ for all $n\ge N$. Then, for all $M\ge 1$, there is $m\ge M$ s.t. $x\in A_m$. Therefore, $x\in \limsup_{n\to \infty }A_n$.
---