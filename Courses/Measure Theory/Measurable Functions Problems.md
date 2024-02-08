#MeasureTheory 

> [!problem] Problem 1
> True or False: For a Borel measure $\mu$, if $f:[0,1]\to \mathbb{R}$ is continuous $\mu$-a.e., $f$ is $\mu$-measurable.

> [!proof]- Answer
>  Let $D$ be the discontinuity points in $[0,1]$. Then, $\mu(E)=0$ and  We have that: $$f^{-1}[(-\infty,a)]=O\cap[0,1]$$where $O$ is open. Then, of course $O\cap[0,1]$ is measurable.
---
> [!problem] Problem 2
> True or False: Let $f:[0,1]\to \mathbb{R}$. If $\{ x\in [0,1]:f(x)=c \}$ is measurable for every $c\in \mathbb{R}$, then $f$ is measurable.

> [!proof]- Answer
> Let $P$ be the Vitali set. We then set: $$f(x)=\begin{cases}x&x\in P\\-x&x\notin P\end{cases}$$Then, $f^{-1}[\{ c \}]$ is measurable for every $c\in \mathbb{R}$. But, $f^{-1}((0,\infty))$ is not measurable.
---
> [!problem] Problem 3
> True or False: There exists a sequence $\{ f_{k} \}_{k}$ of $\mathcal{L}^n$-measurable functions s.t. $f_{k}\xrightarrow{\mu}{0}$ in $x\in \mathbb{R}$ but no subsequence converges uniformly on any subset of positive measure?

> [!proof]-
> False by Egoroff.

---
> [!problem] Problem 4
> True or False: if $f:[0,\infty)\to \mathbb{R}$ is differentiable, then $f'$ is measurable.

> [!proof]- Answer
> True, $f'$ is a limit of measurable functions.
---
> [!problem] Problem 5
> Does there exist a non-measurable function $f\geq 0$ s.t. $\sqrt{ f }$ is measurable?

> [!proof]- Answer
> No, if $\sqrt{ f }$ is measurable, $f$ is measurable.