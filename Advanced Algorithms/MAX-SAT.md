#Definition #Algorithms 

> [!definition]
> Let $x_{1},\dots,x_{n}$ be variables and $c_{1},\dots,c_{m}$ be clauses on the variables. Further, let $w:[m]\to \mathbb{R}$ be the ***weight*** function. 
> 1. The ***MAX-SAT problem*** aims to find: $$\alpha_{\text{OPT}}\in \underset{ \alpha \text{ assignment} }{ \arg\max }\sum_{j:c_{j}\text{ satisfied by }\alpha}^{}w_{j}$$
---
##### Properties
> [!lemma] Proposition 1
> Consider the following algorithm:
>    ```pseudo
>    \begin{algorithm} \caption{Random($I$)} 
>    \begin{algorithmic}
>    \State Pick $\alpha(x_{i})$ from $\{ 0,1 \}$ uniformly at random.
>    \Return $\alpha$
>    \end{algorithmic}
>    \end{algorithm}
>    ```
> 
> Then, 
> 1. $\mathbb{P}(\alpha \text{ satisfies }c_{j})=1-2^{-\left| c_{j} \right|}$ for all $j\in[m]$.
> 2. $\text{Random}$ is a 2-[[Approximation Algorithm|approximation algorithm]]. 
> 3. By repeating $\text{Random}$ $n$ times and taking the maximum, 

> [!proof]-
> We have that:
> 1. $\alpha$ does not satisfy $c_{j}$ if and only if $\alpha$ gives false to all literals in $c_{j}$. This happens with probability $\frac{1}{2^\left| c_{j} \right|}$. This proves the statement.
> 2. For an assignment $\alpha$, let $S(\alpha):=\{ j\in[m]:\alpha \text{ satisfies }c_{j} \}$. Then, $$\mathbb{E}[w(S(\alpha))]=\sum_{j=1}^{m}w_{j}\cdot \mathbb{P}(\alpha \text{ satisfies }c_{j})=\sum_{j=1}^{m}w_{j}\left( 1-\frac{1}{2^{\left| c_{j} \right| }} \right)\geq \frac{1}{2}\sum_{j=1}^{m}w_{j}\geq \frac{1}{2}w(S(\alpha_{\text{OPT}})) $$
> 3. We have that: $$\begin{align}\mathbb{P}\left( w(S(\alpha))< \frac{49}{100}w_{\text{OPT}} \right)&=\prod_{k=1}^{n}\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}w_{\text{OPT}} \right)\\&=\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}w_{\text{OPT}} \right)^n \\&=\mathbb{P}\left( w(S(\alpha_{i}))< \frac{49}{100}W\right)^n \\&=\mathbb{P}\left(W- w(S(\alpha_{i}))> \frac{51}{100}W \right)^n\\&\leq  \left( \frac{50}{51} \right)^n\end{align}$$Therefore, if $n=233$, then we get that it is a $0.49$-approximation with $99\%$ probability.

---
> [!lemma] Theorem 2 (Linear Programming)
> Let $(y^{*},z^{*})$ be the optimal solution of the LP:$$\begin{align}\text{max}\quad&\sum_{j=1}^{m}w_{j}z_{j}\\\text{subject to}\quad &\sum_{i\in S_{j}^+}^{}y_{i}+\sum_{i\in S_{j}^-}^{}(1-y_{i})\geq z_{j}&&\forall j\in [m]\\&0\leq z_{j}\leq 1&&\forall j\in [m]\\&0\leq y_{i}\leq 1&&\forall i\in[n]\end{align}$$
> Then, let $\alpha(x_{i})=1$ with probability $y^{*}_{i}$. We have that:
> 1. $\mathbb{P}(\alpha \text{ satisfies }c_{j})\geq \left( 1-\left( 1-\frac{1}{k} \right)^k \right)z^{*}_{j}$

> [!proof]+
> We have that:
> 1. Notice that: $$\begin{align}\mathbb{P}(\alpha \text{ doesn't satisfy }c_{j})&=\prod_{i\in S^+_{j}}^{}(1-y_{i}^{*})\prod_{i\in S_{j}^-}^{}y^{*}_{i}\\&\leq \left(  \frac{\sum_{i\in S^+_{j}}^{}(1-y_{i}^{*})+\prod_{i\in S_{j}^-}^{}y^{*}_{i}}{k}\right)^k\\&\leq \left(  \frac{k-z^{*}_{j}}{k}\right)^k \end{align}$$Then, $$\mathbb{P}(\alpha \text{ satisfies }c_{j})\geq 1-\left( 1-\frac{z^{*}_{j}}{k} \right) ^k\geq \left( 1-\left( 1-\frac{1}{k} \right)^k \right) z^{*}_{j}$$